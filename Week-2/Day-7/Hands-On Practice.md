## Exercise 1: Check your user and group info

```copy
$ id
$ groups
$ id -un
$ id -gn
```

## Exercise 2: Create file and check ownership

```copy
$ touch myfile . txt
$ ls -l myfile . txt
$ stat -c "% U :% G" myfile . txt
```

## Exercise 3: Change group (if you have multiple groups)

```copy
$ groups # Check your groups
$ chgrp <your - other - group > myfile . txt
$ ls -l myfile . txt
```

## Exercise 4: Practice chown with sudo

```copy
$ sudo chown root : root myfile . txt
$ ls -l myfile . txt
$ sudo chown $USER : $USER myfile . txt # Change back
```
## Exercise 5: Check other users’ info

```copy

$ id root
$ groups root
$ id www - data # Web server user
```
---
