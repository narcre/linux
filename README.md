## OS 
```
uname -m
uname -a
lsb_release -a
```

## Hard ware
```
sudo lshw 
sudo lshw –short
sudo lshw –html > lshw-output.html
sudo lshw –xml >lshw-output.xml


hwinfo
hwinfo –short


lspci
lsscsi
lsusb
```

## Disk
```
lsblk
df -H
```

## File & Directory
```
du -sh
du -sh *|sort -h
du -sh [fileName]   ##capacity of file

date -d "@$(stat -c '%Y' a.out)" '+%a %b %d %T %Z %Y'
stat -c '%y' filename
ls -lrt --block-size=GB 

```

## cpu
```
lscpu
```
