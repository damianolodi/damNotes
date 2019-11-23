---
title: "Basics"
draft: false
---

<img src="/img/content/git/git_workflow.png" class="img-fluid figure-img img-custom">

1.  `git init <directory_path>` create empty git repository in the specified directory. Omit the arguments to initialise in the current directory
2.  `git add <file/directory>` stage all changes in the provided path for the next commit
3.  `git commit -m “<message>”` commit the staged changes with the message provided. Messages must be
    -   in quotation marks;
    -   written in the present tense;
    -   be brief (50 characters or less) when using -m
4.  `git status` list staged, unstaged and untracked files
5.  `git diff` show unstated changes between the index and the working directory
    -   `git diff <file>` preview the differences between the file in the working directory and the one in the staging area
6.  `git log` display the entire commit history. See options for format customization. The 40-character code, called a **SHA**, uniquely identifies the commit.
    -   `git log -<limit>` &rarr; limit the number of commits to the specified number
    -   `git log --oneline` &rarr; condense each commit to a single line
    -   `git log --grep="<pattern>"` &rarr; search for commits with a commit message that matches the one provided
    -   `git log -- <file>` &rarr; only display commits that have the specified file
    -   `git log --stat` &rarr; returns some statistics about which file has changed in each commit
