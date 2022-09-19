# Overview

<figure><img src=".gitbook/assets/git.png" alt=""><figcaption></figcaption></figure>

Git is open-source version control software, used for managing and tracking file revisions. It can be used with any file type, but is most often used for tracking code files.

You’ve likely worked with some form of version control before. For example, Google Docs (as well as other Google Workspace tools) has a “Version History” tool where you can view changes to the document at different points in time. Microsoft Office has something similar with its “Track Changes” feature. Or, you might prefer saving multiple copies of a file and labeling them “v1”, “v2”, etc.

Advanced version control is necessary for software projects, especially collaborative ones. When building software, developers are frequently and simultaneously updating the code to add features and fix bugs. It wouldn’t make sense to make these changes to the source code directly, since any issues would affect users. Instead, developers work with their own copies of the code, then — after the code has been thoroughly tested — add this code to the main codebase.

That seems all well and good. But, with multiple contributors, things can get very messy very quickly if there’s no way to combine everyone’s contributions into one unified codebase or see who contributed what changes. These changes also must be tracked and stored in case something breaks and the developers need to backtrack and restore a previous version.

This is what Git is for. When a developer wants to make a change to the software, they download their own copy of the source code from its central storage location (called a repository, or “repo” for short) to their local system, make modifications safely to their own copy, then merge their revised copy back with the source files in the repository along with comments explaining the changes. Git tracks all of these modifications and stores previous versions as backups.
