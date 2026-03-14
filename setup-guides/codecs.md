# Installing Multimedia Codecs
* RPM Fusion repositories are required for this

|[Back](https://github.com/katsumi-neko/fedora-guide-docs/blob/main/setup-guides/Initial%20Setup.md)|[Home](https://github.com/katsumi-neko/fedora-guide-docs)|
|---|---|

## AMD Specific Codecs
```
sudo dnf swap mesa-va-drivers.i686 mesa-va-drivers-freeworld.i686
```
```
sudo dnf swap mesa-va-drivers mesa-va-drivers-freeworld
```

## Nvidia Specific Codecs
```
sudo dnf install libva-nvidia-driver.{i686,x86_64} libva-utils vdpauinfo nvidia-query-resource-opengl nvidia-texture-tools freeglut-devel libX11-devel libXi-devel libXmu-devel make mesa-libGLU-devel freeimage-devel glfw
```

## Intel Specific Codecs
* For Skylake and **newer** processors or Intel Arc GPUs
```
sudo dnf install libva-intel-driver
```

* For **before** Skylake processors
```
sudo dnf install libva-intel-driver
```
