# 🐧 Day 15: Linux Networking Basics  
### 📡 IP Addresses, Interfaces, and Connectivity

---

## 📘 Overview

This document covers fundamental Linux networking concepts and commonly used commands for managing and troubleshooting network interfaces, IP addresses, routing, and connectivity.

---

# 🌐 Networking Fundamentals

### 🔑 Key Concepts

- **IP Address**: Unique identifier for a device on a network  
  👉 Example: `192.168.1.100`

- **MAC Address**: Physical hardware address  
  👉 Example: `08:00:27:12:34:56`

- **Network Interface**: Connection point of a system  
  👉 Examples: `eth0`, `ens33`, `wlan0`

- **Gateway**: Router that connects local network to other networks

- **Subnet Mask**: Defines network size  
  👉 Example: `255.255.255.0` or `/24`

- **DNS**: Converts domain names into IP addresses

---

# 🔌 Common Network Interfaces

| Interface | Description |
|----------|------------|
| `lo` | Loopback interface (127.0.0.1) |
| `eth0` | First Ethernet interface (legacy naming) |
| `ens33`, `enp0s3` | Predictable Ethernet naming |
| `wlan0`, `wlp2s0` | Wireless interfaces |
| `docker0` | Docker bridge network |
| `virbr0` | Virtual bridge (libvirt) |

---

# 🧰 ifconfig (Legacy Tool)

⚠️ Deprecated but still widely used.

### 📦 Installation (if missing)

```bash
sudo apt install net-tools      # Ubuntu/Debian
sudo yum install net-tools      # CentOS/RHEL
```
---

| Command               | Description             |
| --------------------- | ----------------------- |
| `ifconfig`            | Show active interfaces  |
| `ifconfig -a`         | Show all interfaces     |
| `ifconfig IFACE`      | Show specific interface |
| `ifconfig IFACE up`   | Bring interface up      |
| `ifconfig IFACE down` | Bring interface down    |

---
```bash
# Show all active interfaces
ifconfig

# Show all interfaces
ifconfig -a

# Bring interface down/up
sudo ifconfig eth0 down
sudo ifconfig eth0 up

# Assign IP address (temporary)
sudo ifconfig eth0 192.168.1.50 netmask 255.255.255.0
```
---

🚀 ip addr (Modern Tool)

Modern replacement for ifconfig.

| Command            | Description           |
| ------------------ | --------------------- |
| `ip addr` / `ip a` | Show all IP addresses |
| `ip -4 addr`       | Show IPv4 only        |
| `ip -6 addr`       | Show IPv6 only        |
| `ip addr add`      | Add IP address        |
| `ip addr del`      | Delete IP address     |
| `ip addr flush`    | Remove all IPs        |

---

# Show all IPs
ip addr
ip a

# Show specific interface
ip addr show dev eth0

# Add IP address
sudo ip addr add 192.168.1.50/24 dev eth0

# Add secondary IP
sudo ip addr add 192.168.1.51/24 dev eth0

# Delete IP address
sudo ip addr del 192.168.1.50/24 dev eth0

---

🔗 ip link (Interface Control)

Used for managing network interfaces at link layer.

| Command                   | Description              |
| ------------------------- | ------------------------ |
| `ip link`                 | Show interfaces          |
| `ip link set dev up/down` | Enable/disable interface |
| `ip link set mtu`         | Set MTU                  |
| `ip link set address`     | Change MAC address       |

---

# Show interfaces
ip link

# Show stats
ip -s link

# Bring interface up/down
sudo ip link set eth0 down
sudo ip link set eth0 up

# Change MTU
sudo ip link set eth0 mtu 9000

# Change MAC address
sudo ip link set eth0 down
sudo ip link set eth0 address 00:11:22:33:44:55
sudo ip link set eth0 up

---
🧭 ip route (Routing Table)

| Command             | Description                 |
| ------------------- | --------------------------- |
| `ip route` / `ip r` | Show routing table          |
| `ip route add`      | Add route                   |
| `ip route del`      | Delete route                |
| `ip route get`      | Show route to a destination |
| `ip route flush`    | Clear routing cache         |


---

# Show routing table
ip route

# Get route to a destination
ip route get 8.8.8.8

# Add static route
sudo ip route add 10.0.0.0/8 via 192.168.1.254

# Delete route
sudo ip route del 10.0.0.0/8

# Set default gateway
sudo ip route add default via 192.168.1.1

---
📶 ping (Network Connectivity Testing)

| Option        | Description              |
| ------------- | ------------------------ |
| `-c COUNT`    | Number of packets        |
| `-i INTERVAL` | Interval between packets |
| `-W TIMEOUT`  | Timeout                  |
| `-s SIZE`     | Packet size              |
| `-q`          | Quiet output             |
| `-4`          | IPv4 only                |
| `-6`          | IPv6 only                |
| `-I IFACE`    | Use specific interface   |

---

# Basic ping
ping google.com

# Send 4 packets
ping -c 4 google.com

# Faster interval
ping -c 10 -i 0.2 google.com

# Large packet size
ping -c 4 -s 1000 google.com

# Quiet mode
ping -c 4 -q google.com

# Use specific interface
ping -c 4 -I eth0 8.8.8.8

---

✅ Quick Summary

ifconfig → Legacy tool (deprecated)
ip addr → View IP addresses
ip link → Manage interfaces
ip route → Manage routing
ping → Test connectivity

---

🎯 Practice Tips
Use ip a daily instead of ifconfig
Combine ip addr, ip link, and ip route for full diagnostics
Use ping to verify connectivity issues
Always check:
IP configuration
Gateway
DNS resolution

---
