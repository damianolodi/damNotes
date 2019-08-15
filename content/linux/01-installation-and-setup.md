
# Installation and Setup

## Ubuntu Setup on VM
1. Install linux guest addition to run the VM more stabily and with better performance (right screen resolution, less lag,...)
    - *Devices > Insert Guest Addition CD Image* -> a VBoxAddition should appear on the desktop
    - right click on *VBoxLinuxAddition.run > properties* and look if it is executable
    - open the *VBoxAddition...* > right click > *Open in Terminal* > `sudo ./VBoxLinuxAdditions.run`
    - reboot the system

## Customizing Linux
One wants to dowload some themes to customize the look of the GUI. The GTK is the theming engine used by UNITY (desktop environment), which control how things look (color when item is selected,...).

