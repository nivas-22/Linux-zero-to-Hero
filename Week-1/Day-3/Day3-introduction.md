# Day 3: Directory Operations

Creating, Navigating, and Managing Directories

---

# Commands

1. `mkdir` – Make directories  
2. `rmdir` – Remove empty directories  
3. `cd` – Change directory  
4. `stat` – Display file/directory status  

---

# mkdir Flags

| Flag | Description |
|---|---|
| `-p` | Create parent directories as needed |
| `-v` | Verbose – show message for each created directory |
| `-m MODE` | Set permission mode |

---

# cd Usage

| Command | Description |
|---|---|
| `cd` | Go to home directory |
| `cd ~` | Go to home directory |
| `cd -` | Go to previous directory |
| `cd ..` | Go to parent directory |
| `cd ../..` | Go up two levels |
| `cd /path` | Go to absolute path |
| `cd ./dir` | Go to relative path |

---

# mkdir Examples

## Create single directory

```bash
mkdir projects
ls
```

Output

```
projects
```

---

## Create multiple directories

```bash
mkdir dir1 dir2 dir3
ls
```

Output

```
dir1 dir2 dir3 projects
```

---

## Create nested directories

```bash
mkdir -p projects/webapp/src/main
tree projects
```

Example

```
projects
└── webapp
    └── src
        └── main
```

---

## Create with verbose output

```bash
mkdir -v test1 test2
```

Output

```
mkdir: created directory 'test1'
mkdir: created directory 'test2'
```

---

## Create with specific permissions

```bash
mkdir -m 755 public_folder
mkdir -m 700 private_folder
ls -l
```

Example

```
drwxr-xr-x 2 raman raman 4096 Jan 15 10:00 public_folder
drwx------ 2 raman raman 4096 Jan 15 10:00 private_folder
```

---

## Create complex directory structure

```bash
mkdir -pv project/{src,bin,docs,tests}
```

Output

```
mkdir: created directory 'project'
mkdir: created directory 'project/src'
mkdir: created directory 'project/bin'
mkdir: created directory 'project/docs'
mkdir: created directory 'project/tests'
```

---

# rmdir Examples

## Remove empty directory

```bash
rmdir empty_folder
```

---

## Remove with verbose output

```bash
rmdir -v test_dir
```

Output

```
rmdir: removing directory 'test_dir'
```

---

## Remove nested empty directories

```bash
mkdir -p a/b/c
rmdir -pv a/b/c
```

Output

```
rmdir: removing directory 'a/b/c'
rmdir: removing directory 'a/b'
rmdir: removing directory 'a'
```

---

## Error when directory not empty

```bash
rmdir documents
```

Output

```
rmdir: failed to remove 'documents': Directory not empty
```

---

# cd Examples

## Go to home directory

```bash
cd
pwd
```

Output

```
/home/raman
```

---

## Go to home directory (alternative)

```bash
cd ~
pwd
```

Output

```
/home/raman
```

---

## Go to specific directory

```bash
cd /var/log
pwd
```

Output

```
/var/log
```

---

## Go to parent directory

```bash
cd ..
pwd
```

Output

```
/var
```

---

## Go up two levels

```bash
cd ../..
pwd
```

Output

```
/
```

---

## Go to previous directory

```bash
cd /etc
cd /var/log
cd -
```

Output

```
/etc
```

---

## Relative path examples

```bash
cd ~/Documents
cd ./projects
cd ../Downloads
```

---

# stat Command

Display detailed file or directory information.

## Basic Example

```bash
stat file.txt
```

Example Output

```
File: file.txt
Size: 1024
Blocks: 8
IO Block: 4096 regular file
Device: 801h
Inode: 1234567
Links: 1
Access: (0644/-rw-r--r--)
Uid: (1000/raman)
Gid: (1000/raman)
```

---

# Custom stat Format Examples

## Show file size

```bash
stat -c "%n : %s bytes" file.txt
```

Output

```
file.txt : 1024 bytes
```

---

## Show owner and group

```bash
stat -c "Owner: %U, Group: %G" file.txt
```

Output

```
Owner: raman, Group: raman
```

---

## Show permissions

```bash
stat -c "Permissions: %a (%A)" file.txt
```

Output

```
Permissions: 644 (-rw-r--r--)
```

---

# stat for Directory

```bash
stat /home/raman
```

Example Output

```
File: /home/raman
Size: 4096
Blocks: 8
IO Block: 4096 directory
```

---
