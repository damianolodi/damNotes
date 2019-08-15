---
title: "Os and Datetime"
draft: false
---

```py
import os
import datetime
```

* * *

## Os

-   `os.getcwd()` obtain the current working directory
-   `os.listdir(path)` list all file in the path. Better using `scandir()` for more performance
-   `os.chdir(path)` change the cwd to path
-   `os.remove(path)` remove a file

-   `os.mkdir(path)` create a directory. To avoid errors if the directory exist, use

```py
dirName = 'tempDir'
try:
    # Create target Directory
    os.mkdir(dirName)
    print("Directory " , dirName ,  " Created ")
except FileExistsError:
    print("Directory " , dirName ,  " already exists")
```

-   `os.rename(current-path, destination-path)` move or rename a file

-   `os.scandir(path)` scan all files in the path and create an `os.DirEntry` object containing all files with their information. Follow the [doc](https://docs.python.org/3/library/os.html#os.DirEntry) for all methods and attributes of the object

* * *

## Datetime

-   `datetime.today()` print a date

* * *

\#code/python/modules
