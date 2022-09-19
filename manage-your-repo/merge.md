---
description: >-
  One of Git's most powerful features is the ability to easily create and merge
  branches. As part of the development process user can create new branches
  often and regularly merge them.
---

# Merge

A commonly used branching workflow in Git is to create a new code branch for each new feature, bug fix, or enhancement. These are called _**Feature Branches**_. Each branch compartmentalizes the commits related to a particular feature. Once the new feature is complete – i.e. a set of changes has been committed on the feature branch – it is ready to be merged back into the master branch (or other main code line branch depending on the workflow in use).

If you're merging a new feature into the main branch, you first want to switch to the main branch and then merge into it:

<pre class="language-bash"><code class="lang-bash"><strong>git checkout -b new-branch
</strong><strong>
</strong><strong># ...develop some code...
</strong>
git add –A
git commit –m "Some commit message"
git checkout main
Switched to branch 'main'
git merge new-branch</code></pre>

If all goes well then our job is done. The new feature commits now appear in the main branch. However, it is possible that Git won't be able to complete the merge due to a conflict change in the source branch. This is called a _**merge conflict**_.

### Solving Merge Conflicts

