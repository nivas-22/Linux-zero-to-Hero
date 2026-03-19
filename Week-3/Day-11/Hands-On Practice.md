## Exercise 1: Update and Install (Ubuntu)

```copy
$ sudo apt - get update
$ apt - cache search htop
$ sudo apt - get install htop
$ htop -- version
$ apt - cache show htop
$ dpkg -L htop
```

---

## Exercise 2: Query Packages

```copy
# Ubuntu
$ dpkg -l | grep -i apache
$ dpkg -S / usr / bin / wget
# CentOS
$ rpm - qa | grep -i http
$ rpm - qf / usr / bin / wget
```
---

## Exercise 3: Clean Up

```copy
$ sudo apt - get remove htop
$ sudo apt - get autoremove
$ sudo apt - get clean
```
---

## 🎯 Interview Questions

**❓ Q1: What is the difference between apt-get remove and apt-get purge?**

remove uninstalls the package but keeps configuration files for future reuse.
purge removes the package along with all its configuration files completely.

**❓ Q2: What is the difference between yum and dnf?**

dnf is the next-generation replacement for yum.

It provides:

Better dependency resolution
Improved performance
Cleaner and modern codebase
Most commands are compatible between yum and dnf.
dnf is the default on Fedora, CentOS 8+, and RHEL 8+.

**Q: How do you find which package provides a specific file?**
On Debian/Ubuntu: dpkg -S /path/to/file
On RHEL/CentOS: rpm -qf /path/to/file or yum provides /path/to/file

---
