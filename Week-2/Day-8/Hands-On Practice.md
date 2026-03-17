### Day 8 Practice Exercises

## Exercise 1: Create a new user with home directory

```copy
$ sudo useradd -m -s / bin / bash -c " Test User " testuser
$ sudo passwd testuser
$ id testuser
$ ls -la / home / testuser /
```
## Exercise 2: Create a group and add user

```bash

$ sudo groupadd testgroup
$ sudo usermod - aG testgroup testuser
$ groups testuser
```

## Exercise 3: Check password aging

```copy
$ sudo chage -l testuser
```

## Exercise 4: Check logged in users

```copy
$ whoami
$ who
$ w
```
## Exercise 5: Clean up test user

```copy
$ sudo userdel -r testuser
$ sudo groupdel testgroup
```
---
