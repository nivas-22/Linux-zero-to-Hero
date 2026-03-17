### Disk & Storage Management
# Monitoring and Managing Disk Space

# df - Disk Free Space

```copy
# Basic disk usage
$ df
Filesystem 1K - blocks Used Available Use % Mounted on
/ dev / sda1 50000000 15000000 35000000 30% /
/ dev / sda2 100000000 40000000 60000000 40% / home

# Human - readable ( most common !)
$ df -h
Filesystem Size Used Avail Use % Mounted on
/ dev / sda1 48 G 15 G 34 G 30% /
/ dev / sda2 96 G 39 G 58 G 40% / home

# With filesystem type
$ df -hT
Filesystem Type Size Used Avail Use % Mounted on
/ dev / sda1 ext4 48 G 15 G 34 G 30% /
/ dev / sda2 ext4 96 G 39 G 58 G 40% / home
tmpfs tmpfs 3.9 G 0 3.9 G 0% / dev / shm

# Show inodes
$ df -i
Filesystem Inodes IUsed IFree IUse % Mounted on
/ dev / sda1 3276800 123456 3153344 4% /

# Specific filesystem
$ df -h / home

# Show total
$ df -h -- total

# Only ext4 filesystems
$ df -h -t ext4

# Exclude tmpfs
$ df -h -x tmpfs
```
---
# du - Disk Usage (Directory/File Size)

```copy
# Directory size ( recursive )
$ du -h / home / raman
4.0 K / home / raman /. config
50 M / home / raman / Documents
1.2 G / home / raman / Downloads
1.5 G / home / raman

# Summary only ( total size )
$ du -sh / home / raman
1.5 G / home / raman

# Multiple directories
$ du -sh / home /*
1.5 G / home / raman
500 M / home / john

# One level deep
$ du -h -d 1 / home / raman
50 M / home / raman / Documents
1.2 G / home / raman / Downloads
1.5 G / home / raman

# Find largest directories
$ du -h / home / raman | sort - hr | head -10

# With total
$ du - sch / home /*
1.5 G / home / raman
500 M / home / john
2.0 G total

# Exclude pattern
$ du -sh -- exclude ="*. log " / var

# Current directory subdirectories
$ du -sh */
50 M Documents /
1.2 G Downloads /
100 K Pictures /
```
---
# lsblk - List Block Devices

```copy

# Basic block device listing
$ lsblk
NAME MAJ : MIN RM SIZE RO TYPE MOUNTPOINT
sda 8:0 0 50 G 0 disk
+- sda1 8:1 0 50 G 0 part /
sdb 8:16 0 100 G 0 disk
+- sdb1 8:17 0 100 G 0 part / home
sr0 11:0 1 1024 M 0 rom

# With filesystem info
$ lsblk -f
NAME FSTYPE LABEL UUID MOUNTPOINT
sda
+- sda1 ext4 a1b2c3d4 - e5f6 -7890 - abcd - ef1234567890 /
sdb
+- sdb1 ext4 1234 abcd -5678 -90 ef - ghij - klmnopqrstuv / home

# Custom columns
$ lsblk -o NAME , SIZE , TYPE , FSTYPE , MOUNTPOINT
NAME SIZE TYPE FSTYPE MOUNTPOINT
sda 50 G disk
+- sda1 50 G part ext4 /

# Full paths
$ lsblk -p
NAME MAJ : MIN RM SIZE RO TYPE MOUNTPOINT
/ dev / sda 8:0 0 50 G 0 disk
+ -/ dev / sda1 8:1 0 50 G 0 part /

# Disks only
$ lsblk -d

```
---
# mount, umount - Mount/Unmount Filesystems


```copy
# Show mounted filesystems
$ mount
$ mount | grep "^/ dev "
/ dev / sda1 on / type ext4 ( rw , relatime )
/ dev / sdb1 on / home type ext4 (rw , relatime )

# Mount a device
$ sudo mkdir / mnt / usb
$ sudo mount / dev / sdc1 / mnt / usb

# Mount with specific type
$ sudo mount -t ntfs / dev / sdc1 / mnt / windows

# Mount read - only
$ sudo mount -r / dev / sdc1 / mnt / readonly

# Mount with options
$ sudo mount -o rw , noexec / dev / sdc1 / mnt / data

# Unmount
$ sudo umount / mnt / usb
$ sudo umount / dev / sdc1

# Force unmount ( if busy )
$ sudo umount -f / mnt / usb

# Lazy unmount ( detach immediately )
$ sudo umount -l / mnt / usb

# Remount with different options
$ sudo mount -o remount , ro / mnt / data
```
---
# fdisk - Partition Table Manipulator

```copy
# List all partitions
$ sudo fdisk -l
Disk / dev / sda : 50 GiB , 53687091200 bytes , 104857600 sectors
...
Device Boot Start End Sectors Size Id Type
/ dev / sda1 * 2048 104857599 104855552 50 G 83 Linux

# List specific disk
$ sudo fdisk -l / dev / sda

# Interactive partition editing
$ sudo fdisk / dev / sdb


# Commands inside fdisk :
# m - help menu
# p - print partition table
# n - new partition
# d - delete partition
# t - change partition type
# w - write changes and exit
# q - quit without saving
```
---
# mkfs, fsck - Create/Check Filesystems

```copy
# Create ext4 filesystem
$ sudo mkfs . ext4 / dev / sdb1

# Create with label
$ sudo mkfs . ext4 -L " MyData " / dev / sdb1

# Create XFS filesystem
$ sudo mkfs . xfs / dev / sdb1

# Create FAT32 ( for USB drives )
$ sudo mkfs . vfat / dev / sdc1

# Check filesystem ( must be unmounted !)
$ sudo umount / dev / sdb1
$ sudo fsck / dev / sdb1

# Force check
$ sudo fsck -f / dev / sdb1

# Auto - fix errors
$ sudo fsck -y / dev / sdb1

# Check ext4 specifically
$ sudo e2fsck / dev / sdb1
```
---
