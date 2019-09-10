---
title: "Basics"
draft: false
arguments: [""]
weight: 02
---

### Bash Basics

```bash
var = "value"        # define new variable
export var = "value" # define variable also for othe bash sessions

echo $var            # access the value of a variable
which command_name   # return the path in which the executable is found
```

-   `bash` → open a new bash session

    -   `exit` → exit from the current bash session

-   `env` → list all environment variables

    -   `PATH` → variable that contains all the paths (separated by columns) in which to search for executables


-   `alias` → return all defined aliases

    -   `alias ls = 'ls -al'` → define a new alias

    -   `unalias ls` → remove all associated aliases

-   `type executable` → return the type of the executable (builtin, or the path in which is found). It return the alias if defined

-   `history` → return the history of the commands executed in bash

    -   `history -c` → clean the history

    -   `history` > `ctrl + R` → activate search in the history. Search for previous commands and execute them on the fly

-   `echo val*.sh` → search for all files delimited by 'val' and '.sh' containing whichever number of characters in the middle

    -   `echo val?.sh` → as before, but `?` replace a single character

    -   `echo val??.sh`

* * *

### Usefull Commands

-   `echo $0` → return shell type in use (`$0` is a special variable that containt the name of the process in execution)
    -   `$$` → special variable containing the process id (pid - proper number of the process in execution)
