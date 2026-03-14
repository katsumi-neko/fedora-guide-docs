# Installing Nvidia GPU Drivers & Codecs
* You must have the RPM Fusion repositories installed in order to install the Nvidia drivers.

|[Back](https://github.com/katsumi-neko/fedora-guide-docs/blob/main/setup-guides/Initial%20Setup.md)|[Home](https://github.com/katsumi-neko/fedora-guide-docs)|
|---|---|

## Nvidia GPU Drivers (16xx or newer)
```
sudo dnf install akmod-nvidia xorg-x11-drv-nvidia-cuda xorg-x11-drv-nvidia-cuda-libs
```

## Legacy Nvidia GPU Drivers (10xx or older cards)
**STARTING IN FEDORA 44, NOT AVAILABLE IN F43 YET)**
```
sudo dnf install xorg-x11-drv-nvidia-580xx akmod-nvidia-580xx xorg-x11-drv-nvidia-580xx-cuda
```

## Important Notice!!
* It is critical to wait at least 5 minutes after installing Nvidia drivers, as well as after every system update, to ensure that the kernel modules get build (as this runs in the background). Rebooting early will result in a black screen!!
