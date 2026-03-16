# 🐧 Day 3: Hands-On Practice

## 📂 Directory Operations Practice Exercises

In this session, you will practice **creating, navigating, and managing directories** in Linux.

---

# 📁 Exercise 1: Create a Project Structure

Create a sample project directory with multiple folders.

```bash
mkdir -pv ~/myproject/{src,bin,docs,tests,config}
```

View the directory structure:

```bash
tree ~/myproject
```

### Explanation

* `-p` → Create parent directories if they do not exist
* `-v` → Show verbose output (display created directories)
* `{}` → Create multiple directories at once

Example structure:

```
myproject
├── bin
├── config
├── docs
├── src
└── tests
```

---

# 🧭 Exercise 2: Navigate Using Different Methods

Move between directories and verify location.

```bash
cd ~/myproject/src
pwd
```

Move to the **parent directory**:

```bash
cd ..
pwd
```

Return to the **previous directory**:

```bash
cd -
pwd
```

### Explanation

| Command | Purpose                        |
| ------- | ------------------------------ |
| `cd`    | Change directory               |
| `cd ..` | Move to parent directory       |
| `cd -`  | Return to previous directory   |
| `pwd`   | Show current working directory |

---

# 📦 Exercise 3: Create and Remove Empty Directories

Create multiple directories:

```bash
mkdir -v temp1 temp2 temp3
```

Remove empty directories:

```bash
rmdir -v temp1 temp2 temp3
```

### Explanation

* `mkdir` → Create directories
* `rmdir` → Remove empty directories only
* `-v` → Verbose output

---

# 🌳 Exercise 4: Create Nested Directories and Remove Them

Create nested directories:

```bash
mkdir -pv a/b/c/d/e
```

Remove nested directories:

```bash
rmdir -pv a/b/c/d/e
```

### Explanation

* `-p` allows creating **multiple directory levels in one command**
* `rmdir -p` removes directories **recursively if they are empty**

Example structure created:

```
a
└── b
    └── c
        └── d
            └── e
```

---

# 🔎 Exercise 5: Check File or Directory Status

Display detailed file information:

```bash
stat /etc/passwd
```

Display custom formatted output:

```bash
stat -c "%n : %a permissions, %U owner" /etc/passwd
```

### Explanation

| Option | Purpose            |
| ------ | ------------------ |
| `stat` | Show file metadata |
| `%n`   | File name          |
| `%a`   | File permissions   |
| `%U`   | File owner         |

Example output:

```
/etc/passwd : 644 permissions, root owner
```

---

# 🔐 Exercise 6: Create Directories with Specific Permissions

Create directories with different permission levels:

```bash
mkdir -m 755 public
mkdir -m 700 private
```

Check permissions:

```bash
ls -ld public private
```

### Explanation

| Permission | Meaning                                  |
| ---------- | ---------------------------------------- |
| `755`      | Owner full access, others read & execute |
| `700`      | Only owner has full access               |

Example output:

```
drwxr-xr-x 2 user user 4096 public
drwx------ 2 user user 4096 private
```

---

# 🚀 Summary

In **Day 3**, you practiced:

* Creating directory structures with `mkdir`
* Navigating directories using `cd`
* Removing empty directories with `rmdir`
* Creating nested directories
* Checking file metadata with `stat`
* Setting directory permissions

These operations are **essential for Linux system administration and DevOps workflows**.
