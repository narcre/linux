## info
```
lsblk
df -H
df -hT | grep sda3

sudo pvs

fdisk -lu /dev/vdb
fdisl -l

```


## Extend Size
```
 sudo lvextend -l +100%FREE /dev/mapper/ubuntu--vg-ubuntu--lv

sudo lvextend -r -l +100%FREE /dev/mapper/ubuntu--vg-ubuntu--lv

sudo lvextend -r -L +20G /dev/name-of-volume-group/root

sudo resize2fs /dev/name-of-volume-group/root

```

## mount & unmount
```
mount /dev/vdb1 /mnt

mount | grep "/dev/vdb"
umount /dev/vdb1

```
