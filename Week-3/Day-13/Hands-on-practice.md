# 🧪💻 Day 13 — Linux Hands-On Practice 💻🧪

![Linux](https://img.shields.io/badge/Linux-Hands--On-blue?style=for-the-badge\&logo=linux)
![Level](https://img.shields.io/badge/Level-Beginner--Intermediate-orange?style=for-the-badge)
![Practice](https://img.shields.io/badge/Mode-Lab%20Exercises-green?style=for-the-badge)

---

## 🎯 ✦ Objective

Practice essential Linux commands to:

* 🖥️ Gather system information
* 🧠 Monitor memory & CPU
* 🔧 Discover hardware
* 📡 Inspect kernel logs

---

# 🧾 Exercise 1: Gather System Information

```bash id="ex1"
uname -a
hostname -I
uptime
uptime -p
```

### 🔍 Description

* `uname -a` → Full system/kernel info
* `hostname -I` → IP addresses
* `uptime` → System running time + load
* `uptime -p` → Human-readable uptime

---

# 🧠 Exercise 2: Check Memory and CPU

```bash id="ex2"
free -h
vmstat 1 5
lscpu | head -20
```

### 🔍 Description

* `free -h` → RAM & swap usage
* `vmstat 1 5` → Live system performance (5 samples, 1 sec interval)
* `lscpu` → CPU architecture details

---

# 🔧 Exercise 3: Hardware Discovery

```bash id="ex3"
lsusb
lspci | head -10
sudo lshw -short
```

### 🔍 Description

* `lsusb` → USB devices
* `lspci` → PCI hardware devices
* `lshw -short` → Summary of all hardware components

---

# 📡 Exercise 4: Check Kernel Messages

```bash id="ex4"
dmesg | tail -30
dmesg | grep -i error
dmesg | grep -i usb
```

### 🔍 Description

* `dmesg` → Kernel ring buffer logs
* `tail -30` → Last 30 system messages
* `grep -i error` → Filter error messages
* `grep -i usb` → USB-related logs

---

## 🌈 ✦ Tips for Practice

💡 Use `watch` for real-time monitoring:

```bash id="watch_cmd"
watch free -h
```

💡 Combine commands for deeper insights:

```bash id="combo_cmd"
uname -a && lscpu && free -h
```

💡 Save output to file:

```bash id="save_cmd"
lscpu > cpu_info.txt
```

---

## 🧠 ✦ Learning Outcome

After completing these exercises, you should be able to:

* Identify system configuration 🖥️
* Monitor performance metrics 📊
* Inspect hardware components 🔧
* Analyze kernel logs 📡

---

## 🏁 ✦ Summary

```text id="summary"
System Info   → uname, uptime, hostname  
Memory/CPU    → free, vmstat, lscpu  
Hardware      → lsusb, lspci, lshw  
Logs          → dmesg
```

---

# 🎯💻 Linux Interview Questions & Answers 💻🎯

![Linux](https://img.shields.io/badge/Linux-Interview-blue?style=for-the-badge\&logo=linux)
![Level](https://img.shields.io/badge/Level-Beginner--Intermediate-orange?style=for-the-badge)
![Topic](https://img.shields.io/badge/Topic-System%20Admin-green?style=for-the-badge)

---

## ❓ Q1: How do you check the Linux kernel version?

### ✅ Answer:

You can use the `uname` command:

```bash id="q1_cmd1"
uname -r
```

🔹 Displays the **kernel release version** only.

```bash id="q1_cmd2"
uname -a
```

🔹 Displays **complete system information**, including:

* Kernel version
* Hostname
* Architecture
* OS details

---

## ❓ Q2: How do you check memory usage in Linux?

### ✅ Answer:

Use the `free` command:

```bash id="q2_cmd"
free -h
```

🔍 Key points:

* `-h` → human-readable format (KB, MB, GB)
* Shows:

  * Total RAM 🧠
  * Used memory
  * Free memory
  * Swap usage
  * **Available memory** (important for new applications)

💡 The **"available"** column indicates how much memory can be used without swapping.

---

## ❓ Q3: What is load average and what do the three numbers mean?

### ✅ Answer:

Load average represents the **average number of processes waiting for CPU time** ⚙️

Example:

```text id="load_avg_example"
load average: 0.52, 0.65, 0.70
```

### 📊 The three values represent:

| ⏱️ Time Interval | 📈 Meaning                                |
| ---------------- | ----------------------------------------- |
| 1st number       | Load average over the **last 1 minute**   |
| 2nd number       | Load average over the **last 5 minutes**  |
| 3rd number       | Load average over the **last 15 minutes** |

---

### 🧠 Interpretation:

* ✅ Load < number of CPU cores → Healthy system
* ⚠️ Load ≈ CPU cores → Moderate load
* 🚨 Load > CPU cores → System may be overloaded

💡 Example:

* 4 CPU cores → Load average of 2.5 is fine
* 4 CPU cores → Load average of 6 indicates high pressure

---

## 🌈 ✦ Quick Summary

```text id="interview_summary"
Kernel Version → uname -r
Full System Info → uname -a
Memory Usage → free -h
Load Average → uptime
```

---

## 🏁 ✦ Final Tip

> 🎯 Always understand *what the numbers mean*, not just the commands
> ⚙️ Interviewers often test both command knowledge and interpretation

---
