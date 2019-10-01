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

    - `eth0` (on Debian) is the cabled network card. _inet_ and _inet6_ are the ip address of the local network

- `ip route` &rarr; _list the ip address of the router_ used to connect to external networks

- `host website_name` &rarr; return _ip address and hosting informations_ about the provided website

- `ip link set interface_name down` &rarr; turn off the ntetwork card specified in *interface_name* (e.g. `eth0`). Use `up` to reactivate it

- `ip address change new_ip_address dev interface_name` &rarr; _change the ip address_ of the specified interface. This modification is temporary (until next reboot of the machine)

    - the ip address can be modified permanently changing the configuration inside a directory in `/etc/` (the specific file depends on the distro)