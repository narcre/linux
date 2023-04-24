##### flush dns

###### Ubuntu
```
sudo apt install dnsutils
sudo resolvectl flush-caches 

sudo systemd-resolve --flush-caches
sudo systemctl restart systemd-resolved
```

###### windows

```
ipconfig /flushdns
```
