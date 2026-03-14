# Installing Nvidia GPU Drivers & Codecs

|[Back](https://github.com/katsumi-neko/fedora-guide-docs/blob/main/Initial%20Setup.md)|[Home](https://github.com/katsumi-neko/fedora-guide-docs)|
|---|---|

## Warning:
* Nvidia has dropped support for 10xx and older cards starting with the 590 driver series (in Fedora 44 and newer), please do not install these drivers if you have an unsupported card.

## Nvidia GPU Drivers (16xx or newer)
```
sudo dnf install akmod-nvidia xorg-x11-drv-nvidia-cuda xorg-x11-drv-nvidia-cuda-libs
```

**STARTING IN FEDORA 44, NOT AVAILABLE IN F43 YET)
## Legacy Nvidia GPU Drivers (10xx or older cards)
```
sudo dnf install xorg-x11-drv-nvidia-580xx akmod-nvidia-580xx xorg-x11-drv-nvidia-580xx-cuda
```

## Nvidia multimedia codecs
```
sudo dnf install libva-nvidia-driver.{i686,x86_64} libva-utils vdpauinfo nvidia-query-resource-opengl nvidia-texture-tools freeglut-devel libX11-devel libXi-devel libXmu-devel make mesa-libGLU-devel freeimage-devel glfw
```

## Important Notice!!
* It is critical to wait at least 5 minutes after installing Nvidia drivers, as well as after every system update, to ensure that the kernel modules get build (as this runs in the background). Rebooting early will result in a black screen!!
