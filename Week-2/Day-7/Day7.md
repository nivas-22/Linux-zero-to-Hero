### DAY 7: Ownership & Users Basics
Managing File Ownership


# 👤 File Ownership in Linux
📖 Theory

In Linux, every file and directory has two ownership attributes:

🔑 Ownership Types

| Type           | Description                  |
| -------------- | ---------------------------- |
| 👤 User Owner  | The user who owns the file   |
| 👥 Group Owner | The group that owns the file |

---

🧾 When You Create a File

When a new file is created:

 - 👤 User Owner → Your username

 - 👥 Group Owner → Your primary group

 🔍 Example
 
```
 ls -l file.txt
```

## 🧠 Understanding the Output

```
-rw-r--r-- 1 raman developers 1024 Jan 15 10:00 file.txt
                |       |
                |       +--> 👥 Group Owner (developers)
                +----------> 👤 User Owner (raman)
```

## Examples

```
# Change owner only
$ sudo chown john file . txt

$ ls -l file . txt
-rw -r --r -- 1 john raman 1024 Jan 15 10:00 file . txt

# Change owner and group
$ sudo chown john : developers file . txt
$ ls -l file . txt
-rw -r --r -- 1 john developers 1024 Jan 15 10:00 file . txt

# Change group only ( note the colon )
$ sudo chown : developers file . txt
$ ls -l file . txt
-rw -r --r -- 1 raman developers 1024 Jan 15 10:00 file . txt

# Recursive change for directory
$ sudo chown -R www - data : www - data / var / www / html /

# Verbose output
$ sudo chown -v john : staff file . txt
changed ownership of ’ file . txt ’ from raman : raman to john : staff

# Use reference file
$ sudo chown -- reference = file1 . txt file2 . txt

# Change multiple files
$ sudo chown john : developers *. txt

# Change only if current owner matches
$ sudo chown -- from = raman john file . txt

```
---
