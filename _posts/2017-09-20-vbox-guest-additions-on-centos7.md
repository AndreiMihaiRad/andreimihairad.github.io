---
layout: post
title: VirtualBox Guest Additons on Centos7
date:   2017-09-20 11:37:35 +0100
categories: devops
---

**This is guide, howto install Oracle VirtualBox Guest Additions on, CentOS and Red Hat (RHEL). This guide should work with Fedora 2, CentOS 7/6**

## Install Steps

1. Change root user
```bash
sudo su -
```


2. Make sure that you are running latest kernel
```bash
yum update kernel*
reboot
```


3. Mount VirtualBox Guest Additions.
  * Click Devices > Install Guest Additions… on VirtualBox
  * ![](/assets/post_imgs/virtualbox-install-guest-additions.png)
  ```bash
    #Mount VirtualBox Guest Additions device
    mkdir /media/VirtualBoxGuestAdditions
    mount -r /dev/cdrom /media/VirtualBoxGuestAdditions
  ```


4. Install following packages
```bash
## Fedora, CentOS/RHEL 7/6/5 ##
yum install gcc kernel-devel kernel-headers dkms make bzip2 perl
```


5. Add KERN_DIR environment variable
```bash
## Current running kernel on Fedora, CentOS 7/6 and Red Hat (RHEL) 7/6 ##
KERN_DIR=/usr/src/kernels/`uname -r`
## Export KERN_DIR ##
export KERN_DIR
```


6. Install Guest Additions
```bash
cd /media/VirtualBoxGuestAdditions
./VBoxLinuxAdditions.run
```


7. Reboot guest system
```bash
reboot
```
