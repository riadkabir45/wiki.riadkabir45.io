# How to create debian/ubuntu rootfs
Fedora rootfs are hell minimal.
Not even importand packages like passwd ships with default dependencies.
Most packages are sub-devided into lot of sections


## Initialize the rootfs
Debian/ubuntu can deployed in most linux system as dnf is avaialable in mosts.
But configuring dnf to generate a rootfs is little hussle.
After installing dnf
> /etc/yum.conf:
```
releasever=VERSION
```
> /etc/yum.repos.d:
```
	[fedora]
2	name=Fedora $releasever - $basearch
4	#BD baseurl=http://mirror.xeonbd.com/remi/fedora/linux/releases/$releasever/Everything/$basearch/os/
5	baseurl=http://archives.fedoraproject.org/pub/archive/fedora/linux/releases/$releasever/Everything/$basearch/os/
9	gpgcheck=0
```
GpgCheck is necessary as false here as host might not have fedora keyrings


After that just
```
dnf --installroot ABSOLUTE_PATH_TO_FOLDER install dnf
```

## Pre-Boot
Packages that are needed to boot and connect properly
```
kernel NetworkManager sudo NetworkManager-wifi passwd TEXT_EDITOR
```

Configure timezone and locales
```
ln -sf /usr/share/zoneinfo/Region/City /etc/localtime
locale-gen
```

Edit hosts, set hostname and add user
```
vim /etc/hosts
hostnamectl hostname HOST_NAME
useradd -m -g wheel -G wheel USER
passwd USER
```
