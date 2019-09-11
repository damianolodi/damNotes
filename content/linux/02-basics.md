---
title: "Basics"
draft: false
arguments: ["Documentation", "File Management", "Extracting Information from Files" , "Packages"]
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

-   `history` → return executed **commands history**

    -   `history -c` → _clean_ the history

    -   `history` > `ctrl + R` → activate _search in the history_ (can execute them on the fly)

-   `echo val*.sh` → search for all files delimited by 'val' and '.sh' containing whichever number of characters in the middle

    -   `echo val?.sh` → as before, but `?` replace a single character

    -   `echo val??.sh`

* * *

### Documentation

-   `type executable` → return **type of the executable** (builtin or path if external). It returns the alias if defined

-   `help command_name` → return documentation for builtin commands

-   `man command_name` → return documentation for external commands. This manuals are found in `/usr/share/doc/` and `/usr/share/man/`

    -   > `shift + 7` → search in the manual

    -   > `n`, `N` → next/previous result

* * *

### File Management

-   `touch file_name` → create new file

-   `mkdir dir_name` → create new directory

    -   `mkdir -p parent_dir/dir` → **crete parent directories** if not present

    -   `rmdir parent_dir/dir` → **remove `dir`** (**not** the parent directory). **NOT WORKING** on non-empty directories

-   `rm file_name` → remove file

    -   `rm -r dir` → remove the directory and **all files** contained in it (`r` stands for _recursive_)

-   `mv what_path where_path` → **move** a file into a new directory

-   `mw file new_name` → **rename** the file

-   `cp what where/new_name` → **copy file** in a new location

    -   `cp -r dir where/new_name` → **copy direcotry** and all its content into a new location

-   `file file_name` → return information about the file

#### Archive and Compression

-   `tar -cvf archive_name.tar *` → **create archive** containing all the file in the current direcotry (`-c` create, `-v` verbose, `-f` provide file name)

    -   `tar -cjf archive_name.tar.bz2 *`, `tar -cJf archive_name.tar.xz *` → create archives with different compression algorithm (`-j` for bz2, `-J` for xz)

    -   `tar -tf archive_name.tar` → list the file contained in the archive (`-t` display archive)

    -   `tar -xjf archive_name.tar.bz2 -C final_dir/` → **extract archive** (compress with proper algoritjm provided in the parameters) in the provided directory. Remove `-C` parameter to extract in the current directory

-   `gzip file_name` → **compress file** and delete the original. Can use also `bzip2`

-   `gunzip file_name` → **unzip** compress file

-   `zip archive_name.zip *` → create a zip archive. Reverse with `unzip archive_name.zip`

* * *

### Extracting Information from Files

-   `cat file_name` → print file content. Not very practical for big files

    -   `cat file_name | less` → redirect output to the program _less_, to visualize small bunch of content (can use `less file_name`)

    -   > `shift + 7`, 'n' and 'N' → search, next and previous results

-   `head file_name -n num` → print the **first _num_ lines** of the file. Remove the `-n` parameter to print first 10 lines

-   `tail file_name -n num` → print the **last _num_ lines** of the file. Remove the `-n` parameter to print last 10 lines

-   `grep "string" file_name` → **print the line containing _string_**

-   `sort file_name` → sort the lines alphabetically (`-r` reverse alphabetical order, `-R` random order, `-n` number). Can receive the input also with a pipe, e.g. `cat filename | sort -r`

-   `wc` → return _lines_, _words_ and _charactes_ contained in the file (`-l` return only number of lines, `-c` return only number of characters) It stands for _word count_

-   `cut -d : -f 1,7 file_name` → take each line, separate information using delimiter `-d` and take 1st and 7th column

#### Usage Example

```bash
cat rubrica | grep "0376" | sort -r > contacts.txt # save result in a file

cat /etc/passwd | cut -d : -f 1 | wd -l
```

* * *

### Usefull Commands

-   `echo $0` → return shell type in use (`$0` is a special variable that containt the name of the process in execution)
    -   `$$` → special variable containing the process id (pid - proper number of the process in execution)
