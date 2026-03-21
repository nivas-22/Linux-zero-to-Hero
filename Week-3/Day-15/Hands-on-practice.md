# Linux Complete Guide – Day 15 Exercises (Hands-On Practice)

## Exercise 1: View Network Configuration

```bash
ip addr
ip link
ip route
cat /etc/resolv.conf
```

---
## Exercise 2: Extract Specific Information

```bash
# Find your IP address
ip addr show | grep "inet" | grep -v 127.0.0.1

# Find your default gateway
ip route | grep default

# Find your MAC address
ip link show eth0 | grep ether
```
---
## Exercise 3: Test Connectivity

```bash
ping -c 2 127.0.0.1   # Loopback

ping -c 2 $(ip route | grep default | awk '{ print $3 }')   # Gateway

ping -c 2 8.8.8.8   # Internet

ping -c 2 google.com   # DNS
```
---
## Exercise 4: Check Interface Statistics

```bash
ip -s link show eth0
```
---
