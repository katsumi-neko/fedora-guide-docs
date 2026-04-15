# Installing Multimedia Codecs
You must have the RPM Fusion repositories installed to install the codecs below. 

|[Back](https://github.com/katsumi-neko/fedora-guide-docs/blob/main/setup-guides/Initial%20Setup.md)|[Home](https://github.com/katsumi-neko/fedora-guide-docs)|
|---|---|

## Universal Extra Codecs
* Swap ffmpeg-free for ffmpeg for better compatibility
```
sudo dnf swap ffmpeg-free ffmpeg --allowerasing
```
* Install other proprietary/restricted codecs needed by many multimedia applications
```
sudo dnf update @multimedia --setopt="install_weak_deps=False" --exclude=PackageKit-gstreamer-plugin
```

## Hardware Accelerated Codecs

### For AMD GPUs ( Fedora 43 and earlier)
* This step is no longer necessary for Fedora 44 and newer. 
* These commands will swap out the FOSS codecs with the restricted ones for better compatibility
```
sudo dnf swap mesa-va-drivers.i686 mesa-va-drivers-freeworld.i686
```
```
sudo dnf swap mesa-va-drivers mesa-va-drivers-freeworld
```

### For Nvidia GPUs
* Extra codecs for Nvidia GPUs, will also install the VA-API compatibility driver for VA-API hardware decoding. 
```
sudo dnf install libva-nvidia-driver.{i686,x86_64} libva-utils vdpauinfo nvidia-query-resource-opengl nvidia-texture-tools freeglut-devel libX11-devel libXi-devel libXmu-devel make mesa-libGLU-devel freeimage-devel glfw
```

### For Intel GPUs
* For Skylake and **newer** processors or Intel Arc GPUs
```
sudo dnf install libva-intel-driver
```

* For **before** Skylake processors
```
sudo dnf install intel-media-driver
```

Sources:
* Official RPM Fusion guide
https://rpmfusion.org/Howto/Multimedia
* Community Discord server Guides channel
https://discord.gg/fedora
