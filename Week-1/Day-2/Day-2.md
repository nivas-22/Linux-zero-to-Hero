# Day 2: Linux File System Structure

## Understanding the Linux Directory Hierarchy

---

# Theory

## Linux File System Hierarchy

Everything in Linux is a file — even **devices and processes**.

The Linux file system starts from the **root directory `/`**.

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

# Important Directories

| Directory | Purpose |
|---|---|
| `/` | Root directory – top of file system |
| `/home` | User home directories |
| `/etc` | System configuration files |
| `/var` | Variable data (logs, mail, databases) |
| `/bin` | Essential user binaries (`ls`, `cp`, `mv`) |
| `/sbin` | System binaries (administration commands) |
| `/usr` | User programs and application data |
| `/tmp` | Temporary files (cleared on reboot) |
| `/opt` | Optional or third-party software |
| `/dev` | Device files |
| `/proc` | Process information (virtual filesystem) |
| `/root` | Root user home directory |

---

# Absolute vs Relative Paths

### Absolute Path
Starts from the root `/`

Example

```
/home/raman/documents
```

### Relative Path
Starts from the **current directory**

Examples

```
./documents
../other
```

### Special Symbols

| Symbol | Meaning |
|---|---|
| `.` | Current directory |
| `..` | Parent directory |
| `~` | Home directory |

---

# Command

## ls — List Directory Contents

---

# ls Flags

| Flag | Description |
|---|---|
| `-l` | Long format (permissions, owner, size, date) |
| `-a` | Show hidden files |
| `-h` | Human readable sizes |
| `-R` | Recursive listing |
| `-t` | Sort by time |
| `-r` | Reverse order |
| `-S` | Sort by size |
| `-i` | Show inode numbers |
| `-d` | Show directory itself |
| `-1` | One file per line |
| `--color` | Colorized output |

---

# Workouts

## Basic Listing

```bash
ls
```

Example output

```
Desktop  Documents  Downloads  Music  Pictures
```

---

## Long Listing Format

```bash
ls -l
```

Example

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

Example

```
total 32
drwxr-xr-x 5 raman raman 4096 Jan 15 10:00 .
drwxr-xr-x 3 root  root  4096 Jan 10 08:00 ..
-rw------- 1 raman raman 256 Jan 15 10:00 .bash_history
-rw-r--r-- 1 raman raman 220 Jan 10 08:00 .bashrc
drwxr-xr-x 2 raman raman 4096 Jan 15 10:00 Desktop
```

---

## Human Readable File Sizes

```bash
ls -lh
```

Example

```
-rw-r--r-- 1 raman raman 1.5M Jan 15 10:00 large_file.txt
-rw-r--r-- 1 raman raman 256K Jan 14 09:30 medium_file.txt
```

---

## Sort by Time (Newest First)

```bash
ls -lt
```

---

## Sort by File Size

```bash
ls -lS
```

---

## Recursive Listing

```bash
ls -R
```

Lists all files and subdirectories.

---

## List Files in Specific Directory

```bash
ls -la /etc
```

---

## Show Directory Information Only

```bash
ls -ld /home
```

Example

```
drwxr-xr-x 3 root root 4096 Jan 10 08:00 /home
```

---
