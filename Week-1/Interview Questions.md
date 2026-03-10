# Linux Basic Interview Questions & Answers

---

## 1. What is Linux and how is it different from Windows?

**Linux** is a free and open-source operating system based on Unix. It is widely used for servers, cloud computing, and development environments.

### Key Differences

| Feature | Linux | Windows |
|---|---|---|
| Licensing | Free & Open Source | Paid & Proprietary |
| Interface | Command-line focused (CLI) | Graphical User Interface (GUI) focused |
| Security | More secure due to permissions and open-source model | More vulnerable to malware |
| File System | Case-sensitive | Case-insensitive |
| Software Installation | Package managers (`apt`, `yum`, `dnf`) | Executable installers (`.exe`, `.msi`) |
| Usage | Servers, cloud, DevOps | Personal computers, enterprise desktops |

---

## 2. Explain the Linux file system hierarchy.

Linux uses a **tree-like directory structure** starting from the **root directory `/`**.

| Directory | Purpose |
|---|---|
| `/` | Root directory (top of the file system) |
| `/bin` | Essential user commands |
| `/etc` | System configuration files |
| `/home` | User home directories |
| `/var` | Log files and variable data |
| `/usr` | User applications and utilities |
| `/tmp` | Temporary files |
| `/dev` | Device files |
| `/proc` | Process and system information |

Example path:
```
/home/user/documents/file.txt
```

---

## 3. What is the difference between absolute and relative paths?

| Path Type | Description | Example |
|---|---|---|
| Absolute Path | Full path from root directory `/` | `/home/user/file.txt` |
| Relative Path | Path relative to the current directory | `documents/file.txt` |

Example:

```
pwd
/home/user

Absolute path: /home/user/docs/file.txt
Relative path: docs/file.txt
```

---

## 4. How do you find files in Linux? (find vs locate)

### find
Searches files **in real-time** through the filesystem.

Example:

```
find /home -name "file.txt"
```

### locate
Searches files using a **prebuilt database**, so it is much faster.

Example:

```
locate file.txt
```

Update database:

```
sudo updatedb
```

Difference:

| Command | Speed | Method |
|---|---|---|
| find | Slower | Searches actual filesystem |
| locate | Faster | Uses indexed database |

---

## 5. What does `ls -la` show?

`ls -la` lists **all files and directories with detailed information**.

- `l` → Long listing format
- `a` → Show hidden files (files starting with `.`)

Example output:

```
drwxr-xr-x  2 user user 4096 Jan 10 10:00 documents
-rw-r--r--  1 user user  120 Jan 10 09:50 file.txt
```

Information shown:

- File permissions
- Number of links
- Owner
- Group
- File size
- Last modified date
- File name

---

## 6. How do you safely delete files and directories?

Delete a file:

```
rm file.txt
```

Delete a directory:

```
rm -r directory_name
```

Safe deletion with confirmation:

```
rm -i file.txt
```

Force delete:

```
rm -rf directory_name
```

Best practice: use `-i` to prevent accidental deletion.

---

## 7. What is the difference between `cat`, `more`, and `less`?

| Command | Purpose |
|---|---|
| `cat` | Displays entire file content |
| `more` | Shows file content page by page (forward only) |
| `less` | Shows file content page by page with forward and backward navigation |

Examples:

```
cat file.txt
more file.txt
less file.txt
```

`less` is most commonly used for large files.

---

## 8. How do you monitor a log file in real-time?

Use the `tail` command.

```
tail -f logfile.log
```

Example:

```
tail -f /var/log/syslog
```

`-f` means **follow the file as it grows**, which is useful for monitoring logs.

---

## 9. What command shows system information?

Use the `uname` command.

Example:

```
uname -a
```

Shows:

- Kernel name
- Hostname
- Kernel version
- Architecture
- Operating system

Other useful commands:

```
hostname
uptime
lscpu
free -h
```

---

## 10. How do you create nested directories in one command?

Use the `mkdir -p` command.

Example:

```
mkdir -p project/src/components
```

This creates:

```
project/
 └── src/
      └── components/
```

Without `-p`, intermediate directories must already exist.

---
