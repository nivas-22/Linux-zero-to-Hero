# System Info and Monitoring

> **Hardware and System Information Commands**

# 🖥️ Uname Command - System Information Guide

![Linux](https://img.shields.io/badge/OS-Linux-blue?style=for-the-badge&logo=linux)
![Command](https://img.shields.io/badge/Command-uname-green?style=for-the-badge&logo=gnubash)
![Category](https://img.shields.io/badge/Category-System%20Info-orange?style=for-the-badge)

---

## 📌 Overview
The `uname` command displays **system information** about your machine, including kernel, hardware, and OS details.

```bash
uname [OPTION]
```
---

### 🎯 Common Flags & Options

| 🔤 Flag | 📝 Description                          | 💡 Example |
| ------- | --------------------------------------- | ---------- |
| `-a`    | 🌈 **Print ALL information**            | `uname -a` |
| `-s`    | 🧠 Kernel name (e.g., Linux)            | `uname -s` |
| `-n`    | 🌐 Network hostname                     | `uname -n` |
| `-r`    | 🔢 Kernel release version               | `uname -r` |
| `-v`    | 🏷️ Kernel version                      | `uname -v` |
| `-m`    | 💻 Machine hardware name (e.g., x86_64) | `uname -m` |
| `-p`    | ⚙️ Processor type                       | `uname -p` |
| `-i`    | 🧩 Hardware platform                    | `uname -i` |
| `-o`    | 🖥️ Operating system                    | `uname -o` |

---

**Example Outputs:**

```copy
# Show all system information
$ uname -a
Linux server01 5.15.0 -91 - generic #101 - Ubuntu SMP x86_64 GNU / Linux

# Kernel name only
$ uname -s
Linux

# Kernel release / version ( most commonly used )
$ uname -r
5.15.0 -91 - generic

# Machine architecture
$ uname -m
x86_64

# Operating system
$ uname -o
GNU / Linux

# Hostname
$ uname -n
server01
```
---

# 🌐 Hostname Command Guide

> ✨ **Display or set your system's hostname with ease**

---

## 📌 Overview

The `hostname` command is used to:

- 🖥️ Display the current system hostname  
- ✏️ Set a new hostname (with proper permissions)

---

## 🚀 Basic Usage

```bash
hostname
```

# 🎛️ Hostname Flags & Options

| ⚙️ Flag | 🔤 Long Option | 🌈 Description |
|--------|--------------|----------------|
| `-f` | `--fqdn` | 🌐 Display Fully Qualified Domain Name |
| `-i` | — | 📍 Display IP address of hostname |
| `-I` | — | 🌏 Display ALL IP addresses |
| `-s` | — | ✂️ Display short hostname |
| `-d` | — | 🏷️ Display DNS domain name |

---

**Examples Outputs:**

```copy

# Display hostname
$ hostname
webserver01

# Display FQDN
$ hostname -f
webserver01 . example.com

# Display all IP addresses
$ hostname -I
192.168.1.100 10.0.0.5 172.17.0.1

# Set hostname temporarily
$ sudo hostname newhostname

# Set hostname permanently ( systemd )
$ sudo hostnamectl set - hostname newserver

# View hostnamectl info
$ hostnamectl
Static hostname : server01
Icon name : computer - vm
Chassis : vm
Machine ID : abc123 ...
Boot ID : def456 ...

Operating System : Ubuntu 22.04.3 LTS
Kernel : Linux 5.15.0 -91 - generic
Architecture : x86 -64
```
---

### uptime - System Uptime and Load Average

**Example results**

```copy
# Show uptime
$ uptime
14:32:15 up 45 days , 3:22 , 3 users , load average : 0.15 , 0.20 , 0.18

# Breakdown :
# 14:32:15 - Current time
# up 45 days - System uptime
# 3 users - Number of logged in users
# load average - 1 min , 5 min , 15 min CPU load averages
# Pretty format
$ uptime -p
up 45 days , 3 hours , 22 minutes

# Since when ( boot time )
$ uptime -s
2023 -11 -30 11:10:00
```
---
# 💡 Pro Tip: Understanding Load Average

> ⚡ Measure system performance like a pro

---

## 🧠 What is Load Average?

📊 **Load average** represents the average number of processes:
- Running on CPU 🖥️  
- Waiting for CPU time ⏳  

---

## 🎯 Key Guidelines

- ✅ Values should ideally be **less than the number of CPU cores**
- 💻 Example: On a **4-core system**
  - ✔️ Load `< 4.0` → Healthy
  - ⚠️ Load `= 4.0` → Fully utilized
  - ❌ Load `> 4.0` → System overloaded

---

## ⏱️ The 3 Load Values

| ⏳ Time Window | 📌 Meaning |
|--------------|-----------|
| `1 min`  | ⚡ Immediate system load (short-term) |
| `5 min`  | 📊 Average load (medium-term) |
| `15 min` | 🧘 Long-term trend |

---

## 🚦 Quick Interpretation

- 🟢 Low load → System is underutilized  
- 🟡 Moderate load → Normal operation  
- 🔴 High load → CPU bottleneck / possible slowdown  

---

## 🎨 Example

```bash
uptime
```
---

# 🧠✨ FREE COMMAND - MEMORY USAGE GUIDE ✨🧠


![Linux](https://img.shields.io/badge/Linux-Memory-blue?style=for-the-badge\&logo=linux)
![Command](https://img.shields.io/badge/Command-free-green?style=for-the-badge\&logo=gnubash)
![Usage](https://img.shields.io/badge/Usage-System%20Monitoring-orange?style=for-the-badge)

---

## 🌌 ✦ Overview

> `free` displays **system memory (RAM + swap) usage** in real time ⚡

```bash id="z8l9cw"
free [OPTIONS]
```

---

## 🎛️ ✦ Flags & Options

| ⚡ Option | 💎 Description                           |
| -------- | ---------------------------------------- |
| `-h`     | 📊 Human-readable (KB, MB, GB)           |
| `-b`     | 🧮 Display in bytes                      |
| `-k`     | 📦 Display in kilobytes (default)        |
| `-m`     | 📘 Display in megabytes                  |
| `-g`     | 📗 Display in gigabytes                  |
| `-t`     | ➕ Show total line                        |
| `-s N`   | 🔄 Update every N seconds                |
| `-c N`   | ⏱️ Display N times then exit             |
| `-w`     | 🧩 Wide output (separates buffers/cache) |

---

## 🚀 ✦ Examples

### 📊 Human Readable Output

```bash id="x1f9du"
free -h
```

```text id="6jktm3"
              total   used   free  shared  buff/cache  available
Mem:           7.7G   2.1G   3.5G   200M      2.1G        5.1G
Swap:          2.0G     0B   2.0G
```

---

### 🔄 Live Monitoring (Every 2 Seconds)

```bash id="s2m91c"
free -h -s 2
```

---

### ⏱️ Run 5 Times Then Exit

```bash id="wpl3d9"
free -h -c 5
```

---

### ➕ Show Total Memory

```bash id="af3s7n"
free -h -t
```

---

### 🧩 Wide Output Mode

```bash id="s7f2kd"
free -w
```

---

## 🌈 ✦ Animated Terminal Feel

```text id="8c91mj"
[✔] Checking memory usage...
[✔] Total RAM   → 8GB
[✔] Used        → 2.1GB
[✔] Free        → 3.5GB
[✔] Cache       → 2.1GB
[🚀] System Healthy!
```

---

## 🧠 ✦ Pro Tips

💡 Best combo for monitoring:

```bash id="6v4fma"
watch -n 2 free -h
```

💡 Debug memory issues:

```bash id="1sk6rt"
free -m && ps aux --sort=-%mem | head
```

💡 Focus on actual usable memory:

* `available` is more accurate than `free`

---

## ⚡ ✦ Quick Summary

```text id="zq7x1o"
free = RAM usage in one glance

-h → readable
-s → live refresh
-c → limit runs
-t → totals
```

---

## 🏁 ✦ Final Note

> 🧠 Memory monitoring is key for performance tuning
> ⚙️ Essential for DevOps, backend, and system admins

---
# 🧠📊 VMSTAT — VIRTUAL MEMORY STATISTICS GUIDE 📊🧠

![Linux](https://img.shields.io/badge/Linux-System-blue?style=for-the-badge\&logo=linux)
![Command](https://img.shields.io/badge/Command-vmstat-green?style=for-the-badge\&logo=gnubash)
![Category](https://img.shields.io/badge/Category-Memory%20%26%20CPU-orange?style=for-the-badge)

---

## 🌌 ✦ Overview

> `vmstat` reports **virtual memory, processes, CPU activity, I/O, and system performance** ⚡

```bash id="vmstat_basic"
vmstat [options] [delay [count]]
```

---

## 🎯 ✦ What It Shows

* 🧠 Memory usage (RAM, swap)
* ⚙️ CPU activity
* 🔄 Process states
* 💽 I/O performance
* 📈 System activity trends

---

## 🎛️ ✦ Common Options

| ⚡ Option | 💎 Description               |
| -------- | ---------------------------- |
| `-a`     | 📊 Active/inactive memory    |
| `-s`     | 📋 Memory statistics summary |
| `-d`     | 💽 Disk statistics           |
| `-t`     | 🕒 Add timestamp to output   |
| `-w`     | 📏 Wide output               |

---

## 🚀 ✦ Examples

### 📊 Basic Output

```bash id="vmstat_basic_run"
vmstat
```

```text id="vmstat_output"
procs -----------memory---------- ---swap-- -----io---- -system-- ------cpu-----
 r  b   swpd   free   buff  cache   si   so    bi    bo   in   cs  us sy id wa st
 1  0      0  3500000 120000 2100000  0    0     5    10  200  300   5  2 93  0  0
```

---

### 🔄 Live Monitoring (Every 2 Seconds)

```bash id="vmstat_live"
vmstat 2
```

---

### ⏱️ Run 5 Times with Delay

```bash id="vmstat_count"
vmstat 2 5
```

---

### 📋 Memory Summary

```bash id="vmstat_summary"
vmstat -s
```

---

### 💽 Disk Statistics

```bash id="vmstat_disk"
vmstat -d
```

---

### 🕒 Timestamped Output

```bash id="vmstat_time"
vmstat -t
```

---

## 🌈 ✦ Field Breakdown

### 🧠 Memory Section

* `free` → available memory
* `buff` → buffer memory
* `cache` → cached memory

### 🔄 Swap

* `si` → swap in
* `so` → swap out

### 💽 I/O

* `bi` → blocks received
* `bo` → blocks sent

### ⚙️ System

* `in` → interrupts
* `cs` → context switches

### 🧮 CPU

* `us` → user time
* `sy` → system time
* `id` → idle time
* `wa` → waiting I/O
* `st` → stolen time (VM)

---

## 🌈 ✦ Animated Monitoring Feel

```text id="vmstat_live_view"
[✔] Monitoring system...
[✔] CPU Idle   → 93%
[✔] Free Mem   → Stable
[✔] I/O Wait   → Low
[🚀] System Healthy
```

---

## 🧠 ✦ Pro Tips

💡 Real-time performance tracking:

```bash id="vmstat_watch"
watch -n 1 vmstat
```

💡 Combine with other tools:

```bash id="vmstat_combo"
vmstat 1 5 && free -h
```

💡 Diagnose bottlenecks:

* High `wa` → disk bottleneck 💽
* High `si/so` → memory pressure 🧠
* High `cs` → excessive context switching ⚙️

---

## ⚡ ✦ Quick Summary

```text id="vmstat_summary_short"
vmstat = system performance snapshot

- Memory
- CPU
- I/O
- Processes
```

---

## 🏁 ✦ Final Note

> 📊 vmstat is essential for **performance tuning, debugging, and monitoring system health**
> ⚙️ Widely used in DevOps, SRE, and system diagnostics

---

# 🧠⚙️ LSCPU — CPU INFORMATION GUIDE ⚙️🧠

![Linux](https://img.shields.io/badge/Linux-CPU-blue?style=for-the-badge\&logo=linux)
![Command](https://img.shields.io/badge/Command-lscpu-green?style=for-the-badge\&logo=gnubash)
![Category](https://img.shields.io/badge/Category-Hardware-orange?style=for-the-badge)

---

## 🌌 ✦ Overview

> `lscpu` displays **CPU architecture and detailed processor information** 🧠

```bash id="lscpu_basic"
lscpu
```

---

## 🎯 ✦ What It Shows

* 🧠 CPU architecture
* ⚙️ Number of CPUs / cores / threads
* 🏗️ CPU vendor & model
* 🔢 CPU frequency
* 🧩 Cache details
* 🔁 Virtualization support

---

## 🚀 ✦ Example Output

```text id="lscpu_output"
Architecture:        x86_64
CPU op-mode(s):      32-bit, 64-bit
Byte Order:          Little Endian
CPU(s):              8
On-line CPU(s) list: 0-7
Thread(s) per core:  2
Core(s) per socket:  4
Socket(s):           1
Vendor ID:           GenuineIntel
Model name:          Intel(R) Core(TM) i7 CPU
CPU MHz:             2400.000
Cache size:          8192 KB
```

---

## 🎛️ ✦ Useful Options

| ⚡ Option | 💎 Description                        |
| -------- | ------------------------------------- |
| `-a`     | 📊 Display all CPU information        |
| `-e`     | 📋 Output in extended (table) format  |
| `-p`     | 🧾 Parseable format (script-friendly) |
| `-J`     | 📦 JSON output                        |
| `-x`     | 🧩 Hexadecimal masks                  |

---

## 📊 ✦ Example Commands

### 🧠 Basic CPU Info

```bash id="lscpu_basic_cmd"
lscpu
```

---

### 📋 Extended Table Format

```bash id="lscpu_extended"
lscpu -e
```

---

### 📦 JSON Output (for scripting)

```bash id="lscpu_json"
lscpu -J
```

---

### 🧾 Parseable Output

```bash id="lscpu_parse"
lscpu -p
```

---

## 🌈 ✦ Key Fields Explained

### 🧠 CPU Structure

* `CPU(s)` → Total logical CPUs
* `Core(s) per socket` → Physical cores per CPU
* `Thread(s) per core` → Hyperthreading threads
* `Socket(s)` → Number of physical CPUs

### ⚙️ Performance

* `CPU MHz` → Current clock speed
* `CPU max MHz` / `CPU min MHz` → Frequency range

### 🧩 Cache

* `L1d`, `L1i`, `L2`, `L3` → CPU cache hierarchy

---

## 🌈 ✦ Animated Terminal Feel

```text id="lscpu_live"
[✔] Detecting CPU...
[✔] Vendor     → Intel
[✔] Cores      → 4
[✔] Threads    → 8
[✔] Architecture → x86_64
[🚀] Ready
```

---

## 🧠 ✦ Pro Tips

💡 Check CPU count quickly:

```bash id="lscpu_count"
nproc
```

💡 Combine with `grep` for specific info:

```bash id="lscpu_grep"
lscpu | grep "Model name"
```

💡 Use for performance tuning:

* More cores → better parallel processing
* Threads → improves multitasking

---

## ⚡ ✦ Quick Summary

```text id="lscpu_summary"
lscpu = CPU hardware + architecture details

- Cores
- Threads
- Architecture
- Vendor
- Cache
```

---

## 🏁 ✦ Final Note

> 🧠 `lscpu` is essential for understanding CPU capabilities
> ⚙️ Useful for system tuning, virtualization, and performance analysis

---
