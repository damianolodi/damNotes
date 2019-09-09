---
title: "VirtualBox"
draft: false
arguments: ["Creating VM", "VirtualBox Guest Additions"]
weight: 99
---

### Create New Virtual Machine

1.  Click _new_ and insert name for the OS. It should find the corresponding OS type. If not, select the right type and version;

2.  assign RAM quantity (2GB for 8GB machines should be ok)

3.  _Create new virtual HD_ > _VDI_ > _Dynamically allocated_

4.  Select HD size (15GB should be ok)

5.  Select the machine and go to _Settings_

    -   _General_ > _Advanced_ tab > select _Bidirectional_ in _Shared Clipboard_ [can copy/paste between VM and base OS]
    -   _System_ can change the assigned RAM and can change the chipset to ICH9 (experimental, but can have better performance)
    -   _Processor_ > assign the number of core to the VM. Select _Enable PAE/NX_ to improve performance on newer machines
    -   _Display_ > select video memory to 128MB. Enable 3D acceleration if needed
    -   _Network_ > select _Bridged adapter_. In this way, the network card of the VM is directly connected to the real one and both the systems are visible from the network. In the default _NAT_ option, the IP address has a different class from the one of the real machine, and it can be "invisible" from the network
    -   _Ports_ > can configure USB and serial ports
    -   _Shared Folders_ > create folder to "communicate" with the VM, sharing files if needed. Select _Auto Mount_

6.  Start the VM. In the new window, select in the bottom left corner the CD icon and then select the ISO of the OS to virtualize

7.  Install following the directions given by the OS

8.  When restarting, click again on the CD icon and select _Remove disk from virtual drive_, so that the VM will boot from the HD and not from the ISO

* * *

### Installing VirtualBox Guest Additions

When the VM is running, click _Devices_ > _Insert Guest Additions CD Image_. A virtual CD should apper on the desktop and Linux should try to execute that. At the end, restart the VM and expell the virutal CD (from _Devices_ > _Optical Device_ > _Remove ..._).
