# 🐧 Day 2: Hands-On Practice

## 📂 Linux File System Practice Exercises

Practice common commands used to **explore and inspect the Linux filesystem**.

---

# 📋 Exercise 1: List All Files (Including Hidden)

```bash
ls -la
```

### Explanation

* `-l` → Long listing format
* `-a` → Show hidden files (files starting with `.`)

Example hidden files:

```
.bashrc
.profile
.git
```

---

# 📊 Exercise 2: List Files with Human-Readable Sizes

```bash
ls -lh
```

### Explanation

* `-l` → Long listing format
* `-h` → Human readable file sizes (`K`, `M`, `G`)

Example output:

```
-rw-r--r-- 1 user user 4.0K Jan 10 notes.txt
-rw-r--r-- 1 user user 2.1M Jan 10 video.mp4
```

---

# 🕒 Exercise 3: List Files Sorted by Modification Time

```bash
ls -lt
```

### Explanation

* `-t` → Sort files by **last modified time**

Newest files appear **first**.

---

# 📦 Exercise 4: List Files Sorted by Size (Largest First)

```bash
ls -lS
```

### Explanation

* `-S` → Sort files by **file size**

Largest files appear **first**.

---

# 🗂️ Exercise 5: Explore System Directories

Linux system directories contain **configuration files, logs, and user data**.

---

## List Files in `/etc`

```bash
ls -la /etc
```

**Purpose**

* Stores **system configuration files**
* Examples:

  * `passwd`
  * `hosts`
  * `ssh/`

---

## List Files in `/var/log`

```bash
ls -la /var/log
```

**Purpose**

* Stores **system logs**
* Useful for troubleshooting

Examples:

```
syslog
auth.log
kern.log
```

---

## List Files in `/home`

```bash
ls -la /home
```

**Purpose**

* Contains **user home directories**

Example structure:

```
/home
 ├── user1
 ├── user2
 └── admin
```

---

# 🌳 Exercise 6: Show Directory Tree (2 Levels)

```bash
tree -L 2 /home
```

### Explanation

* `tree` → Displays directories in **tree structure**
* `-L 2` → Limit display to **2 directory levels**

Example output:

```
/home
├── user1
│   ├── Documents
│   └── Downloads
└── user2
    ├── Desktop
    └── Pictures
```

---

## Install `tree` (If Not Installed)

### Ubuntu / Debian

```bash
sudo apt install tree
```

### CentOS / RHEL

```bash
sudo yum install tree
```

---

# 📁 Exercise 7: List Only Directories

## Using `ls`

```bash
ls -d */
```

### Explanation

* `-d` → List directories themselves
* `*/` → Matches only directories

---

## Using `tree`

```bash
tree -d
```

### Explanation

* `-d` → Display **directories only**

Example output:

```
.
├── documents
├── downloads
└── projects
```

---

# 🚀 Summary

In **Day 2**, you practiced:

* Listing files with different `ls` options
* Sorting files by **time and size**
* Exploring important system directories
* Visualizing directory structures with `tree`
* Listing directories only

These commands are **commonly used by Linux administrators and DevOps engineers** when navigating and managing systems.
