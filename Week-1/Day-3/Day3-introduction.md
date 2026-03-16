# 🐧 Day 3: Directory Operations

## 📂 Creating, Navigating, and Managing Directories

In this lesson you will learn how to **create, navigate, inspect, and remove directories** using common Linux commands.

---

# 📌 Commands Covered

| Command | Purpose                               |
| ------- | ------------------------------------- |
| `mkdir` | Create directories                    |
| `rmdir` | Remove empty directories              |
| `cd`    | Change directory                      |
| `stat`  | Display file or directory information |

---

# 📁 `mkdir` Command

The `mkdir` command is used to **create new directories**.

## Common Flags

| Flag      | Description                                    |
| --------- | ---------------------------------------------- |
| `-p`      | Create parent directories if they do not exist |
| `-v`      | Verbose output (shows created directories)     |
| `-m MODE` | Set directory permission mode                  |

---

# 📂 `cd` Command Usage

| Command    | Description                  |
| ---------- | ---------------------------- |
| `cd`       | Go to home directory         |
| `cd ~`     | Go to home directory         |
| `cd -`     | Switch to previous directory |
| `cd ..`    | Move to parent directory     |
| `cd ../..` | Move up two directory levels |
| `cd /path` | Navigate using absolute path |
| `cd ./dir` | Navigate using relative path |

---

# 🛠 mkdir Examples

## Create Single Directory

```bash
mkdir projects
ls
```

Example output:

```
projects
```

---

## Create Multiple Directories

```bash
mkdir dir1 dir2 dir3
ls
```

Example output:

```
dir1 dir2 dir3 projects
```

---

## Create Nested Directories

```bash
mkdir -p projects/webapp/src/main
tree projects
```

Example structure:

```
projects
└── webapp
    └── src
        └── main
```

---

## Create Directories with Verbose Output

```bash
mkdir -v test1 test2
```

Example output:

```
mkdir: created directory 'test1'
mkdir: created directory 'test2'
```

---

## Create Directories with Specific Permissions

```bash
mkdir -m 755 public_folder
mkdir -m 700 private_folder
ls -l
```

Example output:

```
drwxr-xr-x 2 nivas nivas 4096 Jan 15 10:00 public_folder
drwx------ 2 nivas nivas 4096 Jan 15 10:00 private_folder
```

---

## Create Complex Directory Structure

```bash
mkdir -pv project/{src,bin,docs,tests}
```

Example output:

```
mkdir: created directory 'project'
mkdir: created directory 'project/src'
mkdir: created directory 'project/bin'
mkdir: created directory 'project/docs'
mkdir: created directory 'project/tests'
```

---

# 🗑 rmdir Examples

## Remove an Empty Directory

```bash
rmdir empty_folder
```

---

## Remove with Verbose Output

```bash
rmdir -v test_dir
```

Example output:

```
rmdir: removing directory 'test_dir'
```

---

## Remove Nested Empty Directories

```bash
mkdir -p a/b/c
rmdir -pv a/b/c
```

Example output:

```
rmdir: removing directory 'a/b/c'
rmdir: removing directory 'a/b'
rmdir: removing directory 'a'
```

---

## Error When Directory Is Not Empty

```bash
rmdir documents
```

Example output:

```
rmdir: failed to remove 'documents': Directory not empty
```

---

# 🧭 cd Examples

## Go to Home Directory

```bash
cd
pwd
```

Example output:

```
/home/nivas
```

---

## Alternative Home Directory Command

```bash
cd ~
pwd
```

Example output:

```
/home/nivas
```

---

## Go to Specific Directory

```bash
cd /var/log
pwd
```

Example output:

```
/var/log
```

---

## Go to Parent Directory

```bash
cd ..
pwd
```

Example output:

```
/var
```

---

## Move Up Two Levels

```bash
cd ../..
pwd
```

Example output:

```
/
```

---

## Go to Previous Directory

```bash
cd /etc
cd /var/log
cd -
```

Example output:

```
/etc
```

---

## Relative Path Examples

```bash
cd ~/Documents
cd ./projects
cd ../Downloads
```

---

# 🔍 `stat` Command

The `stat` command displays **detailed information about files or directories**.

---

## Basic Example

```bash
stat file.txt
```

Example output:

```
File: file.txt
Size: 1024
Blocks: 8
IO Block: 4096 regular file
Device: 801h
Inode: 1234567
Links: 1
Access: (0644/-rw-r--r--)
Uid: (1000/nivas)
Gid: (1000/nivas)
```

---

# ⚙ Custom `stat` Format Examples

## Show File Size

```bash
stat -c "%n : %s bytes" file.txt
```

Example output:

```
file.txt : 1024 bytes
```

---

## Show Owner and Group

```bash
stat -c "Owner: %U, Group: %G" file.txt
```

Example output:

```
Owner: nivas, Group: nivas
```

---

## Show Permissions

```bash
stat -c "Permissions: %a (%A)" file.txt
```

Example output:

```
Permissions: 644 (-rw-r--r--)
```

---

# 📂 stat for a Directory

```bash
stat /home/nivas
```

Example output:

```
File: /home/nivas
Size: 4096
Blocks: 8
IO Block: 4096 directory
```

---

# 🚀 Summary

In **Day 3**, you learned how to:

* Create directories using `mkdir`
* Remove empty directories using `rmdir`
* Navigate directories using `cd`
* Inspect files and directories using `stat`

These commands are **fundamental for Linux administration, DevOps workflows, and system troubleshooting**.
