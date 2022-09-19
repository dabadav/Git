# Creating a Repo

### 1. Create a new Repo in GitHub

A repository contains all project files, including the revision history. Great repository names are short and memorable.

Sign in to [GitHub](https://github.com) and click on the New button on the top right side

![](<../.gitbook/assets/image (1).png>)

* Fill in the information relative to the new repository: name, description, type, license, excludes..
* Copy the URL to use it later

### 2. Set your local folder as git repository

#### git init

```
# Change directory to the desired folder
cd C:\Users\fm85102\Documents\Coding\repos\powershell
 
# Set current folder as git repository, it creates .git folder underneath
git init
```

#### About Configuration scopes

```
git config -[--local | --global |--system ]   

# system applies to  every repositorCreate your first repo
1. Create repo in GitHub

A repository contains all project files, including the revision history. Great repository names are short and memorable.

Sign in to github.com and click on the New button on the top right side

    Fill in the information relative toe new repository: name, description, type, license, excludes...
    Copy the URL to use it later

CreateRepositoryGitHub
2. Set your local folder as git repository
git init

# Change directory to the desired folder
cd C:\Users\fm85102\Documents\Coding\repos\powershell
 
# Set current folder as git repository, it creates .git folder underneath
git init

About Configuration scopes

git config -[--local | --global |--system ]   

# system applies to  every repository for all users in your computer
# global applies to  every repository that you use on your computer
# local applies only to current repository
# Settings defined in the most local scope take precedence

Configure username and email

# Set username and email
git config --global user.name "John Doe"
git config --global user.email "jdoe@proton.com"

cd C:\Users\fm85102\CLionProjects\stack
git config --global user.name  jdoe  
git config --global user.email jdoe@proton.com

Configure the default editor

git config --global editor nano  

3. Configure remote repository

# Define one or more remote repositories
git remote add origin https://github.com/dubium/powershell.git

# Verify remote repository URLs, you could setup different URLs for fetch adn push
git remote --verbose
origin https://github.com/dubium/powershell.git (fetch)
origin https://github.com/dubium/powershell.git (push)

# To establish a connection between our local master branch and the remote master branch 'origin' 
# 'origin' is the default name for remote repositories
git remote set-url --add origin https://github.com/dubium/powershell.git

# If you wish to set tracking information for this branch you can do so with:
# git branch --set-upstream-to=origin/master master


# To remove a remote repository
git remote set-url --delete origin https://github.com/dubium/powershell.git

# Show remote repositories 
git remote -v
origin https://github.com/dubium/powershell.git (fetch)
origin https://github.com/dubium/powershell.git (push)

git remote get-url --all origin
https://github.com/dubium/powershell.git

Working with a Local repository
Stage and commit

In order to record changes you made in your files (renamed, removed, added folder) to must add stage them, so that next commit operation will register thse changes

# Add all files in the local repository to git and stage them for commit
git add .

# Add a single file to git and stage them for commit
git add readme.md

# To unstage a file 
git reset HEAD <filename>

# To create a commit
git commit -m "First commit"

Undo local changes

[]: https://docs.gitlab.com/ee/topics/git/numerous_undo_possibilities_in_git/	"Numerous undo possibilities in Git"

Until you push your changes to any remote repository, they will only affect you. That broadens your options on how to handle undoing them. Still, local changes can be on various stages and each stage has a different approach on how to tackle them.

git log
git status
git clean
git checkout <filename>

Unstaged local changes (before you commit)

When a change is made, but it is not added to the staged tree, Git itself proposes a solution to discard changes to certain file.

Suppose you edited a file to change the content using your favorite editor:

vim <file>

Since you did not git add to staging, it should be under unstaged files (or untracked if file was created). You can confirm that with:

$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

    modified:   <file>
no changes added to commit (use "git add" and/or "git commit -a")

At this point there are 3 options to undo the local changes you have:

    Discard all local changes, but save them for possible re-use later:

    git stash

    Discarding local changes (permanently) to a file:

    git checkout -- <file>

    Discard all local changes to all files permanently:

    git reset --hard

Before executing git reset --hard, keep in mind that there is also a way to just temporary store the changes without committing them using git stash. This command resets the changes to all files, but it also saves them in case you would like to apply them at some later time. You can read more about it in section below. *** update pointer ***
Quickly save local changes

You are working on a feature when a boss drops by with an urgent task. Since your feature is not complete, but you need to swap to another branch, you can use git stash to save what you had done, swap to another branch, commit, push, test, then get back to previous feature branch, do git stash pop and continue where you left.

The example above shows that discarding all changes is not always a preferred option, but Git provides a way to save them for later, while resetting the repository to state without them. This is achieved by Git stashing command git stash, which in fact saves your current work and runs git reset --hard, but it also has various additional options like:

    git stash save, which enables including temporary commit message, which will help you identify changes, among with other options
    git stash list, which lists all previously stashed commits (yes, there can be more) that were not poped
    git stash pop, which redoes previously stashed changes and removes them from stashed list
    git stash apply, which redoes previously stashed changes, but keeps them on stashed list

Staged local changes (before you commit)
Working with a remote repository
Git Protocols

Git protocols
git clone

git clone https://github.com/StructureLunatics/LunaticsIntoAction 

git log

git log
git log --oneline
git shortlog / git --format

git show HEAD
git show HEAD
git show <commit>
git remote
git remote -v

git push and git pull

# Examples
MINGW64 ~/Documents/Coding/repos/powershell (dev)
# Push from current local <branch> = dev 
git push                     # origin/dev. Default remote repo, local branch
git push origin              # origin/dev. Specifing remote repo, local branch
git push origin development  # origin/dev. Specifing both remote repo and branch
git push origin master       # origin/master Specifing both remote repo and branch

If the local branch does not exist in the remote repository, push will fail

MINGW64 ~/Documents/Coding/repos/powershell (development)

git push --set-upstream origin development

Push contents to the remote repository

git push origin master
git pull origin master
git pull origin master
y for all users in your computer
# global applies to  every repository that you use on your computer
# local applies only to current repository
# Settings defined in the most local scope take precedence
```

#### Configure the default editor

```
git config --global editor nano  
```

### 3. Configure remote repository

```
# Define one or more remote repositories
git remote add origin https://github.com/dubium/powershell.git

# Verify remote repository URLs, you could setup different URLs for fetch adn push
git remote --verbose
origin https://github.com/dubium/powershell.git (fetch)
origin https://github.com/dubium/powershell.git (push)

# To establish a connection between our local master branch and the remote master branch 'origin' 
# 'origin' is the default name for remote repositories
git remote set-url --add origin https://github.com/dubium/powershell.git

# If you wish to set tracking information for this branch you can do so with:
# git branch --set-upstream-to=origin/master master


# To remove a remote repository
git remote set-url --delete origin https://github.com/dubium/powershell.git

# Show remote repositories 
git remote -v
origin https://github.com/dubium/powershell.git (fetch)
origin https://github.com/dubium/powershell.git (push)

git remote get-url --all origin
https://github.com/dubium/powershell.gitsudo apt install git-all
```

##

## Working with a Local repository

### Stage and commit

In order to record changes you made in your files (renamed, removed, added folder) to must add stage them, so that next commit operation will register thse changes

```
# Add all files in the local repository to git and stage them for commit
git add .

# Add a single file to git and stage them for commit
git add readme.md

# To unstage a file 
git reset HEAD <filename>

# To create a commit
git commit -m "First commit"
```



### Undo local changes

\[]: [https://docs.gitlab.com/ee/topics/git/numerous\_undo\_possibilities\_in\_git/](https://docs.gitlab.com/ee/topics/git/numerous\_undo\_possibilities\_in\_git/) "Numerous undo possibilities in Git"

Until you push your changes to any remote repository, they will only affect you. That broadens your options on how to handle undoing them. Still, local changes can be on various stages and each stage has a different approach on how to tackle them.

```
git log
git status
git clean
git checkout <filename>
```

####

#### Unstaged local changes (before you commit)

When a change is made, but it is not added to the staged tree, Git itself proposes a solution to discard changes to certain file.

Suppose you edited a file to change the content using your favorite editor:

```
vim <file>
```

Since you did not `git add` to staging, it should be under unstaged files (or untracked if file was created). You can confirm that with:

```
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

    modified:   <file>
no changes added to commit (use "git add" and/or "git commit -a")
```

At this point there are 3 options to undo the local changes you have:

*   Discard all local changes, but save them for possible re-use [later](https://docs.gitlab.com/ee/topics/git/numerous\_undo\_possibilities\_in\_git/#quickly-save-local-changes):

    ```
    git stash
    ```
*   Discarding local changes (permanently) to a file:

    ```
    git checkout -- <file>
    ```
*   Discard all local changes to all files permanently:

    ```
    git reset --hard
    ```

Before executing `git reset --hard`, keep in mind that there is also a way to just temporary store the changes without committing them using `git stash`. This command resets the changes to all files, but it also saves them in case you would like to apply them at some later time. You can read more about it in [section below](https://docs.gitlab.com/ee/topics/git/numerous\_undo\_possibilities\_in\_git/#quickly-save-local-changes). \*\*\* update pointer \*\*\*

####

#### Quickly save local changes

You are working on a feature when a boss drops by with an urgent task. Since your feature is not complete, but you need to swap to another branch, you can use `git stash` to save what you had done, swap to another branch, commit, push, test, then get back to previous feature branch, do `git stash pop` and continue where you left.

The example above shows that discarding all changes is not always a preferred option, but Git provides a way to save them for later, while resetting the repository to state without them. This is achieved by Git stashing command `git stash`, which in fact saves your current work and runs `git reset --hard`, but it also has various additional options like:

* `git stash save`, which enables including temporary commit message, which will help you identify changes, among with other options
* `git stash list`, which lists all previously stashed commits (yes, there can be more) that were not `pop`ed
* `git stash pop`, which redoes previously stashed changes and removes them from stashed list
* `git stash apply`, which redoes previously stashed changes, but keeps them on stashed list

####

#### Staged local changes (before you commit)

##

## Working with a remote repository

###

### Git Protocols



####

#### git clone

```
git clone https://github.com/StructureLunatics/LunaticsIntoAction 
```

####

#### git log

```
git log
git log --oneline
git shortlog / git --format

git show HEAD
git show HEAD
git show <commit>
git remote
git remote -v
```

####

#### git push and git pull

```
# Examples
MINGW64 ~/Documents/Coding/repos/powershell (dev)
# Push from current local <branch> = dev 
git push                     # origin/dev. Default remote repo, local branch
git push origin              # origin/dev. Specifing remote repo, local branch
git push origin development  # origin/dev. Specifing both remote repo and branch
git push origin master       # origin/master Specifing both remote repo and branch
```

If the local branch does not exist in the remote repository, push will fail

```
MINGW64 ~/Documents/Coding/repos/powershell (development)

git push --set-upstream origin development
```

Push contents to the remote repository

```
git push origin master
git pull origin master
git pull origin master
```
