# Installing Nvidia Drivers & Codecs

|[Back]([https://github.com/](https://github.com/katsumi-neko/fedora-guide-docs/blob/main/Initial%20Setup.md)[Home](https://github.com/katsumi-neko/fedora-guide-docs)|
|---|---|

## Nvidia GPU Drivers
`sudo dnf install akmod-nvidia xorg-x11-drv-nvidia-cuda xorg-x11-drv-nvidia-cuda-libs libva-nvidia-driver libva-utils vdpauinfo vulkan`

## Nvidia multimedia codecs
`sudo dnf install libva-nvidia-driver.{i686,x86_64} libva-utils vdpauinfo`

`sudo dnf install nvidia-query-resource-opengl nvidia-texture-tools`

`sudo dnf install freeglut-devel libX11-devel libXi-devel libXmu-devel make mesa-libGLU-devel freeimage-devel glfw`

## Important Notice!!
* It is critical to wait at least 5 minutes after installing Nvidia drivers, as well as after every system update, to ensure that the kernel modules get build (as this runs in the background). Rebooting early will result in a black screen!!
