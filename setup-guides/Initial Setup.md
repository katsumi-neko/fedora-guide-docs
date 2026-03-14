# Post Installation Setup Guide

|[Home](https://github.com/katsumi-neko/fedora-guide-docs)|
|---|

## DNF Configuration (optional)
* This is a set of quality of life options for your DNF configuration to make life easier.
Edit your `/etc/dnf/dnf.conf` to look like this.
```
[main]
max_parallel_downloads=10 
# Sets the amount of simultaneous downloads to 10
defaultyes=True
# Sets default behavior to Yes when pressing Enter on a confirmation
```

## (Important) Update your system
* It is critical to update your system before installing any packages in order to ensure stability and that you get the latest version of all packages.
```
sudo dnf update
```

## Install the RPM Fusion Repositories
* These repositories are necessary to be able to install extra proprietary software and some free software that isn't included in the main repositories (such as Nvidia drivers, Discord, Steam, etc)
````sudo dnf install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm````

## Installing Nvidia GPU Drivers
* Pick the option for whichever GPU you have. If you have multiple, follow the guide for each one. 

|[Nvidia Driver Installation](https://github.com/katsumi-neko/fedora-guide-docs/blob/main/setup-guides/Nvidia.md)|
|---|

## Installing Multimedia Codecs
|[Multimedia Codec Installation](https://github.com/katsumi-neko/fedora-guide-docs/blob/main/setup-guides/codecs.md)|
|---|

## Replace Fedora Flatpak with Flathub
* By default Fedora ships their own Flatpak repository, but this does not include everything within the Flathub. Additionally, packages on Fedora flatpak may have issues that Flathub flatpaks do not have. It is commonly recommended to replace the Fedora flatpak repository with the one from Flathub. 
````sudo flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo````

````flatpak remote-modify --no-filter --enable flathub````

````flatpak remote-delete fedora```
