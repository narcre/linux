## Create:
```
sudo adduser newuser
-- create user
useradd --no-create-home --shell /bin/false prometheus-libvirt-exporter
```



## usermod:
```
sudo usermod -aG wheel <user>
sudo gpasswd -a <user> wheel
sudo usermod -aG sudo esmaeili
```



### chown
```
sudo chown -R esmaeili:esmaeili *
```
# Disable the Password for the Sudo Command
```
sudo visudo
username ALL=(ALL) NOPASSWD: ALL
%reza ALL=(ALL) NOPASSWD:ALL
```
### permistion
```
deluser b sudo
groupadd diskaccess
usermod -aG diskaccess username
chown :diskaccess /disk
chmod 770 /disk
#read only
chmod 750 /disk
```
# delete user
```
sudo deluser b sudo
groups b
```
