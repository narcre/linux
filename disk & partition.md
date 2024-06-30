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


apt-get install ntfs-3g
sudo mount -t ntfs /dev/sdb1 /mnt/ntfs1



```
```


sudo vgcreate foo /dev/sda1
sudo lvcreate --name bar --size 5g foo
sudo mkfs -t ext4 /dev/mapper/hdd--vg-hdd--lv1
vgdisplay
lvdisplay
blkid /dev/vg00/vol_projects
mkdir /home/projects

nano etc/fstab
UUID=b85df913-580f-461c-844f-546d8cde4646 /home/projects	ext4 defaults 0 0
mount -a
```
##### [how-to-manage-logical-volumes](https://ubuntu.com/server/docs/how-to-manage-logical-volumes)
##### [manage-and-create-lvm-parition-using-vgcreate-lvcreate-and-lvextend](https://www.tecmint.com/manage-and-create-lvm-parition-using-vgcreate-lvcreate-and-lvextend/)
