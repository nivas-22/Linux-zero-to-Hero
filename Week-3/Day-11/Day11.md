# DAY 11: Package Management

**Installing and Managing Software Packages**

# 📦 Package Management in Linux

### 📘 Theory

## What is Package Management?

A **package manager** is a tool that automates the process of:

- Installing software  
- Upgrading packages  
- Configuring applications  
- Removing software  

It simplifies software management and ensures dependencies are handled correctly.

---

### 🐧 Package Managers by Distribution

Different Linux distributions use different package managers:

#### 🔹 Debian / Ubuntu
- **Package Manager:** APT (Advanced Package Tool)
- **Package Format:** `.deb`

Examples:
```bash
sudo apt update
sudo apt install package-name
sudo apt upgrade
```
---

# 🐧 Debian / Ubuntu Package Management

### 📦 apt-get — Advanced Package Tool

`apt-get` is a command-line tool used to manage packages on Debian-based systems like Ubuntu.

---

### ⚙️ Main Commands

| Command | Description |
|--------|------------|
| `apt-get update` | Update package list from repositories |
| `apt-get upgrade` | Upgrade all installed packages |
| `apt-get dist-upgrade` | Upgrade packages with dependency changes |
| `apt-get install PKG` | Install a package |
| `apt-get remove PKG` | Remove a package (keeps configuration files) |
| `apt-get purge PKG` | Remove a package along with its configuration files |
| `apt-get autoremove` | Remove unused dependencies |
| `apt-get clean` | Clear downloaded package cache |
| `apt-get autoclean` | Remove only outdated package cache |

---

### 🔧 Common Options

| Option | Description |
|-------|------------|
| `-y` | Assume "yes" to all prompts (non-interactive) |
| `-q` | Quiet mode (minimal output) |
| `-f` | Fix broken dependencies |
| `-d` | Download only (do not install) |

---

### 🧠 Example Usage

```bash id="z9p2lm"
sudo apt-get update
sudo apt-get upgrade -y
sudo apt-get install nginx
```

---

# Implementation:

### Step 1: Always update package list first
$ sudo apt - get update

### Step 2: Upgrade all installed packages
$ sudo apt - get upgrade -y

### Full system upgrade ( may add / remove packages )
$ sudo apt - get dist - upgrade -y

### Install a single package
$ sudo apt - get install nginx

### Install multiple packages
$ sudo apt - get install nginx mysql - server php

### Install specific version
$ sudo apt - get install nginx =1.18.0 -0 ubuntu1

### Install without recommended packages ( smaller )
$ sudo apt - get install --no - install - recommends nginx

### Remove package ( keep configuration files )
$ sudo apt - get remove nginx

### Remove package AND configuration files
$ sudo apt - get purge nginx

### Remove unused dependencies
$ sudo apt - get autoremove

### Fix broken packages
$ sudo apt - get install -f

### Clean package cache ( free disk space )
$ sudo apt - get clean
$ sudo apt - get autoclean
---

# CentOS/RHEL Package Management

**yum - Yellowdog Updater Modified**


#### 📦 YUM Package Management Commands

#### Commands

1. `yum install PKG` — Install a package  
2. `yum update` — Update all packages  
3. `yum update PKG` — Update a specific package  
4. `yum remove PKG` — Remove a package  
5. `yum search TERM` — Search for packages  
6. `yum info PKG` — Show package information  
7. `yum list installed` — List installed packages  
8. `yum list available` — List available packages  
9. `yum clean all` — Clean cache  
10. `yum repolist` — List enabled repositories  
11. `yum provides FILE` — Find package providing a file  
12. `yum history` — Show transaction history  
13. `yum groupinstall` — Install a package group  

---

#### ⚙️ Common Options

1. `-y` — Assume yes to all prompts  
2. `-q` — Quiet mode (less output)  
3. `--nogpgcheck` — Skip GPG signature verification  
4. `--enablerepo=` — Temporarily enable a repository  
5. `--disablerepo=` — Temporarily disable a repository  

---

# Implementation commands:

### Install a package
$ sudo yum install httpd

### Install with automatic yes
$ sudo yum install -y httpd

### Install multiple packages
$ sudo yum install -y httpd mariadb - server php

### Update all packages
$ sudo yum update -y

### Update specific package
$ sudo yum update httpd

### Remove a package
$ sudo yum remove httpd

### Search for packages
$ yum search nginx
$ yum search " web server "

### Show package information
$ yum info httpd

### List installed packages
$ yum list installed
$ yum list installed | grep http

### List all available packages
$ yum list available

### Find which package provides a file
$ yum provides / usr / sbin / httpd
$ yum provides "*/ nginx "

### Clean cache
$ sudo yum clean all

### List repositories
$ yum repolist
$ yum repolist all # Include disabled

### View transaction history
$ yum history
$ yum history info 5 # Show transaction 5
$ sudo yum history undo 5 # Undo transaction 5

# Install package group
$ sudo yum groupinstall " Development Tools "
$ yum grouplist

---
