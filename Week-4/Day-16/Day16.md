# 🌐🛠️ Network Troubleshooting Guide  
## 📅 Day 16: Diagnosing Network Connectivity Issues  

---

## 🧠 What is Network Troubleshooting?

Network troubleshooting is the process of diagnosing and resolving:
- 🌍 Connectivity issues  
- 🔎 DNS problems  
- 🔀 Routing failures  

### 🔄 Workflow
```text
Diagnose → Identify → Resolve
```

### ⚙️Network Commands

| 🖥️ Command  | 📄 Description                         | 📂 Category    |
| ------------ | -------------------------------------- | -------------- |
| `netstat`    | Display network connections            | 🔗 Connections |
| `ss`         | Socket statistics (modern replacement) | 🔗 Connections |
| `traceroute` | Trace packet route                     | 🔀 Routing     |
| `nslookup`   | Query DNS nameservers                  | 🌐 DNS         |
| `dig`        | Detailed DNS lookup                    | 🌐 DNS         |

---

### 🏥 Real-Life Analogy  
#### 🩺 The Hospital Diagnosis Model

Think of **network troubleshooting** like a doctor diagnosing a patient.  
Each tool plays a critical role in uncovering the problem:

- ❤️ **`netstat` / `ss`** → Check the patient’s vital signs  
  *(Are the connections healthy and active?)*  

- 🧭 **`traceroute`** → Trace the path of symptoms  
  *(Where exactly is the breakdown happening?)*  

- 📚 **`nslookup` / `dig`** → Review medical records  
  *(Is the DNS resolving correctly?)*  

---

🧩 Each tool reveals a different aspect of network health!

# 🔧 Network Commands Guide

---

## 🔍 `ss` — Socket Statistics

The `ss` command is used to inspect socket connections and network statistics quickly and efficiently.

### 📡 Common Usage Examples

# Show listening TCP ports with process info

```
ss -tlnp
```

# Show all TCP connections

```
ss -ta
```

# Show UDP sockets

```
ss -ua
```

# Show socket summary

```
ss -s
```

# Filter by specific port

```
ss -tlnp | grep :80
```

## 🧭 traceroute — Trace Packet Route

**The traceroute command helps trace the path packets take from your system to a destination host.**

**📡 Common Usage Examples**

### Basic traceroute

```
traceroute google.com
```

### Use ICMP instead of UDP

```
traceroute -I google.com
```

### Numeric output only (faster, no DNS resolution)

```
traceroute -n google.com
```

### Set maximum hops

```
traceroute -m 20 google.com
```

## dig - DNS Information Groper

### Basic DNS query

```
dig google . com
```

### Short answer only

```
dig google . com + short
```
### Query specific record types

```
dig google . com MX
dig google . com NS
```
### Query specific DNS server

```
dig @8 .8.8.8 google . com
```
### Trace DNS delegation

```
dig google . com + trace
```
---

## nslookup - DNS Query

### Basic DNS lookup

```
nslookup google . com
```

### Query specific DNS server

```
nslookup google . com 8.8.8.8
```

### Query MX records

```
nslookup - type = mx gmail . com
```

### Reverse DNS lookup

```
nslookup 142.250.190.14
```
