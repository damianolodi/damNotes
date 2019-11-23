---
title: "Command Line Setup"
draft: false
arguments: ["Terminal Setup on macOS",
            "Custom Commands"]
weight: 99
---

In `~`, the file `.bash_profile` is used for _login shells_, while `.bashrc` is used for _non-login shells_ (terminal session opened using the `bash` command).

In OSX, _all sessions are login sessions so they will not source `$HOME/.bashrc`_, they will source `$HOME/.profile` or `$HOME/.bash_profile` ([reference](https://stackoverflow.com/questions/44658135/osx-terminal-not-recognizing-bashrc-and-bash-profile-on-startup))

* * *

### Terminal Setup on macOS

- Open the `.bash_profile` file and type the following to automatically load the content of the file contained in `.bashrc`. This will guarantee that both type of shells will behave the same

```bash
if [ -f ~/.bashrc ]; then
    source ~./bashrc
fi
```

- Open the `.bashrc` file in a text editor

- Write the following

```bash
orange=$(tput setaf 166);
yellow=$(tput setaf 228);
green=$(tput setaf 71);
white=$(tput setaf 15);
bold=$(tput bold);
reset=$(tput sgr0);

PS1="\[${bold}\]\n";
PS1+="\[${orange}\]\u";
PS1+="\[${yellow}\]@\h";
PS1+="\[${white}\] in ";
PS1+="\[${green}\]\W";
PS1+="\n";
PS1+="\[${white}\]\$ \[${reset}\]";
export PS1;
```

- Finally type `source .bashrc` to apply changes

- Special character that could be used in the PS1 variable are:

    - `\h` (hostname), `\n` (newline), `\s` (shell name)
    
    - `\t` (current time), `\u` (current username)
    
    - `\w` (current working directory), `\W` (basename of the current working directory)

- `$()` is called _command substitution_

- Colors number can be found [here](https://upload.wikimedia.org/wikipedia/commons/1/15/Xterm_256color_chart.svg)

* * *

### Custom Commands

Open the `~/.bashrc` file and type the following

```bash
alias command_name="command1 && command2 && ..."
```

The `&&` apply the following command only if the current one is succesfull. On the other hand, use `;` to run all the commands one after the other.


* * *

### Sources

- [Customizing the Terminal - 2](https://youtu.be/vDOVEDl2z84) - Corey Shafer

- [Customizing the Terminal - 2](https://youtu.be/LXgXV7YmSiU) - Corey Shafer