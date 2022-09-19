# Overview

Git is **open-source version control software**, used for managing and tracking file revisions. It can be used with any file type, but is most often used for tracking code files.

<figure><img src=".gitbook/assets/git.png" alt=""><figcaption></figcaption></figure>

* Tracking code changes
* Tracking who made changes
* Coding collaboration

#### What does Git do?

* Manage projects with **Repositories**
* **Clone** a project to work on a local copy
* Control and track changes with **Staging** and **Committing**
* **Branch** and **Merge** to allow for work on different parts and versions of a project
* **Pull** the latest version of the project to a local copy
* **Push** local updates to the main project

<figure><img src="https://git-scm.com/book/en/v2/images/areas.png" alt=""><figcaption></figcaption></figure>

#### Working with Git

* Initialize Git on a folder, making it a **Repository**
* Git now creates a hidden folder to keep track of changes in that folder
* When a file is changed, added or deleted, it is considered **modified**
* You select the modified files you want to **Stage**
* The **Staged** files are **Committed**, which prompts Git to store a **permanent** snapshot of the files
* Git allows you to see the full history of every commit.
* You can revert back to any previous commit.
* Git does not store a separate copy of every file in every commit, but keeps track of changes made in each commit!

You have probably already worked with some form of version control. For example, Google Docs (as well as other Google Workspace tools) has a "Version History" tool where you can see the changes made to the document at different times. Microsoft Office has something similar with its "Track Changes" feature. Or maybe you prefer to save multiple copies of a file and label them "v1", "v2", etc.

Advanced version control is necessary for software projects, especially collaborative ones. When building software, developers are frequently and simultaneously updating the code to add features and fix bugs. It wouldn’t make sense to make these changes to the source code directly, since any issues would affect users. Instead, developers work with their own copies of the code, then — after the code has been thoroughly tested — add this code to the main codebase.

That seems all well and good. But, with multiple contributors, things can get very messy very quickly if there’s no way to combine everyone’s contributions into one unified codebase or see who contributed what changes. These changes also must be tracked and stored in case something breaks and the developers need to backtrack and restore a previous version.

This is what Git is for. When a developer wants to make a change to the software, they download their own copy of the source code from its central storage location (called a repository, or “repo” for short) to their local system, make modifications safely to their own copy, then merge their revised copy back with the source files in the repository along with comments explaining the changes. Git tracks all of these modifications and stores previous versions as backups.
