---
title: iptables
---

#### list rules with line numbers
    sudo iptables --list --line-numbers

#### delete a rule with number
    sudo iptables -D INPUT <number>

#### add an input rule
    sudo iptables -A INPUT -p tcp --dport 25 -j ACCEPT

#### only allow communication when connected to VPN
```
iptables config to prevent communication unless connected to a VPN.
<sxh>
#!/bin/sh

IPT="/sbin/iptables"

# Allow loopback device
$IPT -A INPUT -i lo -j ACCEPT
$IPT -A OUTPUT -o lo -j ACCEPT

# Allow all local traffic.
$IPT -A INPUT -s 192.168.81.0/24 -j ACCEPT
$IPT -A OUTPUT -d 192.168.81.0/24 -j ACCEPT
$IPT -A INPUT -s 10.0.81.0/24 -j ACCEPT
$IPT -A OUTPUT -d 10.0.81.0/24 -j ACCEPT

# Allow VPN establishment
$IPT -A OUTPUT -p udp --dport 1194 -j ACCEPT
$IPT -A INPUT -p udp --sport 1194 -j ACCEPT

# Accept all TUN connections (tun = VPN tunnel)
$IPT -A OUTPUT -o tun+ -j ACCEPT
$IPT -A INPUT -i tun+ -j ACCEPT

# Set default policies to drop all communication unless specifically allowed
$IPT -P INPUT DROP
$IPT -P OUTPUT DROP
$IPT -P FORWARD DROP
```
