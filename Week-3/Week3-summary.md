# 📘⚡ DAY 11–15 — LINUX QUICK REFERENCE CHEAT SHEET ⚡📘

![Linux](https://img.shields.io/badge/Linux-CheatSheet-blue?style=for-the-badge\&logo=linux)
![Level](https://img.shields.io/badge/Level-Quick%20Reference-green?style=for-the-badge)
![Use](https://img.shields.io/badge/Use-Revision%20%7C%20Interview-orange?style=for-the-badge)

---

# 📦 ✦ Package Management (Debian / Ubuntu)

| Command            | Purpose                 | Example                      |
| ------------------ | ----------------------- | ---------------------------- |
| `apt-get update`   | Update package list     | `sudo apt-get update`        |
| `apt-get upgrade`  | Upgrade packages        | `sudo apt-get upgrade -y`    |
| `apt-get install`  | Install package         | `sudo apt-get install nginx` |
| `apt-get remove`   | Remove package          | `sudo apt-get remove nginx`  |
| `apt-cache search` | Search packages         | `apt-cache search nginx`     |
| `dpkg -l`          | List installed packages | `dpkg -l \| grep nginx`      |
| `dpkg -S`          | Find file owner         | `dpkg -S /usr/bin/vim`       |

---

# 📦 ✦ Package Management (RHEL / CentOS)

| Command       | Purpose                 | Example                   |
| ------------- | ----------------------- | ------------------------- |
| `yum install` | Install package         | `sudo yum install httpd`  |
| `yum update`  | Update packages         | `sudo yum update`         |
| `yum remove`  | Remove package          | `sudo yum remove httpd`   |
| `rpm -qa`     | List installed packages | `rpm -qa \| grep http`    |
| `rpm -qf`     | Find file owner         | `rpm -qf /usr/sbin/httpd` |

---

# ⚙️ ✦ Services (systemd)

| Command             | Purpose         | Example                        |
| ------------------- | --------------- | ------------------------------ |
| `systemctl start`   | Start service   | `sudo systemctl start nginx`   |
| `systemctl stop`    | Stop service    | `sudo systemctl stop nginx`    |
| `systemctl restart` | Restart service | `sudo systemctl restart nginx` |
| `systemctl enable`  | Enable at boot  | `sudo systemctl enable nginx`  |
| `systemctl status`  | Check status    | `systemctl status nginx`       |

---

# 🖥️ ✦ System Information

| Command       | Purpose       | Example         |
| ------------- | ------------- | --------------- |
| `uname -a`    | System info   | `uname -a`      |
| `hostname -I` | Show IPs      | `hostname -I`   |
| `uptime`      | Uptime & load | `uptime`        |
| `free -h`     | Memory usage  | `free -h`       |
| `lscpu`       | CPU info      | `lscpu`         |
| `dmesg`       | Kernel logs   | `dmesg \| tail` |

---

# 📦 ✦ Backup & Archiving

| Command     | Purpose          | Example                        |
| ----------- | ---------------- | ------------------------------ |
| `tar -czvf` | Create tar.gz    | `tar -czvf backup.tar.gz dir/` |
| `tar -xzvf` | Extract tar.gz   | `tar -xzvf backup.tar.gz`      |
| `tar -tzvf` | List contents    | `tar -tzvf backup.tar.gz`      |
| `rsync -av` | Sync directories | `rsync -av src/ dest/`         |
| `zip -r`    | Create zip       | `zip -r archive.zip dir/`      |
| `unzip`     | Extract zip      | `unzip archive.zip`            |

---

# 🌐 ✦ Networking

| Command    | Purpose               | Example                |
| ---------- | --------------------- | ---------------------- |
| `ip addr`  | Show IP addresses     | `ip a`                 |
| `ip link`  | Show interfaces       | `ip l`                 |
| `ip route` | Show routing table    | `ip r`                 |
| `ping`     | Test connectivity     | `ping -c 4 google.com` |
| `ifconfig` | Legacy network config | `ifconfig`             |

---

# 🧠 ✦ Quick Interview Recall

* 📦 `apt` → Debian-based package management
* 📦 `yum/rpm` → RHEL-based package management
* ⚙️ `systemctl` → Service control (systemd)
* 🖥️ `uname`, `free`, `uptime` → System diagnostics
* 📦 `tar`, `zip`, `rsync` → Backup & sync tools
* 🌐 `ip`, `ping` → Networking & connectivity

---

# 🚀 ✦ Pro Tip

👉 In real-world Linux:

* Use `ip` instead of `ifconfig`
* Use `systemctl` instead of older service commands
* Use `rsync` for efficient backups
* Use `tar` for archiving + compression workflows

---

# 🏁 ✦ Final Note

> ⚡ This cheat sheet is designed for **quick revision, interviews, and hands-on practice** across Linux administration topics

---
