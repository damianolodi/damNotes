---
title: "Security and Permissions"
draft: false
arguments: ["User Types",
            "File Permissions"]
weight: 07
---

There are 3 types of users: 

1. _standard_ user &rarr; can do only some things. User ID start from 1000

2. _system_ user &rarr; particular standard user. User ID under 1000

3. _root_ user &rarr; can do everything

The list of all users is found inside `/etc/passwd`

- `who` &rarr; display active users and relative informations. Use `w` for more detailed informations

- `last` &rarr; display the history of user's logins on the system

The directory `/etc/skel/` contains all the files that will be copied into the home of a newly created user.

* * *

### File Permissions

Using `ls -l` on a file will return infomrations on it. In particular one will have something like

```bash
-rw-r--r-- 1 user group 0 date name
```

(Use `ls -ld direcotry_name` to obtain informations about the directory instead of displaying its content)

In the order, the following informations are displayed: permissions, number of link pointing to this files, owner user name, owner group name, dimension, creation date and name of the file.

The permissions characters descibe the following propertis:

- character 1 &rarr; kind of element (file, directory, link,...)

- characters 2-4 &rarr; permission for the owner (_u_) (`r` read, `w` write, `x` execute)

- characters 5-7 &rarr; permission for the owner group (_g_)

- characters 8-10 &rarr; permission for all the other users (_o_)

One can add/remove permissions to a certain file using `chmod +x file_name`. This will add execution permission to _all user groups_ reported above.

- `chmod u+x file_name` &rarr; add execution permission only to the owner

- `chmod o-r file_name` &rarr; remove read permission to all users outside the owner and the owner's group

- `chmode +t file_name` &rarr; _add the sticky bit_ to the file permissions. This means that only the owner can delete the file