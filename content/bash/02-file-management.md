---
title: "File Management"
draft: false
arguments: ["Create and Remove Files",
            "Copy and Move Files",
            "Archive Creation",
            "File Compression"]
weight: 02
---

-   `touch file_name` &rarr; **create** new file

-   `mkdir dir_name` &rarr; create new directory

    -   `mkdir -p parent_dir/dir` &rarr; **crete parent directories** if not present

    -   `rmdir parent_dir/dir` &rarr; **remove `dir`** (**not** the parent directory). **NOT WORKING** on non-empty directories

-   `rm file_name` &rarr; remove file

    -   `rm -r dir` &rarr; remove the directory and **all files** contained in it (`r` stands for _recursive_)

-   `mv what_path where_path` &rarr; **move** a file into a new directory

-   `mw file new_name` &rarr; **rename** the file

-   `cp what where/new_name` &rarr; **copy file** in a new location

    -   `cp -r dir where/new_name` &rarr; **copy direcotry** and all its content into a new location

-   `file file_name` &rarr; return information about the file

#### Archive and Compression

-   `tar -cvf archive_name.tar *` &rarr; **create archive** containing all the file in the current direcotry (`-c` create, `-v` verbose, `-f` provide file name)

    -   `tar -cjf archive_name.tar.bz2 *`, `tar -cJf archive_name.tar.xz *` &rarr; create archives with different compression algorithm (`-j` for bz2, `-J` for xz)

    -   `tar -tf archive_name.tar` &rarr; list the file contained in the archive (`-t` display archive)

    -   `tar -xjf archive_name.tar.bz2 -C final_dir/` &rarr; **extract archive** (compress with proper algoritjm provided in the parameters) in the provided directory. Remove `-C` parameter to extract in the current directory

-   `gzip file_name` &rarr; **compress file** and delete the original. Can use also `bzip2`

-   `gunzip file_name` &rarr; **unzip** compress file

-   `zip archive_name.zip *` &rarr; create a zip archive. Reverse with `unzip archive_name.zip`