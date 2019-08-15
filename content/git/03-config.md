---
title: "Config"
draft: false
---

The `--global` input means that one wants to apply this setting to all the project, not just the current one.

1.  `git config --global user.name <name>` -> define the author name to be used fo all commits by the current user

2.  `git config --global user.email <email>`

3.  `git config --global alias. <alias-name> <git-command>` -> create shortcut for a git command

    -   e.g. `git config --global alias.ciao commit -m` set `git ciao` to `git commit -m`

4.  `git config --global color.ui auto` -> activate the color code while using the diff command

5.  `git config —global core.editor “atom —wait”` -> open a text editor when needed (in this case Atom)

6.  `git config user.name <name>` define the author name used for all the commits in the current repo
