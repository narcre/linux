# folder access
```
mkdir /disk
sudo groupadd diskaccess
sudo usermod -aG diskaccess a
sudo chown :diskaccess /disk
#read/write
sudo chmod 770 /disk
#read only
sudo chmod 750 /disk
```

# sample senario
```
before:

vda                       252:0    0   25G  0 disk 
├─vda1                    252:1    0    1M  0 part 
├─vda2                    252:2    0    2G  0 part /boot
└─vda3                    252:3    0   23G  0 part 
  └─ubuntu--vg-ubuntu--lv 253:0    0   23G  0 lvm

df -h
Filesystem                         Size  Used Avail Use% Mounted on
tmpfs                              392M  1.4M  390M   1% /run
/dev/mapper/ubuntu--vg-ubuntu--lv   23G   17G  5.1G  77% /


after:

vda                       252:0    0   25G  0 disk 
├─vda1                    252:1    0    1M  0 part 
├─vda2                    252:2    0    2G  0 part /boot
└─vda3                    252:3    0   23G  0 part 
  └─ubuntu--vg-ubuntu--lv 253:0    0   23G  0 lvm  /
vdb                       252:16   0   20G  0 disk 




parted /dev/vdb -- mklabel gpt
parted /dev/vdb -- mkpart primary 0% 100%
pvcreate /dev/vdb1
vgextend ubuntu-vg /dev/vdb1
lvextend -l +100%FREE /dev/ubuntu-vg/ubuntu-lv
resize2fs /dev/ubuntu-vg/ubuntu-lv

#if using xfs
xfs_growfs /


df -h
Filesystem                         Size  Used Avail Use% Mounted on
tmpfs                              392M  1.4M  390M   1% /run
/dev/mapper/ubuntu--vg-ubuntu--lv   43G   17G   24G  41% /


vda                       252:0    0   25G  0 disk 
├─vda1                    252:1    0    1M  0 part 
├─vda2                    252:2    0    2G  0 part /boot
└─vda3                    252:3    0   23G  0 part 
  └─ubuntu--vg-ubuntu--lv 253:0    0   43G  0 lvm  /
vdb                       252:16   0   20G  0 disk 
└─vdb1                    252:17   0   20G  0 part 
  └─ubuntu--vg-ubuntu--lv 253:0    0   43G  0 lvm  /

```

```
1- reformat disk
2- create /boot to create /boot and /boot/efi for boot 2G
3- create unformatted on all free space of disk to create partition
4- create ubuntu-vg and check partition below of disk number
5- create lvm
```

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
### [CREATE NEW PARTITION](https://gcore.com/learning/how-to-partition-a-disk-in-linux/)
```
sda 300G
sda1 => 70G
for extend :
parted /dev/sda
unit s print free
resizepart 1
-0   ====> extend to end of free space of disk
or
xxxx ===> NEW END

vgextend ubuntu-vg /dev/sda3
```
```
fdisk /dev/sda
n
p
w
```
```
1) pv  create
2) if donot have pv 
3) fdisk  use n
4) for create new partition in existing pv
5) vgextend [existing volume group newpartion]
6) for extend size of volume group
7) extend existing lvm size by
8) lvextend -l +100%FREE -r [lvm name]
9) get lvm name
10) with lvdisplay
```
```
#نکته : درصورتیکه سایز پارتیشن قبلی افزایش داده شود بازهم امکان تغییر vg نیست تازمانیکه پارتیشن جدیدی در pv ایجاد گردد و vg اکستند شود
```
# sample command for tshoot
```
smartctl -a /dev/sdX
lvdisplay /dev/cinder-volumes/volume-<UUID>
iscsiadm -m session
multipath -ll
dmsetup ls --tree
```
