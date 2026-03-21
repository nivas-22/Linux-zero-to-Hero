# Linux Complete Guide – Day 14 Exercises (Hands-On Practice)

## Exercise 1: Create and Extract Archives

```bash
mkdir test_backup && cd test_backup

echo "test1" > file1.txt
echo "test2" > file2.txt

mkdir subdir
echo "test3" > subdir/file3.txt

# Create compressed archive
tar -czvf backup.tar.gz .

# List contents
tar -tzvf backup.tar.gz

# Extract to new directory
mkdir restore
tar -xzvf backup.tar.gz -C restore/

ls -la restore/
```
---


## Exercise 2: Compare Compression

```
# Create a 10MB test file
dd if=/dev/zero of=testfile bs=1M count=10

# Compress using gzip
cp testfile testfile_gzip
gzip testfile_gzip

# Compress using bzip2
cp testfile testfile_bzip
bzip2 testfile_bzip

# Compress using xz
cp testfile testfile_xz
xz testfile_xz

# Check file sizes
ls -lh testfile*
```
---
## Exercise 3: Practice rsync

```copy

mkdir source dest

# Create initial files
touch source/{a,b,c}.txt

# Sync source to destination
rsync -av source/ dest/

# Verify contents
ls dest/

# Add a new file
touch source/d.txt

# Sync again (only new file will be transferred)
rsync -av source/ dest/
```
---

# Interview Question
### Q: How do you create a compressed backup of a directory?
>Use tar -czvf backup.tar.gz /path/to/directory to create a gzip-compressed archive. Use
>-cjvf for bzip2 or -cJvf for xz compression.

### Q: What is the difference between tar and rsync for backups?

>tar creates archive files (one file containing many). rsync synchronizes directories by copying
>only changed files. rsync is better for incremental backups and remote sync.

### Q: How do you create a bootable USB drive from an ISO?

>Use sudo dd if=image.iso of=/dev/sdX bs=4M status=progress where sdX is the USB de-
>vice. Be VERY careful to specify the correct device.
