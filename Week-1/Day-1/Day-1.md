# 🐧 Day 1: Introduction to Linux

## 📘 Understanding the Linux Operating System

---

# 🧠 What is Linux?

**Linux** is a **free and open-source operating system** based on Unix.
It is widely used in servers, cloud platforms, and development environments.

### 🌍 Where Linux is Used

* 📡 **96% of web servers** run Linux
* 📱 **Android** is built on the Linux kernel
* ☁️ **All major cloud platforms** rely on Linux
* 🐳 **Docker containers** run on Linux

---

# ⚖️ Linux vs Windows

| Feature               | Linux                           | Windows                     |
| --------------------- | ------------------------------- | --------------------------- |
| Licensing             | Free & Open Source              | Paid & Proprietary          |
| Interface             | Command-line focused            | GUI focused                 |
| File System           | Case-sensitive (`File ≠ file`)  | Case-insensitive            |
| Path Separator        | Uses `/`                        | Uses `\`                    |
| Drives                | No drive letters                | Uses `C:`, `D:`             |
| Software Installation | Package managers (`apt`, `yum`) | Installers (`.exe`, `.msi`) |

---

# 🐧 Popular Linux Distributions

| Distribution      | Description                              |
| ----------------- | ---------------------------------------- |
| **Ubuntu**        | Beginner-friendly Linux distribution     |
| **CentOS / RHEL** | Enterprise-level server distributions    |
| **Debian**        | Known for stability and reliability      |
| **Amazon Linux**  | Optimized for AWS cloud                  |
| **Alpine Linux**  | Lightweight distribution used for Docker |

---

# 💻 Basic Linux Commands

| Command    | Description                        |
| ---------- | ---------------------------------- |
| `whoami`   | Display the current logged-in user |
| `pwd`      | Print working directory            |
| `ls`       | List files and directories         |
| `uname`    | Display system information         |
| `hostname` | Show or set system hostname        |

---

# 📅 `date` Command Flags

| Flag / Format | Description                      |
| ------------- | -------------------------------- |
| `-u`          | Display UTC time                 |
| `-d "STRING"` | Display date described by STRING |
| `+%Y`         | Year (Example: 2024)             |
| `+%m`         | Month (01–12)                    |
| `+%d`         | Day of month (01–31)             |
| `+%H`         | Hour (00–23)                     |
| `+%M`         | Minute (00–59)                   |
| `+%S`         | Second (00–59)                   |
| `+%A`         | Full weekday name                |
| `+%B`         | Full month name                  |

---

# 🖥️ `uname` Command Flags

| Flag | Description                  |
| ---- | ---------------------------- |
| `-a` | Print all system information |
| `-s` | Print kernel name            |
| `-n` | Print hostname               |
| `-r` | Print kernel release version |
| `-v` | Print kernel version         |
| `-m` | Print machine hardware name  |
| `-p` | Print processor type         |
| `-o` | Print operating system       |

---

# 🌐 `hostname` Command Flags

| Flag | Description                                |
| ---- | ------------------------------------------ |
| `-f` | Display fully qualified domain name (FQDN) |
| `-i` | Display IP address                         |
| `-I` | Display all IP addresses                   |
| `-s` | Display short hostname                     |
| `-d` | Display domain name                        |

---

# 🏋️ Practice (Workout)

## 📅 Date Command Examples

```bash
date
```

```bash
date +"%Y-%m-%d"
```

```bash
date +"%H:%M:%S"
```

```bash
date +"%A, %B %d, %Y"
```

```bash
date -u
```

```bash
date -d "next Friday"
```

```bash
date -d "2 days ago"
```

---

## 🖥️ Uname Command Examples

```bash
uname
```

```bash
uname -a
```

```bash
uname -r
```

```bash
uname -m
```

```bash
uname -n
```

```bash
uname -o
```

---

## 🌐 Hostname Command Examples

```bash
hostname
```

```bash
hostname -f
```

```bash
hostname -i
```

```bash
hostname -I
```

```bash
hostname -s
```

---

# 🚀 Summary

In **Day 1**, you learned:

* What Linux is and where it is used
* Differences between Linux and Windows
* Popular Linux distributions
* Basic Linux commands
* Important flags for `date`, `uname`, and `hostname`
* Practical command examples for hands-on practice

These concepts are the **foundation for Linux system administration, DevOps, and cloud engineering**.
