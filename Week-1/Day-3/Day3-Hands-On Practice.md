# Day 3: Hands-On Practice

## Directory Operations Practice Exercises

---

## Exercise 1: Create a project structure

```bash
mkdir -pv ~/myproject/{src,bin,docs,tests,config}
tree ~/myproject
```

---

## Exercise 2: Navigate using different methods

```bash
cd ~/myproject/src
pwd

cd ..
pwd

cd -
pwd
```

---

## Exercise 3: Create and remove empty directories

```bash
mkdir -v temp1 temp2 temp3
rmdir -v temp1 temp2 temp3
```

---

## Exercise 4: Create nested directories and remove

```bash
mkdir -pv a/b/c/d/e
rmdir -pv a/b/c/d/e
```

---

## Exercise 5: Check file/directory status

```bash
stat /etc/passwd
stat -c "%n : %a permissions, %U owner" /etc/passwd
```

---

## Exercise 6: Create directories with specific permissions

```bash
mkdir -m 755 public
mkdir -m 700 private
ls -ld public private
```

---
