---
description: >-
  Whether you accidentally commit changes, or just realized your previous
  committed code isn't what you wanted, often times you'll need to revert a
  previous commit in Git.
---

# Revert to previous commit

### Delete Unpublished Commits <a href="#deleteunpublishedcommits" id="deleteunpublishedcommits"></a>

If you haven't yet published your commits to a remote repository, like GitHub, then you can essentially delete previous commits by using the `reset` command.

While this is an effective solution, it's a dangerous one since you're rewriting history and leaving the "deleted" commits unreferenced, or "orphaned". The only way to find and recover these unreferenced commits is with `git reflog`.

The `reset` command has three different options, two of which we'll describe here:

```bash
git reset --hard <hash-or-ref>
```

Using the `--hard` option, everything is reverted back to the specified commit. This includes the commit history reference pointers, the staging index, and your working directory.

This means that by using just this command you'll not only revert to a previous commit, but you'll lose all working changes in the process. To avoid losing any working changes, you can use the `stash` and `stash pop` commands:

```bash
git stash
git reset --hard <hash-or-ref>
git stash pop
```

The `stash` command saves your working changes (without any commits or changes to the tree), and then `stash pop` brings them back.

The other option you may consider is the `--soft` option. This option works much the same way as `git reset --hard <hash-or-ref>`, but it only affects the commit history, not your working directory or staging index.

```bash
git reset --soft <hash-or-ref>
```

So if you have uncommitted changes that you want to keep, then this is likely the option you want.

### Deleting Published Commits <a href="#deletingpublishedcommits" id="deletingpublishedcommits"></a>

So let's say you committed your code and then pushed it to the remote repository. At this point it's highly advised that you **do not** use something like `git reset` since you'd be rewriting history.

Instead, the recommended approach would be to use the `revert` command. This command works by undoing changes that were made in the specified commit by creating a _new commit_ and not actually removing any previous commits. This is ideal for published changes because then the true history of the repo is preserved. Here is the command:

```bash
git revert <hash-or-ref>
```

So let's say you have a text file in your repo with the following content:

```
This is my sample text
```

And then you change it to:

```
This is my awesome sample text
```

Your commit history might look something like this:

```bash
git log --pretty=oneline
676ec97a9cb2cebbb5c77904bbc61ced05b86f52 Added 'awesome' to text
735c5b43bf4b5b7107a9cc3f6614a3890e2889f6 Initial commit
```

If we decide we don't want "awesome" in our text anymore, but we don't want to delete the `676ec` commit, we can use `revert` to undo that change:

```bash
git revert 676ec
[master f68e546] Revert "Added 'awesome' to text"
 1 file changed, 1 insertion(+), 1 deletion(-)
```

After being prompted to enter a commit message, we can now see in our commit history that there is actually a new commit:

```bash
git log --pretty=oneline
f68e546ac2ae240f22b2676b5aec499aab27f1ca Revert "Added 'awesome' to text"
676ec97a9cb2cebbb5c77904bbc61ced05b86f52 Added 'awesome' to text
735c5b43bf4b5b7107a9cc3f6614a3890e2889f6 Initial commit
```

As a result of this, the first and third commits represent the exact same project state. The commit has been reverted, and no history was lost.
