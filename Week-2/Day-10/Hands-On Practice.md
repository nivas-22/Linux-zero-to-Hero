## Exercise 1: Check disk space

```copy
$ df -h
$ df -hT
$ df -i
```
## Exercise 2: Find large directories

```copy
$ du -sh / home /*
$ du -h / var | sort - hr | head -10
$ du -sh / var / log
```
## Exercise 3: View block devices

```
$ lsblk
$ lsblk -f
$ sudo blkid
```
## Exercise 4: Check mounted filesystems

```copy
$ mount | grep "^/ dev "
$ cat / etc / fstab
```
## Exercise 5: View partition table (read-only)

```copy
$ sudo fdisk -l
$ sudo parted -l
```
