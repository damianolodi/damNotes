---
title: "Basics"
draft: false
arguments: ["Documentation", "File Management", "Extracting Information from Files" , "Packages"]
weight: 01
---

```bash
var = "value"        # define new variable
export var = "value" # define variable also for othe bash sessions

echo $var            # access the value of a variable
which command_name   # return the path in which the executable is found
```

-   `bash` &rarr; open a new bash session

    -   `exit` &rarr; exit from the current bash session

-   `env` &rarr; list all environment variables

    -   `PATH` &rarr; variable that contains all the paths (separated by columns) in which to search for executables

-   `alias` &rarr; return all defined aliases

    -   `alias ls = 'ls -al'` &rarr; define a new alias

    -   `unalias ls` &rarr; remove all associated aliases

-   `history` &rarr; return executed **commands history**

    -   `history -c` &rarr; _clean_ the history

    -   `history` > `ctrl + R` &rarr; activate _search in the history_ (can execute them on the fly)

-   `echo val*.sh` &rarr; search for all files delimited by 'val' and '.sh' containing whichever number of characters in the middle

    -   `echo val?.sh` &rarr; as before, but `?` replace a single character

    -   `echo val??.sh`

* * *

### Documentation

-   `type command_name` &rarr; return **type of the executable** (builtin or path if external). It returns the alias if defined

-   `help command_name` &rarr; return documentation for builtin commands

-   `man command_name` &rarr; return documentation for external commands. This manuals are found in `/usr/share/doc/` and `/usr/share/man/`

    -   \> `shift + 7` &rarr; search in the manual

    -   \> `n`, `N` &rarr; next/previous result

* * *

### Usefull Commands

-   `echo $0` &rarr; return shell type in use (`$0` is a special variable that containt the name of the process in execution)
    -   `$$` &rarr; special variable containing the process id (pid - proper number of the process in execution)
