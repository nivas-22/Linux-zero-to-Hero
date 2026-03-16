# 🐧 Day 2: Linux File System Structure

## 📂 Understanding the Linux Directory Hierarchy

---

# 📘 Theory

## Linux File System Hierarchy

In Linux, **everything is treated as a file** — including devices, processes, and system information.

The Linux filesystem begins at the **root directory `/`**, which is the top-level directory of the entire system.

### Directory Tree

```
/
├── home
├── etc
├── var
├── bin
├── usr
├── tmp
├── opt
├── dev
├── proc
└── root
```

---

# 📁 Important Directories

| Directory | Purpose                                     |
| --------- | ------------------------------------------- |
| `/`       | Root directory – top of the filesystem      |
| `/home`   | User home directories                       |
| `/etc`    | System configuration files                  |
| `/var`    | Variable data such as logs, mail, databases |
| `/bin`    | Essential user commands (`ls`, `cp`, `mv`)  |
| `/sbin`   | System administration commands              |
| `/usr`    | User applications and utilities             |
| `/tmp`    | Temporary files (often cleared on reboot)   |
| `/opt`    | Optional or third-party software            |
| `/dev`    | Device files                                |
| `/proc`   | Virtual filesystem containing process info  |
| `/root`   | Root user's home directory                  |

---

# 📍 Absolute vs Relative Paths

## Absolute Path

An **absolute path** starts from the root directory `/`.

Example:

```
/home/raman/documents
```

---

## Relative Path

A **relative path** starts from the **current working directory**.

Examples:

```
./documents
../other
```

---

## Special Path Symbols

| Symbol | Meaning           |
| ------ | ----------------- |
| `.`    | Current directory |
| `..`   | Parent directory  |
| `~`    | Home directory    |

---

# 💻 Command: `ls`

The `ls` command is used to **list directory contents**.

---

# ⚙️ `ls` Command Flags

| Flag      | Description                                          |
| --------- | ---------------------------------------------------- |
| `-l`      | Long listing format (permissions, owner, size, date) |
| `-a`      | Show hidden files                                    |
| `-h`      | Human-readable file sizes                            |
| `-R`      | Recursive listing                                    |
| `-t`      | Sort by modification time                            |
| `-r`      | Reverse sorting order                                |
| `-S`      | Sort by file size                                    |
| `-i`      | Show inode numbers                                   |
| `-d`      | Show directory itself instead of contents            |
| `-1`      | Display one file per line                            |
| `--color` | Colorized output                                     |

---

# 🏋️ Workouts

## Basic Listing

```bash
ls
```

Example output:

```
Desktop  Documents  Downloads  Music  Pictures
```

---

## Long Listing Format

```bash
ls -l
```

Example output:

```
drwxr-xr-x 2 raman raman 4096 Jan 15 10:00 Desktop
drwxr-xr-x 3 raman raman 4096 Jan 14 09:30 Documents
-rw-r--r-- 1 raman raman 1024 Jan 13 15:20 file.txt
```

---

## Show Hidden Files

```bash
ls -la
```

Example output:

```
total 32
drwxr-xr-x 5 raman raman 4096 Jan 15 10:00 .
drwxr-xr-x 3 root  root  4096 Jan 10 08:00 ..
-rw------- 1 raman raman 256 Jan 15 10:00 .bash_history
-rw-r--r-- 1 raman raman 220 Jan 10 08:00 .bashrc
drwxr-xr-x 2 raman raman 4096 Jan 15 10:00 Desktop
```

---

## Human-Readable File Sizes

```bash
ls -lh
```

Example output:

```
-rw-r--r-- 1 raman raman 1.5M Jan 15 10:00 large_file.txt
-rw-r--r-- 1 raman raman 256K Jan 14 09:30 medium_file.txt
```

---

## Sort by Time (Newest First)

```bash
ls -lt
```

Lists files ordered by **latest modified time**.

---

## Sort by File Size

```bash
ls -lS
```

Lists files ordered by **largest size first**.

---

## Recursive Listing

```bash
ls -R
```

Lists **all files and subdirectories recursively**.

---

## List Files in a Specific Directory

```bash
ls -la /etc
```

Useful for exploring **system configuration files**.

---

## Show Directory Information Only

```bash
ls -ld /home
```

Example output:

```
drwxr-xr-x 3 root root 4096 Jan 10 08:00 /home
```

---

# 🚀 Summary

In **Day 2**, you learned:

* The **Linux filesystem hierarchy**
* Important system directories
* **Absolute vs relative paths**
* Special path symbols (`.`, `..`, `~`)
* Advanced usage of the **`ls` command**

These concepts are fundamental for **Linux administration, DevOps, and cloud engineering**.
