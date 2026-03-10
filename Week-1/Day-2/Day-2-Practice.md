# Day 2: Hands-On Practice

## Linux File System Practice Exercises

---

## Exercise 1: List all files including hidden ones

```bash
ls -la
```

---

## Exercise 2: List files with human-readable sizes

```bash
ls -lh
```

---

## Exercise 3: List files sorted by modification time

```bash
ls -lt
```

---

## Exercise 4: List files sorted by size (largest first)

```bash
ls -lS
```

---

## Exercise 5: Explore system directories

List files in `/etc`

```bash
ls -la /etc
```

List files in `/var/log`

```bash
ls -la /var/log
```

List files in `/home`

```bash
ls -la /home
```

---

## Exercise 6: Show directory tree (2 levels)

```bash
tree -L 2 /home
```

If `tree` is not installed:

Ubuntu / Debian

```bash
sudo apt install tree
```

CentOS / RHEL

```bash
sudo yum install tree
```

---

## Exercise 7: List only directories

Using `ls`

```bash
ls -d */
```

Using `tree`

```bash
tree -d
```

---
