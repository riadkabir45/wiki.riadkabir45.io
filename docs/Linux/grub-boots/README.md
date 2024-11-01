# Grub bootloaders
## Linux
```
menuentry 'Linux OS' {
search --set=root --file /ID_FILE
probe -u $root --set=rootUUID
linux /vmlinuz quiet rw root=UUID=$rootUUID
initrd /initrd.img
}
```
## Android-x86
```
menuentry 'Android' {
set android=/FOLDER_NAME
search --set=root --file $android/kernel 
linux $android/kernel quiet root=/dev/ram0 androidboot.selinux=permissive SRC=$android
initrd $android/initrd.img
}
```
