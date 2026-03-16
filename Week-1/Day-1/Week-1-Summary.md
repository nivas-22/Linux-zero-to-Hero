# 🐧 Linux Basic Commands Cheat Sheet

A quick reference guide for commonly used **Linux terminal commands**.

---

# 📂 File & Directory Navigation

| Command  | Purpose                                 | Example     |
| -------- | --------------------------------------- | ----------- |
| `whoami` | Show current logged-in user             | `whoami`    |
| `pwd`    | Show current working directory          | `pwd -P`    |
| `cd`     | Change directory                        | `cd ~`      |
| `ls`     | List files and directories              | `ls -la`    |
| `tree`   | Show directory structure in tree format | `tree -L 2` |

### Example

```bash
pwd
cd ~/Documents
ls -la
```

---

# 📅 System Information Commands

| Command    | Purpose                    | Example            |
| ---------- | -------------------------- | ------------------ |
| `date`     | Display or set system date | `date +"%Y-%m-%d"` |
| `uname`    | Show system information    | `uname -a`         |
| `hostname` | Display system hostname    | `hostname -I`      |

### Example

```bash
date +"%Y-%m-%d"
uname -r
hostname -I
```

---

# 📁 File and Directory Management

| Command | Purpose                               | Example                |
| ------- | ------------------------------------- | ---------------------- |
| `mkdir` | Create directory                      | `mkdir -p project/src` |
| `rmdir` | Remove empty directory                | `rmdir -p dir`         |
| `touch` | Create empty file or update timestamp | `touch file.txt`       |
| `stat`  | Show detailed file information        | `stat file.txt`        |

### Example

```bash
mkdir -p project/src
touch file.txt
stat file.txt
```

---

# 📦 File Operations

| Command | Purpose                     | Example                 |
| ------- | --------------------------- | ----------------------- |
| `cp`    | Copy files or directories   | `cp -rp src/ dest/`     |
| `mv`    | Move or rename files        | `mv -v old.txt new.txt` |
| `rm`    | Delete files or directories | `rm -ri folder/`        |

### Example

```bash
cp file.txt backup/
mv old.txt new.txt
rm -ri folder/
```

---

# 🔍 File Searching

| Command  | Purpose                         | Example                |
| -------- | ------------------------------- | ---------------------- |
| `find`   | Search files in directories     | `find . -name "*.txt"` |
| `locate` | Fast file search using database | `locate -i file`       |

### Example

```bash
find . -name "*.log"
locate -i report
```

---

# 📖 File Viewing Commands

| Command | Purpose                       | Example            |
| ------- | ----------------------------- | ------------------ |
| `cat`   | Display file contents         | `cat -n file.txt`  |
| `tac`   | Display file in reverse order | `tac file.txt`     |
| `more`  | View file page by page        | `more file.txt`    |
| `less`  | Advanced file viewer          | `less -N file.txt` |

### Example

```bash
cat file.txt
less -N file.txt
```

---

# 📊 Viewing Parts of Files

| Command | Purpose                  | Example             |
| ------- | ------------------------ | ------------------- |
| `head`  | Show first lines of file | `head -20 file.txt` |
| `tail`  | Show last lines of file  | `tail -f logfile`   |

### Example

```bash
head -10 file.txt
tail -f /var/log/syslog
```

---

# 🚀 Quick Summary

This cheat sheet covers essential Linux commands for:

* 📂 Navigation
* 📁 File management
* 🔍 File searching
* 📖 File viewing
* 📊 Log monitoring
* 💻 System information

These commands are **commonly used by Linux administrators, developers, and DevOps engineers**.
