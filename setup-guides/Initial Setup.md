# Post Installation Setup Guide
This guide will help you set up your Fedora installation for general use, please read everything in a section before just running commands.
Items tagged `(Optional)` are personal suggestions/preferences for a better experience, these are not required. 

|[Home](https://github.com/katsumi-neko/fedora-guide-docs)|
|---|


## (Important) Update your system
* It is critical to update your system before installing any packages in order to ensure stability and that you get the latest version of all packages.
```
sudo dnf update
```

## Install the RPM Fusion Repositories
* These repositories are necessary to be able to install extra proprietary software and some free software that isn't included in the main repositories (such as Nvidia drivers, Discord, Steam, etc)
```
sudo dnf install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
```

## Installing Nvidia GPU Drivers
* Pick the option for whichever GPU you have. If you have multiple, follow the guide for each one. 

|[Nvidia Driver Installation](https://github.com/katsumi-neko/fedora-guide-docs/blob/main/setup-guides/Nvidia.md)|
|---|

## Installing Multimedia Codecs
|[Multimedia Codec Installation](https://github.com/katsumi-neko/fedora-guide-docs/blob/main/setup-guides/codecs.md)|
|---|

## (optional) Replace Fedora Flatpak with Flathub
* By default Fedora ships their own Flatpak repository, but this does not include everything within the Flathub. Additionally, packages on Fedora flatpak may have issues that Flathub flatpaks do not have. It is commonly recommended to replace the Fedora flatpak repository with the one from Flathub.
* Fedora does not ship with any Flatpaks installed by default, if you have installed them, you will need to reinstall them from Flathub before deleting the Fedora flatpak. You can check if you have any flatpaks installed by running `flatpak list`
```
sudo flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```
```
flatpak remote-modify --no-filter --enable flathub
```
```
flatpak remote-delete fedora
```

## (optional) Fix occasional slow bootup
* By default, the service `NetworkManager-wait-online.service` is enabled in Fedora. This service will delay the system booting up until a network connection is established, but it is known to occasionally hang and delay startup. You should only disable this service if you do not have any services that are dependent on an online connection to start. (Out of the box, Fedora does not have any such services)
```
sudo systemctl disable NetworkManager-wait-online.service
```

## Conclusion
It is recommended to reboot your system one more time after completing the initial setup, then your system should be ready to use!

### Sources
Official RPM Fusion configuration guide https://rpmfusion.org/Configuration
Community tutorial to replace Fedora Flatpak with Flathub https://discussion.fedoraproject.org/t/tutorial-how-to-replace-the-fedora-flatpak-repo-with-flathub/44320

