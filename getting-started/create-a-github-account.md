# Creating a Repo

### Create a new Repo in GitHub

A repository contains all project files, including the revision history. Great repository names are short and memorable.

Sign in to [GitHub](https://github.com) and click on the New button on the top right side

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

* Fill in the information relative to the new repository: name, description, type, license, excludes..
* Copy the URL to use it later

### Set your local folder as git repository

If you have a project directory that is currently not under version control and you want to start controlling it with Git, you first need to go to that project’s directory. If you’ve never done this, it looks a little different depending on which system you’re running:

for Linux:

```bash
cd /home/user/my_project
git init
```

This creates a new subdirectory named `.git` that contains all of your necessary repository files — a Git repository skeleton. At this point, nothing in your project is tracked yet. See [Git Internals](https://git-scm.com/book/en/v2/ch00/ch10-git-internals) for more information about exactly what files are contained in the `.git` directory you just created.

If you want to start version-controlling existing files (as opposed to an empty directory), you should probably begin tracking those files and do an initial commit. You can accomplish that with a few `git add` commands that specify the files you want to track, followed by a `git commit`:

```bash
git add *.c
git add LICENSE
git commit -m 'Initial project version'
```

We’ll go over what these commands do in just a minute. At this point, you have a Git repository with tracked files and an initial commit.

In order to publish the local repo to GitHub, create an empty repo add configure the push destination

```bash
git remote add my_project https://github.com/user/my_project
```

Then push the current branch and set the remote as upstream

```bash
git push --up-stream my_project master
```

### Cloning an Existing Repository <a href="#_git_cloning" id="_git_cloning"></a>

If you want to get a copy of an existing Git repository — for example, a project you’d like to contribute to — the command you need is `git clone`. If you’re familiar with other VCSs such as Subversion, you’ll notice that the command is "clone" and not "checkout". This is an important distinction — instead of getting just a working copy, Git receives a full copy of nearly all data that the server has. Every version of every file for the history of the project is pulled down by default when you run `git clone`. In fact, if your server disk gets corrupted, you can often use nearly any of the clones on any client to set the server back to the state it was in when it was cloned (you may lose some server-side hooks and such, but all the versioned data would be there — see [Getting Git on a Server](https://git-scm.com/book/en/v2/ch00/\_getting\_git\_on\_a\_server) for more details).

You clone a repository with `git clone <url>`. For example, if you want to clone the Git linkable library called `Test`, you can do so like this:

```
git clone https://github.com/dav-esci/Test
```

That creates a directory named `Test`, initializes a `.git` directory inside it, pulls down all the data for that repository, and checks out a working copy of the latest version. If you go into the new `Test` directory that was just created, you’ll see the project files in there, ready to be worked on or used.
