## 🛠️ Text Processing: Hands-On Practice

| 🔢 # | 📝 Task Description           | ⚡ Command Example                                   |
|------|-----------------------------|----------------------------------------------------|
| 1    | Create a test file           | `echo -e "apple\nbanana\napple" > fruits.txt`     |
| 2    | Find duplicate lines         | `sort fruits.txt \| uniq -c`                       |
| 3    | Extract usernames            | `cut -d':' -f1 /etc/passwd \| head`               |
| 4    | Search for a pattern         | `grep "root" /etc/passwd`                          |
| 5    | Print first column           | `awk -F':' '{print $1}' /etc/passwd`              |
| 6    | Replace text in a string     | `echo "Hello World" \| sed 's/World/Linux/'`      |
| 7    | Convert text to uppercase    | `echo "hello" \| tr 'a-z' 'A-Z'`                  |

---

### 💡 Tip

> Combine commands in pipelines to **process, filter, and transform text efficiently**.  
> Example: `cut -d':' -f1 /etc/passwd | grep "root"` 🔍  

---

## 🎤 Interview Questions: Text Processing & Logs

### Q1: Difference between `grep`, `sed`, and `awk`?

| ⚡ Command | 📝 Purpose / Use Case                  |
|------------|--------------------------------------|
| 🔍 `grep`  | Search patterns, return matching lines |
| ✂️ `sed`   | Stream editor, find & replace text     |
| 🧩 `awk`   | Programming language for columns       |

> 💡 Tip:  
> - Use `grep` to **find** text  
> - Use `sed` to **replace** text  
> - Use `awk` to **process columns**  

---

### Q2: How to find unique entries in a log?

**Command:**  

```bash
awk '{print $1}' log | sort | uniq -c | sort -rn
```
---
