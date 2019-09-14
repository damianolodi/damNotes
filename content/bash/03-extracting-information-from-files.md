---
title: "Files Information Extraction"
draft: false
arguments: ["Display Files",
            "Search Inside Files",
            "Lines Sorting",
            "Files Statistics"]
weight: 03
---

-   `cat file_name` &rarr; print file content. Not very practical for big files

    -   `cat file_name | less` &rarr; redirect output to the program _less_, to visualize small bunch of content (can use `less file_name`)

    -   \> `shift + 7`, `n` and `N` &rarr; search, next and previous results

-   `head file_name -n num` &rarr; print the **first _num_ lines** of the file. Remove the `-n` parameter to print first 10 lines

-   `tail file_name -n num` &rarr; print the **last _num_ lines** of the file. Remove the `-n` parameter to print last 10 lines

-   `grep "string" file_name` &rarr; **print the line containing _string_**

-   `sort file_name` &rarr; **sort the lines** alphabetically (`-r` reverse alphabetical order, `-R` random order, `-n` number). Can receive the input also with a pipe, e.g. `cat filename | sort -r`

-   `wc` &rarr; return _lines_, _words_ and _charactes_ contained in the file (`-l` return only number of lines, `-c` return only number of characters). It stands for _word count_

-   `cut -d : -f 1,7 file_name` &rarr; take each line, separate information using delimiter `:` and take 1st and 7th column

#### Usage Example

```bash
cat rubrica | grep "0376" | sort -r > contacts.txt # save result in a file

cat /etc/passwd | cut -d : -f 1 | wd -l
```