---
title: "Bash Scripts"
draft: false
arguments: []
weight: 1
---

### Making Custom Commands

-   Access the `.bashrc` file with

```shell
nano ~/.bashrc
```

_Open with `nano` and not with `open`, otherwise problems may occur when applying the following steps._

-   Inside the file, write the following

```shell
alias command_name="command1 && command2 && ..."
```

The `&&` apply the following command only if the current one is succesfull. On the other hand, use `;` to run all the commands one after the other.

-   Save the file and use the following command to apply changes

```shell
source ~/.bashrc
```

* * *

### Automatic File Sourcing

-   In OSX, _all sessions are login sessions and will not source `$HOME/.bashrc`_, they will source `$HOME/.profile` or `$HOME/.bash_profile`. So, to source automatically the `.bashrc` file, put the following in your `.bash_profile`:

```shell
if [ -f ~/.bashrc ]; then
    source ~/.bashrc
fi
```

[Reference](https://stackoverflow.com/questions/44658135/osx-terminal-not-recognizing-bashrc-and-bash-profile-on-startup)
