# How to create debian/ubuntu rootfs
Debian rootfs is generally better than ubuntu as ubuntu dependencies are lot worse.
Any display package pulls gnome which in term pulls snap which is kinda shit.


## Initialize the rootfs
Debian/ubuntu can easily deployed in most linux system as debootstrap is available in most.
The command is simply
```
debootstrap VERSION_CODE_NAME FOLDER
```

After that, make sure to enable extra repos
> /etc/apt/source.list[debian]:
```
deb https://deb.debian.org/debian bullseye main contrib non-free
```

## Pre-Boot
Packages that are needed to boot and connect properly
```
inux-image-generic firmware-linux network-manager sudo locales firmware-YOUR_BRAND TEXT_EDITOR
```

Configure timezone and locales
```
dpkg-reconfigure tzdata
dpkg-reconfigure locales
```

Edit hosts, set hostname and add user
```
vim /etc/hosts
hostnamectl set-hostname HOST_NAME
useradd -m -g wheel -G wheel USER
passwd USER
```
