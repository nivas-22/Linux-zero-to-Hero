# DAY 1: Introduction to Linux

## Understanding the Linux Operating System

---

## What is Linux?

Linux is a free, open-source operating system based on Unix. It’s used everywhere:

- 96% of web servers run Linux  
- Android is based on Linux  
- All major cloud platforms use Linux  
- Docker containers run on Linux  

---

## Linux vs Windows

| Feature | Linux | Windows |
|------|------|------|
| Licensing | Free & Open Source | Paid & Proprietary |
| Interface | Command-line focused | GUI focused |
| File System | Case-sensitive (`File ≠ file`) | Case-insensitive |
| Path Separator | Uses `/` for paths | Uses `\` for paths |
| Drives | No drive letters (`C:`, `D:`) | Uses drive letters |
| Software Installation | Package managers (`apt`, `yum`) | Installers (`.exe`, `.msi`) |

---

## Popular Linux Distributions

- **Ubuntu** – Best for beginners, desktop use  
- **CentOS / RHEL** – Enterprise servers  
- **Debian** – Stable and reliable  
- **Amazon Linux** – Optimized for AWS  
- **Alpine Linux** – Lightweight, commonly used for Docker containers  

---

## Basic Commands

1. `whoami` – Display current user  
2. `pwd` – Print working directory  
3. `ls` – List files  
4. `uname` – System information  
5. `hostname` – Show or set system hostname  

---

## `date` Command Flags

| Flag / Format | Description |
|---|---|
| `-u` | Display UTC time |
| `-d "STRING"` | Display date described by STRING |
| `+%Y` | Year (e.g., 2024) |
| `+%m` | Month (01–12) |
| `+%d` | Day of month (01–31) |
| `+%H` | Hour (00–23) |
| `+%M` | Minute (00–59) |
| `+%S` | Second (00–59) |
| `+%A` | Full weekday name (Monday) |
| `+%B` | Full month name (January) |

---

## `uname` Command Flags

| Flag | Description |
|---|---|
| `-a` | Print all information |
| `-s` | Print kernel name (Linux) |
| `-n` | Print hostname |
| `-r` | Print kernel release version |
| `-v` | Print kernel version |
| `-m` | Print machine hardware name (x86_64) |
| `-p` | Print processor type |
| `-o` | Print operating system |

---

## `hostname` Command Flags

| Flag | Description |
|---|---|
| `-f` | Display FQDN (Fully Qualified Domain Name) |
| `-i` | Display IP address |
| `-I` | Display all IP addresses |
| `-s` | Display short hostname |
| `-d` | Display domain name |

---

# Workout

```bash
$ date
Mon Jan 15 10:30:45 IST 2024

$ date +"%Y-%m-%d"
2024-01-15

$ date +"%H:%M:%S"
10:30:45

$ date +"%A, %B %d, %Y"
Monday, January 15, 2024

$ date -u
Mon Jan 15 05:00:45 UTC 2024

$ date -d "next Friday"
Fri Jan 19 00:00:00 IST 2024

$ date -d "2 days ago"
Sat Jan 13 10:30:45 IST 2024


$ uname
Linux

$ uname -a
Linux server01 5.15.0-91-generic #101-Ubuntu SMP x86_64 GNU/Linux

$ uname -r
5.15.0-91-generic

$ uname -m
x86_64

$ uname -n
server01

$ uname -o
GNU/Linux


$ hostname
webserver01

$ hostname -f
webserver01.example.com

$ hostname -i
192.168.1.100

$ hostname -I
192.168.1.100 10.0.0.5

$ hostname -s
webserver01
```
