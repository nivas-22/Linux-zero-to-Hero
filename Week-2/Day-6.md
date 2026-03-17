### 🗂️ Day 6: File Permissions

# Understanding and Managing File Permissions


### 📖 Theory: Linux Permission System

Every file and directory in Linux has three types of permissions for three categories of users.

🔑 Permission Types

| Symbol | Permission | File Action     | Directory Action     |
| ------ | ---------- | --------------- | -------------------- |
| r      | Read       | View contents   | List contents        |
| w      | Write      | Modify contents | Create/delete files  |
| x      | Execute    | Run as program  | Enter directory (cd) |
| -      | None       | Cannot access   | Cannot access        |


---

### 👥 User Categories

| Symbol | User Category                 |
| ------ | ----------------------------- |
| u      | User (owner of the file)      |
| g      | Group (users in file’s group) |
| o      | Others (everyone else)        |
| a      | All (user + group + others)   |

---


# 📜 Reading Permission String

```copy
-rwxr-xr--
|\_/\_/\_/
| | | |
| | | +-- Others: r-- (read only)
| | +-- Group: r-x (read + execute)
| +-- User: rwx (read + write + execute)
+-- File type: - (regular file)
```

---

# 🔢 Permission Reference

Numeric (Octal) Permissions

| Permission | Numeric Value |
| ---------- | ------------- |
| r          | 4             |
| w          | 2             |
| x          | 1             |
| -          | 0             |

---
Common Numeric Combinations

| Numeric | Symbolic | Meaning                |
| ------- | -------- | ---------------------- |
| 7       | rwx      | Read + Write + Execute |
| 6       | rw-      | Read + Write           |
| 5       | r-x      | Read + Execute         |
| 4       | r--      | Read only              |
| 3       | -wx      | Write + Execute        |
| 2       | -w-      | Write only             |
| 1       | --x      | Execute only           |
| 0       | ---      | No permissions         |

---
Common Permission Sets:

| Octal | Symbolic  | Use Case                      |
| ----- | --------- | ----------------------------- |
| 755   | rwxr-xr-x | Executable files, directories |
| 644   | rw-r--r-- | Regular files                 |
| 700   | rwx------ | Private files                 |
| 777   | rwxrwxrwx | Full access – dangerous!      |

---
## 🛠️ chmod – Change File Mode/Permissions


⚙️ Flags & Options

| Flag             | Description                                      |
| ---------------- | ------------------------------------------------ |
| -R               | Recursive – apply to directories & contents      |
| -v               | Verbose – show files being changed               |
| -c               | Like verbose but report only if changes are made |
| -f               | Silent – suppress error messages                 |
| --reference=FILE | Use FILE’s permissions as reference              |

---
🔹 Symbolic Mode Operators

| Operator | Description                           |
| -------- | ------------------------------------- |
| +        | Add permission                        |
| -        | Remove permission                     |
| =        | Set exact permission (removes others) |

# 💡 Examples
# Numeric Mode

```bash
# Give owner full, group read+execute, others read
chmod 754 script.sh
ls -l script.sh

# Private file – only owner can access
chmod 700 private.txt

# Standard file permissions
chmod 644 document.txt

# Full permissions (DANGEROUS!)
chmod 777 shared_file.txt

# Apply recursively to directory
chmod -R 755 project/
```

Symbolic Mode

```bash

# Add execute permission for owner
chmod u+x script.sh

# Remove write permission for group and others
chmod go-w file.txt

# Add read permission for all
chmod a+r file.txt

# Set exact permissions
chmod u=rwx,g=rx,o=r file.txt

# Make file executable by everyone
chmod +x script.sh

# Copy permissions from another file
chmod --reference=file1.txt file2.txt

# Verbose output
chmod -v 755 script.sh

```
---
