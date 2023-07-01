## apt
```
apt list -a --installed
sudo apt --fix-broken install
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
/etc/apt/apt.conf.d/proxy.conf


Acquire::http::Proxy "http://yourproxyaddress:proxyport";

```
