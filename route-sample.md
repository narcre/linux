# SERVER
```
#ens4             UP             192.168.100.253
sudo sysctl -w net.ipv4.ip_forward=1
sudo nano /etc/sysctl.conf
net.ipv4.ip_forward=1
sudo sysctl -p
ip route
sudo iptables -t nat -A POSTROUTING -s 192.168.100.0/24 -o ens3 -j MASQUERADE
sudo iptables -A FORWARD -i ens4 -o ens3 -j ACCEPT
sudo iptables -A FORWARD -i ens3 -o ens4 -m state --state RELATED,ESTABLISHED -j ACCEPT
echo "nameserver 8.8.8.8" | sudo tee /etc/resolv.conf
sudo ip route del default via 192.168.100.1
ip route | grep default
sudo iptables -L -v -n
sudo iptables -P FORWARD ACCEPT
sudo sysctl -w net.ipv4.conf.all.rp_filter=0
sudo sysctl -w net.ipv4.conf.default.rp_filter=0
sudo sysctl -w net.ipv4.conf.ens3.rp_filter=0
sudo sysctl -w net.ipv4.conf.ens4.rp_filter=0
sudo tcpdump -i ens3 icmp
```

# CLIENT
```
#ens3             UP             192.168.100.176
ip route
sudo ip route add default via 192.168.100.253
echo "nameserver 8.8.8.8" | sudo tee /etc/resolv.conf
sudo ip route del default via 192.168.100.1
sudo ip route del 1.1.1.1 via 192.168.100.1
```
