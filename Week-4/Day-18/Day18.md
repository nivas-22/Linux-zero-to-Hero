# Firewall & Security

**Protecting Your Linux System**

# 🛡️ What is a Firewall?

A firewall is a security system that monitors and controls incoming and outgoing network traffic based on predefined security rules.

---

## 🔄 Workflow

```text
Filter Traffic → Block Threats → Protect
```

### 🧠 Explanation

A firewall acts as a barrier between trusted and untrusted networks by:

- 🔍 Filtering network packets based on rules
- 🚫 Blocking unauthorized or suspicious traffic
- ✅ Allowing legitimate communication to pass through

### 🔐 Key Idea

> A firewall enforces security policies by deciding what traffic is allowed and what should be denied

---

# 🔐 Security Commands — Firewall & Packet Tools

| ⚙️ Command   | 📄 Description              | 🐧 Distro Support        | 📊 Complexity |
|-------------|---------------------------|--------------------------|--------------|
| `iptables`  | Kernel-level firewall rules | All Linux distributions   | 🔴 High       |
| `firewalld` | Dynamic firewall manager    | RHEL / CentOS / Fedora    | 🟡 Medium     |
| `ufw`       | Uncomplicated Firewall      | Ubuntu / Debian           | 🟢 Low        |
| `tcpdump`   | Packet capture tool         | All Linux distributions   | 🟡 Medium     |

---

## 🧠 Notes

- 🔥 **`iptables`** provides low-level, powerful rule configuration but can be complex  
- ⚙️ **`firewalld`** simplifies firewall management with dynamic rule handling  
- 🧩 **`ufw`** offers an easy-to-use interface for beginners  
- 📡 **`tcpdump`** is used to capture and analyze network packets  

---

## 💡 Summary

- Use **`ufw`** for simplicity (especially on Ubuntu/Debian)  
- Use **`firewalld`** for managed dynamic environments  
- Use **`iptables`** for fine-grained, advanced control  
- Use **`tcpdump`** for network debugging and packet analysis  

---

## 🏰 Real-Life Analogy  
### 🛡️ The Castle Security Model

Think of a firewall like the security system of a castle that controls who can enter or leave:

- 🔥 **`iptables`** → Master guard rules *(highly powerful and detailed control)*  
- 🧭 **`firewalld`** → Zone-based security *(organizes access by zones/areas)*  
- 🚪 **`ufw`** → Simple gate controls *(easy-to-use interface for basic rules)*  
- 📹 **`tcpdump`** → Security cameras *(monitors and captures network activity)*  

---

### 🧩 Key Insight

> The firewall acts as the gatekeeper of the network, deciding which traffic is allowed in and which is kept out.

---

### ⚡ Takeaway

🛡️ Strong security comes from **controlling access + monitoring activity + enforcing clear rules**.

---

# 🔥 UFW – Uncomplicated Firewall (Ubuntu)

A quick and stylish guide to managing your firewall with **UFW**.

---

## 📌 🔍 Check Firewall Status

```bash
sudo ufw status verbose
```

---

## ⚠️ 🔐 IMPORTANT: Allow SSH First!

> Prevent locking yourself out of your server.

```bash
sudo ufw allow ssh
sudo ufw allow 22/tcp
```

---

## 🚀 Enable Firewall

```bash
sudo ufw enable
```

---

## 🌐 Allow Common Services

### 🌍 HTTP (Port 80)

```bash
sudo ufw allow http
```

### 🔒 HTTPS (Port 443)

```bash
sudo ufw allow https
```

### ⚙️ Custom Port (e.g., 8080)

```bash
sudo ufw allow 8080/tcp
```

---

## 🧑‍💻 Allow Access from Specific IP

```bash
sudo ufw allow from 192.168.1.100
```

---

## ❌ Deny Specific Port (e.g., Telnet 23)

```bash
sudo ufw deny 23/tcp
```

---

## 🛡️ Set Default Policies

### 🚫 Deny Incoming Traffic

```bash
sudo ufw default deny incoming
```

### ✅ Allow Outgoing Traffic

```bash
sudo ufw default allow outgoing
```

---

## 🗑️ Manage Rules

### 📋 Show Numbered Rules

```bash
sudo ufw status numbered
```

### ❌ Delete Rule by Number

```bash
sudo ufw delete 2
```

---

## ✨ Tips

* Always allow SSH **before enabling UFW** 🔑
* Use `verbose` mode for detailed insights 🔍
* Keep rules clean and minimal 🧹

---

## 🧯 Stay Secure. Stay Simple.

UFW makes firewall management easy—use it wisely!

---

# 🧱 IPTables – Kernel Firewall (Linux)

A powerful and flexible firewall built into the Linux kernel. Here’s a clean and stylish quick-reference guide.

---

## 📋 🔍 List All Rules

```bash id="y6r2ld"
sudo iptables -L -n -v
```

---

## 🔐 Allow Incoming SSH (Port 22)

```bash id="t2o7c8"
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
```

---

## 🌐 Allow Incoming HTTP (Port 80)

```bash id="wq9l5x"
sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT
```

---

## 🚫 Block Specific IP

```bash id="3cnh7g"
sudo iptables -A INPUT -s 192.168.1.100 -j DROP
```

---

## 🔄 Allow Established & Related Connections

> Ensures ongoing connections (like SSH sessions) remain active.

```bash id="tpx8fn"
sudo iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
```

---

## 🧹 Flush All Rules (Reset)

⚠️ **Warning:** This removes all current firewall rules.

```bash id="f4x9hz"
sudo iptables -F
```

---

## 💡 Tips

* Order matters! Rules are processed top → bottom 📊
* Always allow **SSH before restrictive rules** 🔑
* Save rules if you want persistence after reboot 💾
* Test carefully to avoid locking yourself out 🚪

---

## ⚡ Pro Tip

Combine rules wisely for better security and performance. IPTables is powerful—but with great power comes great responsibility 🕷️

---
# 📡 TCPDump – Packet Capture (Linux)

A powerful command-line tool to capture and analyze network traffic in real time.

---

## 🌐 🎯 Capture on Interface

```bash id="k3h9sd"
sudo tcpdump -i eth0
```

---

## 🔎 Capture Traffic on Specific Port (e.g., 80)

```bash id="u8f2lm"
sudo tcpdump -i eth0 port 80
```

---

## 🖥️ Capture Traffic from Specific Host

```bash id="c7v1qx"
sudo tcpdump -i eth0 host 192.168.1.100
```

---

## 💾 Save Capture to File

> Useful for later analysis in tools like Wireshark.

```bash id="a5k2zr"
sudo tcpdump -i eth0 -w capture.pcap
```

---

## 🔢 Capture Limited Number of Packets

```bash id="n0p4yt"
sudo tcpdump -i eth0 -c 100
```

---

## ⚡ Bonus Filters

### 📥 Only Incoming Traffic

```bash id="h9e3wb"
sudo tcpdump -i eth0 dst host 192.168.1.100
```

### 📤 Only Outgoing Traffic

```bash id="d2x8qo"
sudo tcpdump -i eth0 src host 192.168.1.100
```

---

## 💡 Tips

* Use `-n` to avoid DNS lookups (faster output) ⚡
* Combine filters for precision (port + host) 🎯
* Use `-vv` for more verbose packet details 🔍
* Run with `sudo` for full packet visibility 🔐

---

## 🧠 Example Combo

```bash id="x7r5gf"
sudo tcpdump -i eth0 host 192.168.1.100 and port 80 -c 50
```

---

## 🧯 Stay Observant. Capture Smart.

TCPDump is essential for debugging, monitoring, and security analysis.

---

