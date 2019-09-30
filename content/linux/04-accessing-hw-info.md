---
title: "Accessing Hardware Info"
draft: false
arguments: ["External Drivers",
            "Network Card",
            "Serial Peripherals"]
weight: 04
---

- `lsblk` &rarr; access all the information about _external drives_ (it menas 'list block devices').

    - in Linux, all external storage devices are stored in `/dev/sd*`. Usualy, first letter (_a_,...) is the name of the disk, followed by a number if more that one partitions are present

- `lsusb` &rarr; lists all USB peripherals (keyboard, mouse, serial ports,...)

- `lspci` &rarr; lists all peripherals attached to the PCI bus

- `cat /proc/cpuinfo` &rarr; contains all info on the mounted CPU

    - `top` &rarr; display statistics on the CPU usage

- `cat /proc/meminfo` &rarr; contains all the info on the installed RAM

    - `free -m` &rarr; display amount of free and occupied memory

* * *

### Network Cards

- `ip addr` (or `ifconfig`, but it is deprecated) &rarr; lists all _network cards_

    - firts diplayed is `lo` (loopback). It is a virtual network card used to assign the ip address for localhost

    - `eth0` is the cabled network card. _inet_ and _inet6_ are the ip address of the local network

- `ip route` &rarr; _list the ip address of the router_ used to connect to external networks

- `host website_name` &rarr; return _ip address and hosting informations_ about the provided website