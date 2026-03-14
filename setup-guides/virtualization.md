# Setting up Virtual Machines on Fedora Linux
* This guide will teach you how to set up virtual machines on Fedora linux

  |[Home](https://github.com/katsumi-neko/fedora-guide-docs)|
|---|

## System Requirements
* You will need at least 600mb of disk space and 256mb of RAM per virtual machine.
* It is recommended you use a CPU that supports virtualization, which most CPUs do. You may have to enable CPU virtualization in your BIOS (Check your manufacturers guide for details)
* You can check if your CPU is supported by running the following command:
```
grep -E '^flags.*(vmx|svm)' /proc/cpuinfo
```
If this command returns nothing, your CPU isn't supported. You can still run virtual machines, but they will be software virtualized, making performance much worse. 

## Installation
* First, install the packages for Virtualization
```
sudo dnf group install --with-optional virtualization
```
* After the packages are installed, enable the service
```
sudo systemctl enable --now libvirtd
```
* If you do not want to enter your root password every time you open up Virtual Machine Manager, add your user to the `libvirt` group
```
sudo usermod -aG libvirt $USER
```

## Creating and Using Virtual Machines
* It is far easier to use the Virtual Machine Manager GUI application to manage your virtual machines. This is installed in the steps above
* If you prefer a command line based method of managing virtual machines, [this guide](https://docs.fedoraproject.org/en-US/quick-docs/virtualization-getting-started/#_creating_virtual_machines/) will help you do this. 
