# 🐧 Linux Basic Interview Questions & Answers

A quick reference guide for **Linux fundamentals** commonly asked in technical interviews.

---

# 📘 1. What is Linux and how is it different from Windows?

**Linux** is a **free and open-source operating system** based on Unix.
It is widely used in **servers, cloud infrastructure, DevOps, and development environments**.

## 🔑 Key Differences

| Feature               | Linux                                          | Windows                                  |
| --------------------- | ---------------------------------------------- | ---------------------------------------- |
| Licensing             | Free & Open Source                             | Paid & Proprietary                       |
| Interface             | Command Line (CLI) focused                     | Graphical Interface (GUI) focused        |
| Security              | Strong permissions model, open-source auditing | More common malware target               |
| File System           | Case-sensitive                                 | Case-insensitive                         |
| Software Installation | Package managers (`apt`, `yum`, `dnf`)         | `.exe` / `.msi` installers               |
| Usage                 | Servers, Cloud, DevOps                         | Personal computers & enterprise desktops |

---

# 📁 2. Explain the Linux File System Hierarchy

Linux uses a **tree-like directory structure** that starts from the **root directory `/`**.

```
/
├── bin
├── etc
├── home
├── usr
├── var
├── tmp
├── dev
└── proc
```

## 📂 Important Directories

| Directory | Purpose                                      |
| --------- | -------------------------------------------- |
| `/`       | Root directory (top level of the filesystem) |
| `/bin`    | Essential user commands                      |
| `/etc`    | System configuration files                   |
| `/home`   | User home directories                        |
| `/var`    | Logs and variable data                       |
| `/usr`    | Applications and utilities                   |
| `/tmp`    | Temporary files                              |
| `/dev`    | Device files                                 |
| `/proc`   | Process and system information               |

Example path:

```
/home/user/documents/file.txt
```

---

# 📍 3. Absolute Path vs Relative Path

| Path Type     | Description                        | Example               |
| ------------- | ---------------------------------- | --------------------- |
| Absolute Path | Full path starting from `/`        | `/home/user/file.txt` |
| Relative Path | Path relative to current directory | `documents/file.txt`  |

### Example

```bash
pwd
/home/user
```

Absolute path:

```bash
/home/user/docs/file.txt
```

Relative path:

```bash
docs/file.txt
```

---

# 🔍 4. How do you find files in Linux? (`find` vs `locate`)

## Using `find`

Searches the filesystem **in real time**.

```bash
find /home -name "file.txt"
```

---

## Using `locate`

Searches using a **prebuilt database**, making it much faster.

```bash
locate file.txt
```

Update the database:

```bash
sudo updatedb
```

### Difference

| Command  | Speed  | Method                     |
| -------- | ------ | -------------------------- |
| `find`   | Slower | Searches actual filesystem |
| `locate` | Faster | Uses indexed database      |

---

# 📂 5. What does `ls -la` show?

Lists **all files including hidden files** with detailed information.

```bash
ls -la
```

### Flags

* `-l` → Long listing format
* `-a` → Show hidden files (`.` prefixed)

Example output:

```
drwxr-xr-x 2 user user 4096 Jan 10 10:00 documents
-rw-r--r-- 1 user user 120 Jan 10 09:50 file.txt
```

### Information Displayed

* File permissions
* Number of links
* Owner
* Group
* File size
* Last modified date
* File name

---

# 🗑️ 6. How do you safely delete files and directories?

### Delete a file

```bash
rm file.txt
```

### Delete a directory

```bash
rm -r directory_name
```

### Safe deletion with confirmation

```bash
rm -i file.txt
```

### Force delete

```bash
rm -rf directory_name
```

⚠️ **Best Practice:** Use `-i` to prevent accidental deletion.

---

# 📖 7. Difference between `cat`, `more`, and `less`

| Command | Purpose                                |
| ------- | -------------------------------------- |
| `cat`   | Displays entire file content           |
| `more`  | Shows file page by page (forward only) |
| `less`  | Page navigation forward and backward   |

Examples:

```bash
cat file.txt
```

```bash
more file.txt
```

```bash
less file.txt
```

💡 `less` is the **most commonly used** for large files.

---

# 📡 8. How do you monitor a log file in real-time?

Use the **tail command** with the `-f` flag.

```bash
tail -f logfile.log
```

Example:

```bash
tail -f /var/log/syslog
```

`-f` means **follow the file as it grows**, useful for **log monitoring**.

---

# 💻 9. What command shows system information?

Use the `uname` command.

```bash
uname -a
```

Shows:

* Kernel name
* Hostname
* Kernel version
* Architecture
* Operating system

### Other Useful Commands

```bash
hostname
```

```bash
uptime
```

```bash
lscpu
```

```bash
free -h
```

---

# 📂 10. How do you create nested directories in one command?

Use the `mkdir -p` command.

```bash
mkdir -p project/src/components
```

### Directory Structure Created

```
project/
 └── src/
      └── components/
```

Without `-p`, intermediate directories must already exist.

---

# 🚀 Summary

This guide covers essential **Linux fundamentals** including:

* File system hierarchy
* Paths
* File searching
* File viewing
* Log monitoring
* System information commands
* Directory creation

These are **core concepts frequently asked in Linux, DevOps, and system administration interviews**.
