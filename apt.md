## apt
```
apt list -a --installed
```

## insecute repo add
```
vim /etc/apt/sources.list

deb http://security.ubuntu.com/ubuntu bionic-security main universe

apt-get update --allow-insecure-repositories
```
## proxy
```
sudo nano /etc/apt/apt.conf
Acquire::http::Proxy "http://yourproxyaddress:proxyport";

```
