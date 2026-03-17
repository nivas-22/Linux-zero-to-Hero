### DAY 8: User & Group Management

Creating and Managing Users and Groups

```copy
# Create basic user
$ sudo useradd john

# Create user with home directory
$ sudo useradd -m john
$ ls -la / home / john /

# Create user with all options
$ sudo useradd -m -s / bin / bash -c " John Doe " -G sudo , developers
john

# Create system user ( for services )
$ sudo useradd -r -s / usr / sbin / nologin appuser

# Create user with specific UID
$ sudo useradd -m -u 1500 john

# Create user with expiry date
$ sudo useradd -m -e 2024 -12 -31 tempuser

# Verify user creation
$ cat / etc / passwd | grep john
john :x :1001:1001: John Doe :/ home / john :/ bin / bash
$ id john
uid =1001( john ) gid =1001( john ) groups =1001( john ) ,27( sudo ) ,1002(
developers )
```
---

## usermod - Modify User Account

```copy

# Add user to group ( IMPORTANT : use -aG , not just -G !)
$ sudo usermod - aG sudo john
$ sudo usermod - aG docker john

# Change login name
$ sudo usermod -l johndoe john

# Change home directory and move contents
$ sudo usermod -d / home / johndoe -m john

# Change shell
$ sudo usermod -s / bin / zsh john

# Lock user account
$ sudo usermod -L john
$ sudo passwd -S john
john L 01/15/2024 ... # L = Locked

# Unlock user account
$ sudo usermod -U john

# Set account expiry
$ sudo usermod -e 2024 -12 -31 john

# Add to multiple groups
$ sudo usermod - aG developers , testers , docker john
```
---
## userdel - Delete User Account

```copy
# Delete user ( keeps home directory )
$ sudo userdel john

# Delete user AND home directory
$ sudo userdel -r john

# Force delete ( even if logged in )
$ sudo userdel - rf john

# Verify deletion
$ cat / etc / passwd | grep john
# ( no output = deleted )
```
---
