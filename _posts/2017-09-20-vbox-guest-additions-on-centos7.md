---
layout: post
title: VirtualBox Guest Additons on Centos7
date:   2017-09-17 11:37:35 +0100
categories: devops
---

**This is guide, howto install Oracle VirtualBox Guest Additions on, CentOS and Red Hat (RHEL). This guide should work with Fedora 26/25/24/23/22/21/20/19/18/17/16, CentOS 7.3/6.9/5.11, Red Hat (RHEL) 7.3/6.9/5.11.**

#Install VirtualBox Guest Additions on CentOS and Red Hat (RHEL)
1. Change root user
```bash
sudo su -
```

2. Make sure that you are running latest kernel
```
yum update kernel*

reboot
```

3. Mount VirtualBox Guest Additions
Click Devices > Install Guest Additions… on VirtualBox
[image]

```
#Mount VirtualBox Guest Additions device
mkdir /media/VirtualBoxGuestAdditions
mount -r /dev/cdrom /media/VirtualBoxGuestAdditions
```

4. Install following packages
**Add epel repo**
**Install following packages**

```
## Fedora 21/20/19/18/17/16/15/14/13/12, CentOS/RHEL 7/6/5 ##
yum install gcc kernel-devel kernel-headers dkms make bzip2 perl
```

5. Add KERN_DIR environment variable
```
## Current running kernel on Fedora, CentOS 7/6 and Red Hat (RHEL) 7/6 ##
KERN_DIR=/usr/src/kernels/`uname -r`

## Current running kernel on CentOS 5 and Red Hat (RHEL) 5 ##
KERN_DIR=/usr/src/kernels/`uname -r`-`uname -m`

## Fedora example ##
KERN_DIR=/usr/src/kernels/2.6.33.5-124.fc13.i686

## CentOS and Red Hat (RHEL) example ##
KERN_DIR=/usr/src/kernels/2.6.18-194.11.1.el5-x86_64

## Export KERN_DIR ##
export KERN_DIR
```

6. Install Guest Additions
```
cd /media/VirtualBoxGuestAdditions

# 32-bit and 64-bit systems run following
./VBoxLinuxAdditions.run
```

7. Reboot guest system

```
reboot
```
