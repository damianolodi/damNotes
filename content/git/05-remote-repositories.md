---
title: "Remote Repositories"
draft: false
---

1.  `git clone <repository_path> <clone_name>` clone the provided repository in the current path. Original repo can be located on the local filesystem or on a remote machine via HTTP or SSH

2.  `git remote add <name> <url>` create a new connection to a remote repository.

    -   After adding a remote, you can use `<name>` as a shortcut for `<url>` in other commands.

    -   `git remote -v` -> lists the name of the remote, origin, as well as its location

3.  `git pull <remote>` fetch the specified remotes copy of the current branch and immediately merge it into the local copy

4.  `git push <remote> <branch>` push the branch to the remote repo. creates the named branch in the remote repo if it doesn’t exist

    -   `git push <remote> --all` push all the local branches

5.  `git fetch <remote> <branch>` fetches a specific branch from the repo. Leave off `<branch>` to fetch all remote refs.

    -   `git fetch` -> This command will not merge changes from the remote into your local repository. It brings those changes onto what’s called a remote branch.

        -   To explain this we can say that even though Sally’s new commits have been fetched to your local copy of the Git project, those commits are on the origin/master branch. Your local master branch has not been updated yet, so you can’t view or make changes to any of the work she has added.

        -   One can merge those changes in the local master branch by using the merge command `git merge origin/master`
