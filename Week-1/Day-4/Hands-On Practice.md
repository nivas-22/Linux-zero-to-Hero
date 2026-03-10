# Day 4: Hands-On Practice

## File Operations Practice Exercises

---

## Exercise 1: Create test files

```bash
touch file{1..10}.txt
touch test{a..e}.log
ls
```

---

## Exercise 2: Copy files with options

```bash
mkdir backup
cp -v *.txt backup/
cp -rp project/ project_backup/
```

---

## Exercise 3: Move and rename files

```bash
mv file1.txt renamed_file.txt
mv -v *.log /tmp/logs/
```

---

## Exercise 4: Safe file deletion

```bash
rm -i file1.txt
rm -rv backup/
```

---

## Exercise 5: Find files with conditions

```bash
find /home -name "*.txt" -type f
find . -size +1M
find /var/log -mtime -1
```

---

## Exercise 6: Use locate

```bash
sudo updatedb
locate -i "passwd"
locate -n 10 "*.conf"
```

---
