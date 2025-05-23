```
lsblk -o NAME,UUID,MOUNTPOIN
```
## lsmod

## dmesg
```
dmesg | grep -i memory
```

## Memory
```
grep MemTotal /proc/meminfo || free -g
```
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

## cpu
```
lscpu
```

## دما
```
sudo apt install hddtemp lm-sensors
sensors
sudo hddtemp /dev/sda   


sudo apt-get install hardinfo
```
