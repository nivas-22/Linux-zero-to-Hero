# Day 4: File Operations

Creating, Copying, Moving, and Deleting Files

---

## Commands

1. `touch` – Create empty files / update timestamps  
2. `cp` – Copy files and directories  
3. `mv` – Move / rename files and directories  
4. `find` – Search for files  
5. `locate` – Fast file search (uses database)  

---

## Rename and Move Files / Directories

### Rename a file

```bash
mv oldname.txt newname.txt
```

### Move file to directory

```bash
mv file.txt /home/raman/Documents/
```

### Move multiple files

```bash
mv file1.txt file2.txt file3.txt backup/
```

### Rename a directory

```bash
mv old_folder new_folder
```

### Move with verbose

```bash
mv -v file.txt /tmp/
```

Output:

```
renamed 'file.txt' -> '/tmp/file.txt'
```

### Interactive mode (confirm before overwrite)

```bash
mv -i file.txt existing.txt
```

### Don’t overwrite existing files

```bash
mv -n file.txt existing.txt
```

### Backup before overwrite

```bash
mv -b file.txt existing.txt
```

### Move using wildcards

```bash
mv *.log /var/log/archive/
```

---

## Remove Files / Directories

### Remove single file

```bash
rm file.txt
```

### Remove multiple files

```bash
rm file1.txt file2.txt file3.txt
```

### Remove with confirmation

```bash
rm -i important_file.txt
```

Output:

```
rm: remove regular file 'important_file.txt'? y
```

### Remove directory and contents

```bash
rm -r folder/
rm -rf folder/   # Force, no prompts
```

### Verbose removal

```bash
rm -rv project/
```

Output:

```
removed 'project/file1.txt'
removed 'project/file2.txt'
removed directory 'project/'
```

### Remove files matching pattern

```bash
rm *.tmp
rm *.log
```

### Remove empty directory

```bash
rm -d empty_folder/
```

### Safe recursive delete (prompt once)

```bash
rm -rI large_folder/
```

---

⚠️ **DANGER**: Be extremely careful with `rm -rf`!  
**Never run these commands**:

```bash
rm -rf /       # Deletes ENTIRE system
rm -rf /*      # Deletes everything
rm -rf ~       # Deletes home directory
rm -rf .       # Deletes current directory
```

✅ **Best practice:** Use `rm -ri` for important deletions.

---

## Find Command Examples

### Find by name

```bash
find /home -name "*.txt"
find . -name "config.yml"
find / -iname "readme*"    # Case-insensitive
```

### Find by type

```bash
find /var -type f -name "*.log"
find /etc -type d -name "ssh"
```

### Find by size

```bash
find / -size +100M        # Larger than 100MB
find /home -size -1k      # Smaller than 1KB
find . -size +10M -size -50M   # Between 10-50MB
```

### Find by modification time

```bash
find /var/log -mtime -7   # Modified in last 7 days
find . -mtime +30         # Modified more than 30 days ago
find . -mmin -60          # Modified in last 60 minutes
```

### Find by owner/group

```bash
find /home -user raman
find /var -group www-data
```

### Find by permissions

```bash
find / -perm 777
find /home -perm -u=w     # User has write permission
```

### Find empty files / directories

```bash
find . -empty
find . -type f -empty
find . -type d -empty
```

### Limit search depth

```bash
find . -maxdepth 2 -name "*.txt"
```

### Execute command on results

```bash
find . -name "*.tmp" -exec rm {} \;
find . -name "*.log" -exec mv {} /backup/ \;
find . -type f -exec chmod 644 {} \;
```

### Combined conditions

```bash
find /var -type f -name "*.log" -size +10M -mtime +7
```

---

## Locate Command Examples

```bash
sudo updatedb             # Update database first (run as root)
locate passwd
locate -i README          # Case-insensitive
locate -n 5 "*.conf"      # Limit results to 5
locate -c "*.log"         # Count matches
locate -b passwd          # Show basename only
```

---

## Find vs Locate

| Command | Description |
|---|---|
| `find` | Real-time search, slower but always current |
| `locate` | Uses database, very fast but may be outdated (run `sudo updatedb` to refresh) |

---

## Common Find Options

| Option | Description |
|---|---|
| `-name "pattern"` | Search by filename (case-sensitive) |
| `-iname "pattern"` | Search by name (case-insensitive) |
| `-type f` | Find only files |
| `-type d` | Find only directories |
| `-type l` | Find only symbolic links |
| `-size +10M` | Files larger than 10MB |
| `-size -10M` | Files smaller than 10MB |
| `-mtime -7` | Modified in the last 7 days |
| `-mtime +30` | Modified more than 30 days ago |
| `-user username` | Files owned by user |
| `-perm 644` | Files with specific permissions |
| `-empty` | Find empty files/directories |
| `-maxdepth n` | Limit search depth |
| `-exec cmd {} \;` | Execute command on results |

---
