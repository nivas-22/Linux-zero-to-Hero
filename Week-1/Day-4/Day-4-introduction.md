# 🐧 Day 4: File Operations

## 📂 Creating, Copying, Moving, and Deleting Files

This lesson covers essential Linux commands used to **manage files and directories**.

---

# 📌 Commands Covered

| Command  | Purpose                                 |
| -------- | --------------------------------------- |
| `touch`  | Create empty files or update timestamps |
| `cp`     | Copy files and directories              |
| `mv`     | Move or rename files and directories    |
| `rm`     | Remove files and directories            |
| `find`   | Search files in real-time               |
| `locate` | Fast file search using a database       |

---

# ✏️ Rename and Move Files / Directories

## Rename a File

```bash
mv oldname.txt newname.txt
```

---

## Move File to a Directory

```bash
mv file.txt /home/raman/Documents/
```

---

## Move Multiple Files

```bash
mv file1.txt file2.txt file3.txt backup/
```

---

## Rename a Directory

```bash
mv old_folder new_folder
```

---

## Move with Verbose Output

```bash
mv -v file.txt /tmp/
```

Example output:

```text
renamed 'file.txt' -> '/tmp/file.txt'
```

---

## Interactive Mode (Confirm Before Overwrite)

```bash
mv -i file.txt existing.txt
```

---

## Do Not Overwrite Existing Files

```bash
mv -n file.txt existing.txt
```

---

## Backup Before Overwriting

```bash
mv -b file.txt existing.txt
```

---

## Move Using Wildcards

```bash
mv *.log /var/log/archive/
```

---

# 🗑 Remove Files / Directories

## Remove Single File

```bash
rm file.txt
```

---

## Remove Multiple Files

```bash
rm file1.txt file2.txt file3.txt
```

---

## Remove with Confirmation

```bash
rm -i important_file.txt
```

Example output:

```text
rm: remove regular file 'important_file.txt'? y
```

---

## Remove Directory and Contents

```bash
rm -r folder/
```

Force delete without prompts:

```bash
rm -rf folder/
```

---

## Verbose Removal

```bash
rm -rv project/
```

Example output:

```text
removed 'project/file1.txt'
removed 'project/file2.txt'
removed directory 'project/'
```

---

## Remove Files Matching a Pattern

```bash
rm *.tmp
rm *.log
```

---

## Remove Empty Directory

```bash
rm -d empty_folder/
```

---

## Safe Recursive Delete (Prompt Once)

```bash
rm -rI large_folder/
```

---

# ⚠️ Dangerous Commands

Be extremely careful when using `rm -rf`.

Never run the following commands:

```bash
rm -rf /
rm -rf /*
rm -rf ~
rm -rf .
```

These commands can **delete critical parts of your system**.

✅ **Best Practice**

Use safer options:

```bash
rm -ri
```

---

# 🔍 `find` Command Examples

## Find by Name

```bash
find /home -name "*.txt"
find . -name "config.yml"
find / -iname "readme*"
```

`-iname` performs **case-insensitive search**.

---

## Find by Type

```bash
find /var -type f -name "*.log"
find /etc -type d -name "ssh"
```

| Type | Meaning   |
| ---- | --------- |
| `f`  | File      |
| `d`  | Directory |

---

## Find by File Size

```bash
find / -size +100M
find /home -size -1k
find . -size +10M -size -50M
```

---

## Find by Modification Time

```bash
find /var/log -mtime -7
find . -mtime +30
find . -mmin -60
```

---

## Find by Owner or Group

```bash
find /home -user raman
find /var -group www-data
```

---

## Find by Permissions

```bash
find / -perm 777
find /home -perm -u=w
```

---

## Find Empty Files or Directories

```bash
find . -empty
find . -type f -empty
find . -type d -empty
```

---

## Limit Search Depth

```bash
find . -maxdepth 2 -name "*.txt"
```

---

## Execute Commands on Results

```bash
find . -name "*.tmp" -exec rm {} \;
find . -name "*.log" -exec mv {} /backup/ \;
find . -type f -exec chmod 644 {} \;
```

---

## Combine Multiple Conditions

```bash
find /var -type f -name "*.log" -size +10M -mtime +7
```

---

# ⚡ `locate` Command Examples

First update the locate database:

```bash
sudo updatedb
```

Then search files:

```bash
locate passwd
locate -i README
locate -n 5 "*.conf"
locate -c "*.log"
locate -b passwd
```

---

# 🔄 Find vs Locate

| Command  | Description                                              |
| -------- | -------------------------------------------------------- |
| `find`   | Real-time filesystem search (slower but always accurate) |
| `locate` | Uses indexed database (very fast but may be outdated)    |

Update the locate database regularly:

```bash
sudo updatedb
```

---

# 📊 Common `find` Options

| Option             | Description                      |
| ------------------ | -------------------------------- |
| `-name "pattern"`  | Search by filename               |
| `-iname "pattern"` | Case-insensitive filename search |
| `-type f`          | Find files                       |
| `-type d`          | Find directories                 |
| `-type l`          | Find symbolic links              |
| `-size +10M`       | Files larger than 10MB           |
| `-size -10M`       | Files smaller than 10MB          |
| `-mtime -7`        | Modified in last 7 days          |
| `-mtime +30`       | Modified more than 30 days ago   |
| `-user username`   | Files owned by a specific user   |
| `-perm 644`        | Files with specific permissions  |
| `-empty`           | Find empty files or directories  |
| `-maxdepth n`      | Limit search depth               |
| `-exec cmd {} \;`  | Execute command on results       |

---

# 🚀 Summary

In **Day 4**, you learned how to:

* Create files using `touch`
* Copy files with `cp`
* Move or rename files using `mv`
* Delete files and directories using `rm`
* Search files using `find`
* Perform fast searches using `locate`

These commands are **essential for Linux administration, DevOps tasks, and system troubleshooting**.
