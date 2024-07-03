## Create:
```
sudo adduser newuser
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
```
