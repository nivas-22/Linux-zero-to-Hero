# 🐧 Day 4: Hands-On Practice

## 📂 File Operations Practice Exercises

These exercises help you practice **creating, copying, moving, deleting, and searching files in Linux**.

---

# 🧪 Exercise 1: Create Test Files

Create multiple test files using **brace expansion**.

```bash id="m91gq5"
touch file{1..10}.txt
touch test{a..e}.log
ls
```

### Explanation

* `file{1..10}.txt` → Creates `file1.txt` to `file10.txt`
* `test{a..e}.log` → Creates `testa.log` to `teste.log`

Example output:

```text id="qz1wgr"
file1.txt file2.txt file3.txt ... file10.txt
testa.log testb.log testc.log testd.log teste.log
```

---

# 📦 Exercise 2: Copy Files with Options

Create a backup directory:

```bash id="f9w3kz"
mkdir backup
```

Copy `.txt` files with verbose output:

```bash id="xtzsnj"
cp -v *.txt backup/
```

Copy directories recursively while preserving permissions:

```bash id="76k1j3"
cp -rp project/ project_backup/
```

### Explanation

| Option | Purpose                             |
| ------ | ----------------------------------- |
| `-v`   | Verbose (show copied files)         |
| `-r`   | Recursive copy (for directories)    |
| `-p`   | Preserve permissions and timestamps |

---

# 🚚 Exercise 3: Move and Rename Files

Rename a file:

```bash id="db9s5c"
mv file1.txt renamed_file.txt
```

Move `.log` files to another directory:

```bash id="kpg5ws"
mv -v *.log /tmp/logs/
```

### Explanation

* `mv` → Move or rename files
* `-v` → Show what is being moved

Example output:

```text id="qqsnrw"
renamed 'testa.log' -> '/tmp/logs/testa.log'
```

---

# 🗑 Exercise 4: Safe File Deletion

Remove a file with confirmation:

```bash id="fr0p9h"
rm -i file1.txt
```

Remove directory recursively with verbose output:

```bash id="ejb2ak"
rm -rv backup/
```

### Explanation

| Option | Purpose                  |
| ------ | ------------------------ |
| `-i`   | Interactive confirmation |
| `-r`   | Recursive deletion       |
| `-v`   | Show removed files       |

Example output:

```text id="22k5tr"
removed 'backup/file2.txt'
removed 'backup/file3.txt'
removed directory 'backup/'
```

---

# 🔍 Exercise 5: Find Files with Conditions

Find `.txt` files in `/home`:

```bash id="zuhxci"
find /home -name "*.txt" -type f
```

Find files larger than **1MB**:

```bash id="z5p5x2"
find . -size +1M
```

Find log files modified in the **last day**:

```bash id="3vptwi"
find /var/log -mtime -1
```

### Explanation

| Option      | Meaning                   |
| ----------- | ------------------------- |
| `-name`     | Search by file name       |
| `-type f`   | Only files                |
| `-size +1M` | Files larger than 1MB     |
| `-mtime -1` | Modified in last 24 hours |

---

# ⚡ Exercise 6: Use `locate`

Update the locate database:

```bash id="95zzul"
sudo updatedb
```

Search for files containing `passwd`:

```bash id="we8r1o"
locate -i "passwd"
```

Show only the **first 10 results**:

```bash id="iqo6l1"
locate -n 10 "*.conf"
```

### Explanation

| Option | Meaning                 |
| ------ | ----------------------- |
| `-i`   | Case-insensitive search |
| `-n`   | Limit number of results |

---

# 🚀 Summary

In **Day 4 Hands-On Practice**, you practiced:

* Creating multiple files with `touch`
* Copying files and directories using `cp`
* Moving and renaming files with `mv`
* Safely deleting files using `rm`
* Searching files using `find`
* Performing fast file searches using `locate`

These skills are **fundamental for Linux system administration and DevOps workflows**.
