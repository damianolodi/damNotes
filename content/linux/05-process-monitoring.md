---
title: "Process Monitoring"
draft: false
arguments: ["System Manager",
            "Process Definition",
            "Process Termination"]
weight: 05
---

A process is the instance of a program which is ebeing executed by the CPU. It contains the program code and its activity.

Important parameters are: **PID** (Process ID), **priority**, occupied **memory**, used **CPU percentage**

- `top` &rarr; call the system manager to visualize all the processes

    - `top -M` &rarr; use the best measurment unit in the column of the allocated memory of each process

    - \> `P`, \> `M` &rarr; order processes for CPU percentage or memory percentage

    - \> `k` + type _PID_ + signal &rarr; kill the associated process. _Signal_ can be `15` (sigterm) for close request, or `9` (sigkill) for forcing the closure

- `free -m` &rarr; monitor memory status. `-m` display in megabytes

- `ps` &rarr; display processes active in the current bash session

- `htop` &rarr; like `top` but better look. It has to be installed

- `pgrep` + _name_ &rarr; display all the PIDs of the processes containing _name_

- `ps aux | grep` + _name_ &rarr; display all processes (and their specs) containing _name_

- `kill` + PID &rarr; try to close the process with the _sigterm_ signal.

    - `kill -9` + PID &rarr; use _sigkill_ instead

* * *

**In Linux everything is a file.** In the `/proc/` directory, there is a directory for _every_ process that is in execution (named as the PID of the process). Inside there are various other files and directories used by the OS to monitor the process. For example, in the `cmdline` file there is the bash command that started the process.