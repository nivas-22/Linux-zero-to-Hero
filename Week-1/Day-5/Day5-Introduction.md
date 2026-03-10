# Day 5: File Viewing Commands

Reading and Viewing File Contents

---

## Commands

1. `cat` – Concatenate and display files  
2. `tac` – Display file in reverse (last line first)  
3. `more` – View file one screen at a time  
4. `less` – Improved file viewer (more features than `more`)  
5. `head` – Display first lines of a file  
6. `tail` – Display last lines of a file  

---

## cat Examples

### Display file contents

```bash
cat file.txt
```

Output:

```
Hello World
This is line 2
This is line 3
```

---

### Display with line numbers

```bash
cat -n file.txt
```

### Number non-blank lines only

```bash
cat -b file.txt
```

### Concatenate multiple files into a new file

```bash
cat file1.txt file2.txt > combined.txt
```

### Create a file using cat

```bash
cat > newfile.txt
# Type your content here
# Press Ctrl + D to save
```

### Append to a file

```bash
cat >> file.txt
# Type content to append
# Press Ctrl + D
```

### Show end of lines and tabs

```bash
cat -A file.txt
```

### Squeeze blank lines

```bash
cat -s file_with_blanks.txt
```

---

## tac Examples

### Display file in reverse

```bash
tac file.txt
```

### Useful for viewing newest logs first

```bash
tac /var/log/syslog | head -20
```

---

## more Examples

### View file

```bash
more /var/log/syslog
```

### Start at a specific line

```bash
more +100 largefile.txt
```

### Display N lines per screen

```bash
more -20 file.txt
```

### Navigation in more

- Space → Next page  
- Enter → Next line  
- `b` → Previous page  
- `q` → Quit  
- `/text` → Search for "text"  

---

## less Examples

### View file

```bash
less /var/log/syslog
```

### With line numbers

```bash
less -N file.txt
```

### Follow log file in real-time

```bash
less +F /var/log/syslog
```

- Press `Ctrl + C` to stop following, `F` to resume  

### Search within less

```text
/ error     # Search forward for "error"
/ warning   # Search backward for "warning"
n           # Next match
N           # Previous match
```

### Navigation

- `g` → Go to beginning  
- `G` → Go to end  
- `50g` → Go to line 50  

**Advantages of less over more:**

- Allows backward navigation  
- Better search capabilities  
- Doesn’t load the entire file into memory  
- Follow mode for log files  

---

## head Examples

### Display first 10 lines (default)

```bash
head file.txt
```

### Display first 5 lines

```bash
head -n 5 file.txt
head -5 file.txt
```

### Display first 100 bytes

```bash
head -c 100 file.txt
```

### Display first lines of multiple files

```bash
head file1.txt file2.txt
```

### Quiet mode (no headers)

```bash
head -q file1.txt file2.txt
```

### Display all but last 5 lines

```bash
head -n -5 file.txt
```

---

## tail Examples

### Display last 10 lines (default)

```bash
tail file.txt
```

### Display last 20 lines

```bash
tail -n 20 file.txt
tail -20 file.txt
```

### Display last 50 bytes

```bash
tail -c 50 file.txt
```

### Follow log file in real-time

```bash
tail -f /var/log/syslog
```

- Press `Ctrl + C` to stop  

### Follow multiple files

```bash
tail -f /var/log/syslog /var/log/auth.log
```

### Follow with retry (for log rotation)

```bash
tail -F /var/log/syslog
```

### Display starting from line 100

```bash
tail -n +100 file.txt
```

### Combine with grep for filtering

```bash
tail -f /var/log/syslog | grep error
```

### Monitor DevOps logs in real-time

```bash
tail -f /var/log/nginx/access.log
tail -f /var/log/nginx/error.log
tail -f /var/log/syslog | grep -i error
```

---
