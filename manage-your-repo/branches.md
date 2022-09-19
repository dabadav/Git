---
description: https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell
---

# Branches

### Create a New Branch

The most common way to create a new branch is the following:

```bash
git checkout -b <branch-name>
```

In order to check the existing branches and in which one are you currently working, you can use

```bash
git branch
```

And I you want to move to another branch and start working there:

```bash
git checkout <branch-name>
```

### Rename a Local Git Branch <a href="#renamealocalgitbranch" id="renamealocalgitbranch"></a>

To rename a local branch, you'll want to use the `branch` command like this:

```bash
git branch -m <old-branch-name> <new-branch-name>
```

The `-m` option is an alias for `--move`, which is analog to the Unix `mv` command.

Continuing with the convention we saw with the [delete branch option](https://stackabuse.com/git-delete-branch-locally-and-remotely/), capitalizing the flag as `-M`, which is an alias for `--move --force`, allows you to "force" the change. Using the option in this way will let you rename the branch even if the new branch name already exists in your repository.

If you're wanting to rename the branch that is currently checked out, then you can omit the `<old-branch-name>` option, which looks like this:

```bash
git branch -m <new-branch-name>
```

### Rename a Remote Git Branch <a href="#renamearemotegitbranch" id="renamearemotegitbranch"></a>

Renaming a remote branch is a bit more involved, and isn't actually possible in the same way it is for renaming local branches. To do it, you'll need to rename the local branch, delete the remote branch, and then push the renamed local branch to the remote repo again.

In terms of Git commands, here is how the process looks:

```bash
git branch -m <old-branch-name> <new-branch-name>
git push <remote-repo> -d <old-branch-name>
git push <remote-repo> <new-branch-name>
git checkout <new-branch-name>
git push <remote-repo> -u <new-branch-name>
```
