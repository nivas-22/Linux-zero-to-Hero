# Linux Command Cheat Sheet (DevOps Basics)

---

# 1. System Information

| Command | Purpose | Example |
|---|---|---|
| `whoami` | Current logged-in user | `whoami` |
| `hostname` | Show system hostname | `hostname` |
| `uname` | System information | `uname -a` |
| `uptime` | System running time | `uptime` |
| `date` | Show system date/time | `date +"%Y-%m-%d"` |
| `cal` | Display calendar | `cal` |

---

# 2. File & Directory Navigation

| Command | Purpose | Example |
|---|---|---|
| `pwd` | Print current directory | `pwd` |
| `ls` | List files | `ls -la` |
| `cd` | Change directory | `cd /home/user` |
| `tree` | Show directory structure | `tree -L 2` |

---

# 3. File & Directory Management

| Command | Purpose | Example |
|---|---|---|
| `mkdir` | Create directory | `mkdir newfolder` |
| `mkdir -p` | Create nested directories | `mkdir -p project/src/app` |
| `rmdir` | Remove empty directory | `rmdir folder` |
| `touch` | Create file | `touch file.txt` |
| `cp` | Copy file | `cp file.txt backup.txt` |
| `cp -r` | Copy directory | `cp -r folder backup/` |
| `mv` | Move or rename | `mv old.txt new.txt` |
| `rm` | Remove file | `rm file.txt` |
| `rm -r` | Remove directory | `rm -r folder` |
| `stat` | File information | `stat file.txt` |

---

# 4. File Viewing Commands

| Command | Purpose | Example |
|---|---|---|
| `cat` | Display file content | `cat file.txt` |
| `tac` | Reverse file display | `tac file.txt` |
| `more` | Page-by-page viewer | `more file.txt` |
| `less` | Advanced file viewer | `less file.txt` |
| `head` | First lines of file | `head -10 file.txt` |
| `tail` | Last lines of file | `tail -10 file.txt` |
| `tail -f` | Monitor logs live | `tail -f /var/log/syslog` |

---

# 5. File Search Commands

| Command | Purpose | Example |
|---|---|---|
| `find` | Search files in filesystem | `find /home -name "*.txt"` |
| `locate` | Fast file search | `locate file.txt` |
| `which` | Locate command path | `which python` |

Update locate database:

```
sudo updatedb
```

---

# 6. File Permissions

| Command | Purpose | Example |
|---|---|---|
| `chmod` | Change file permissions | `chmod 755 script.sh` |
| `chown` | Change file owner | `chown user:file file.txt` |
| `chgrp` | Change group | `chgrp devops file.txt` |

Example:

```
chmod +x script.sh
```

Make file executable.

---

# 7. Disk Usage

| Command | Purpose | Example |
|---|---|---|
| `df` | Disk space usage | `df -h` |
| `du` | Directory size | `du -sh folder/` |
| `lsblk` | Block devices | `lsblk` |
| `mount` | Mount filesystem | `mount /dev/sdb1 /mnt` |

---

# 8. Process Management

| Command | Purpose | Example |
|---|---|---|
| `ps` | Process list | `ps aux` |
| `top` | Real-time processes | `top` |
| `htop` | Advanced process viewer | `htop` |
| `kill` | Kill process | `kill 1234` |
| `kill -9` | Force kill | `kill -9 1234` |
| `jobs` | Background jobs | `jobs` |

---

# 9. Networking Commands

| Command | Purpose | Example |
|---|---|---|
| `ping` | Check connectivity | `ping google.com` |
| `curl` | Fetch URL data | `curl https://example.com` |
| `wget` | Download files | `wget file_url` |
| `ip a` | Show IP address | `ip a` |
| `ss` | Network sockets | `ss -tuln` |
| `netstat` | Network info | `netstat -tulnp` |

---

# 10. Compression & Archives

| Command | Purpose | Example |
|---|---|---|
| `tar` | Archive files | `tar -cvf archive.tar folder` |
| `tar -xvf` | Extract tar file | `tar -xvf archive.tar` |
| `gzip` | Compress file | `gzip file.txt` |
| `gunzip` | Decompress | `gunzip file.txt.gz` |
| `zip` | Create zip archive | `zip archive.zip file.txt` |
| `unzip` | Extract zip | `unzip archive.zip` |

---

# 11. User Management

| Command | Purpose | Example |
|---|---|---|
| `useradd` | Add user | `sudo useradd devuser` |
| `passwd` | Set password | `passwd devuser` |
| `userdel` | Delete user | `sudo userdel devuser` |
| `groupadd` | Create group | `sudo groupadd devops` |
| `groups` | Show user groups | `groups username` |

---

# 12. Useful Shortcuts

| Shortcut | Purpose |
|---|---|
| `Ctrl + C` | Stop command |
| `Ctrl + Z` | Suspend process |
| `Ctrl + L` | Clear terminal |
| `Tab` | Auto-complete |
| `!!` | Repeat last command |

---

# Example DevOps Workflow

```
mkdir -p project/src
cd project
touch app.py
chmod +x app.py
git init
```

---
