# Initial Setup Guide

|[Return]([https://github.com/](https://github.com/katsumi-neko/fedora-setup))|
|---|

## DNF Configuration (optional)
* This is a set of quality of life options for your DNF configuration to make life easier.
Edit your `/etc/dnf/dnf.conf and add the following options BELOW [main]
```
max_parallel_downloads=10 
# Sets the amount of simultaneous downloads to 10
defaultyes=True
# Sets default behavior to Yes when pressing Enter on a confirmation
```
