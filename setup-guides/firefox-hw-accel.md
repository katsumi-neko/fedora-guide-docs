# Setting up hardware accelerated video decoding in Firefox on Nvidia GPUs 
This guide uses information from the [nvidia-vaapi-driver](https://github.com/elFarto/nvidia-vaapi-driver) repository.
* You must have the Nvidia drivers and codecs (Can be found in the [initial setup guide.](https://github.com/katsumi-neko/fedora-guide-docs/blob/main/setup-guides/Initial%20Setup.md)

<sup><sub>I may add Chromium based browsers later on</sub></sup>

|[Home](https://github.com/katsumi-neko/fedora-guide-docs)|
|---|

## Browser configuration
* In firefox, enter `about:config` in the address bar and press enter. From there, you will set the following values:

`media.ffmpeg.vaapi.enabled` = `true` | Required

`media.hardware-video-decoding.force-enabled` = `true` | Required

`media.rdd-ffmpeg.enabled` = `true` | Required

`gfx.x11-egl.force-enabled` = `true` | Required

`media.av1.enabled` = `false` | **Optional**, disables AV1. Required if your GPU does not support AV1 decoding.

## Environment Variables
In addition to the browser configuration, you will need to enable these environment variables.
* In Fedora KDE Plasma edition, you can can right click Firefox in the Application menu, click `Edit application`, and add these to the `Environment Variables` line

`MOZ_DISABLE_RDD_SANDBOX=1 LIBVA_DRIVER_NAME=nvidia`
