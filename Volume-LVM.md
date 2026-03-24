# 🐧 Linux Volume Management – Complete Notes

A complete guide to understanding Linux storage & volume management: disks, partitions, filesystems, mounting, and LVM.

**📦 1. What is a Volume in Linux?**

A volume is a storage area where data is stored.

🔹 Types of Volumes:
💽 Entire disks
🧩 Disk partitions
🧠 Logical volumes (LVM)

⚠️ A volume must be formatted before use.

**🧱 Linux Storage Architecture**

```
Physical Disk → Partition → Filesystem → Mount → Directory
```

✅ Example:
```
/dev/nvme1n1 → /dev/nvme1n1p1 → ext4 → /mnt/data
```

**🔍 2. Listing Available Disks**

⭐ lsblk (MOST IMPORTANT)
```
lsblk
```

📊 Shows:

- Disks
- Partitions
- Mount points
- Sizes

🧾 Example:

```
nvme1n1     10G disk
└─nvme1n1p1 10G part /mnt/data
```
`disk` = physical device
`part` = partition
`/mnt/data` = mounted location

💡 Interview Tip:
👉 If you remember ONE command → lsblk

📉 df -h (Check Mounted Storage)(Disk Usage)

```
df -h
```

✔ Shows:

- Used space
- Free space
- Mounted filesystems
`-h` = human readable (GB/MB)

🧠 fdisk -l (Detailed Info)
```
sudo fdisk -l
```

✔ Displays:

- Disk size
- Partition table
- Sector info

**🛠️ 3. Creating a Filesystem**

⚠️ Formatting deletes ALL data

📌 EXT4 (Most Common)
```
sudo mkfs.ext4 /dev/nvme1n1
```

OR

```
sudo mkfs -t ext4 /dev/nvme1n1
```

**⚙️ What happens internally?**

Creates inode tables
Allocates blocks
Builds journal

## 🔗 4. Mounting a Volume
**Step 1️⃣ Create Mount Directory**

```
sudo mkdir /mnt/data
```
**Step 2️⃣ Mount Disk**

```
sudo mount /dev/nvme1n1 /mnt/data
```

**Step 3️⃣ Verify**

```
df -h
```
Now the disk is usable.

**Step 4️⃣ Test**

```
cd /mnt/data
touch testfile
```

✅ If file is created → mount successful

🔁 5. Persistent Mount (VERY IMPORTANT)

💥 Problem: Mount disappears after reboot
✅ Solution: Use /etc/fstab

Edit File

```
sudo nano /etc/fstab
```

Example Entry:

```
/dev/nvme1n1 /mnt/data ext4 defaults 0 0
```

📋 Fields Explained:

| Field       | Meaning        |
| ----------- | -------------- |
| Device      | Disk path      |
| Mount Point | Directory      |
| Filesystem  | ext4/xfs       |
| Options     | defaults       |
| Dump        | Backup flag    |
| Pass        | FS check order |


🧪 Test Without Reboot

```
sudo mount -a
```
If no error → configuration correct

⚠️ Wrong config can break boot!

## 🔌 6. Unmounting a Disk

```
sudo umount /mnt/data
```

OR

```
sudo umount /dev/nvme1n1
```

❗ If Busy:

```
lsof | grep /mnt/data
```

## 🧠 7. Introduction to LVM

**📌 What is LVM?**

Logical Volume Manager = Flexible disk management

🚫 Traditional Partition Problems:

- Hard to resize
- Requires downtime
- 
✅ LVM Advantages:

**✅Easy resizing**
**✅Combine disks**
**✅Snapshots**
**✅Better planning**

🏗️ LVM Architecture

```
Disk → PV → VG → LV → Filesystem → Mount
```

🧩 Analogy:
🧱 PV = Bricks
🏢 VG = Wall
🚪 LV = Room


## ⚙️ 8. LVM Practical Steps

🔹 Step 1: Create Physical Volume (PV)

```
sudo pvcreate /dev/nvme2n1
```

✔ Verify:

```
pvs
```

```
pvdisplay
```

🔹 Step 2: Create Volume Group (VG)

```
sudo vgcreate learn_vg /dev/nvme2n1
```

✔ Check:

vgs

## 🔹 Step 3: Create Logical Volume (LV)

```
sudo lvcreate -L 2G learn_vg -n learn_devops_lv
```

✔ Verify:

```
lvs
lvdisplay
```

📍 Path:

```
/dev/learn_vg/learn_devops_lv
```

**🔹 Step 4: Format LV**

```
sudo mkfs.ext4 /dev/learn_vg/learn_devops_lv
```

**🔹 Step 5: Mount LV**

```
sudo mkdir /mnt/lvm_data
sudo mount /dev/learn_vg/learn_devops_lv /mnt/lvm_data
```

✔ Verify:

```
df -h
```

## 📈 9. Extending LVM (🔥 DevOps Favorite)

**➕ Extend Logical Volume**

Example: Add 3GB

```
sudo lvextend -L +3G /dev/learn_vg/learn_devops_lv
```

**🔄 Resize Filesystem**

```
sudo resize2fs /dev/learn_vg/learn_devops_lv
```


✅ No downtime 🎉


**➕ Add New Disk to VG**

```
sudo pvcreate /dev/nvme3n1
sudo vgextend learn_vg /dev/nvme3n1
```

## ⚠️ Reduce Logical Volume (DANGEROUS)

🚨 Always backup first!

```
sudo umount /mnt/lvm_data
sudo e2fsck -f /dev/learn_vg/learn_devops_lv
sudo resize2fs /dev/learn_vg/learn_devops_lv 1G
sudo lvreduce -L 1G /dev/learn_vg/learn_devops_lv
```

Remount after.

## 📚 Cheat Sheet
## 💽 Storage

```
lsblk
df -h
fdisk -l
blkid
```

## 🔗 Mounting

```
mount
umount
cat /etc/fstab
```

## 🧠 LVM Commands

```
pvcreate
vgcreate
lvcreate
pvs
vgs
lvs
lvextend
lvreduce
```

## 🎯 Pro Tips

⭐ Always verify with lsblk after changes
⚠️ Never edit /etc/fstab without testing
🔄 Use LVM in production for flexibility
💾 Always backup before resize/reduce

---
