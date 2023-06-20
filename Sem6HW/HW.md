Tlyuxt 1.
KoHour netplan:
network:
version: 2
renderer: networkd
ethernets:
enp@s3:
dhcp4: no
addresses: [192.168.0.8/24]
routes:
- to: default
via: 192.168.0.254
nameservers:
addresses:
- 8.8.8.8
- 1.1.1.1
KomaHaa ip:
sudo ip addr add 192.168.0.9/255.255.255.@ broadcast 192.168.0.255
dev enp@s3
ping ya.ru

Tlyuxt 2.

iptables -A INPUT -i lo -j ACCEPT

iptables -A INPUT -p TCP --dport 22 -j ACCEPT

iptables -A INPUT -p TCP --dport 8@ -j ACCEPT

iptables -A INPUT -p TCP --dport 443 -j ACCEPT

iptables -A INPUT -m state --state ESTABLISHED, RELATED -j ACCEPT
iptables -P INPUT DROP

Tlyuxt 3.
iptables -I INPUT -s 3.4.5.6 -j DROP
Tyuxt 4.

iptables -t nat -I PREROUTING -p tcp --dport 8090 -j REDIRECT
--to-port 88

Tlyuxt 5.
iptables -I INPUT -p TCP --dport 22 -j DROP

iptables -I INPUT -p TCP --dport 22 -s 192.168.0.0/24 -j ACCEPT