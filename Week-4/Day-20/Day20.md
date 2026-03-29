# 🏆 DAY 20: Text Processing – INTERVIEW GOLD!

## 💻 Master the Most Asked Linux Text Processing Commands

Text processing is a **critical skill** for Linux interviews. Think of it as the Swiss Army knife of command-line data handling.

---

## 1️⃣ `cat` – Concatenate & Display Files

```bash id="cat001"
cat file.txt
cat file1.txt file2.txt > combined.txt
```

* Display contents
* Combine multiple files

---

## 2️⃣ `tac` – Reverse File Content

```bash
tac logfile.txt | grep "ERROR" | head -n 10
```
Shows 10 most recent errors

* Reads files **line by line from bottom to top**

Memory Tip
- cat → top → bottom
- tac → bottom → top
Think of it like reversing a stack of papers! 📄🔄

---

## 3️⃣ `head` & `tail` – Peek at Top/Bottom

```bash id="head001"
head -n 10 file.txt  # First 10 lines
tail -n 10 file.txt  # Last 10 lines
tail -f /var/log/syslog  # Real-time monitoring
```

---

## 4️⃣ `cut` – Extract Columns

```bash id="cut001"
cut -d',' -f1,3 file.csv
```

* `-d` → delimiter
* `-f` → fields to extract

---

## 5️⃣ `sort` – Organize Data

```bash id="sort001"
sort file.txt            # Alphabetical
sort -r file.txt         # Reverse order
sort -n file.txt         # Numerical sort
sort -t',' -k2 file.csv  # Sort by 2nd column
```

---

## 6️⃣ `uniq` – Filter Duplicate Lines

```bash id="uniq001"
sort file.txt | uniq
sort file.txt | uniq -c  # Count duplicates
```

---

## 7️⃣ `grep` – Search Patterns

```bash id="grep001"
grep 'error' file.log
grep -i 'error' file.log   # Case-insensitive
grep -r 'TODO' ./          # Recursive search
grep -v 'DEBUG' file.log   # Exclude pattern
```

---

## 8️⃣ `awk` – Advanced Text Processing

```bash id="awk001"
awk '{print $1}' file.txt           # Print first column
awk -F',' '{print $2}' file.csv     # Column by delimiter
awk '{sum+=$2} END {print sum}' file.txt  # Sum values
```

---

## 9️⃣ `sed` – Stream Editor

```bash id="sed001"
sed 's/error/ERROR/g' file.txt     # Replace text
sed -n '1,5p' file.txt            # Print lines 1-5
sed '/DEBUG/d' file.txt            # Delete lines matching pattern
```

---

## 🔟 Combine Commands – Power Tools

```bash id="combo001"
grep 'ERROR' logfile.txt | sort | uniq -c | sort -nr
```

* Search errors, count occurrences, and sort by frequency

---

| Command     | Icon & Color | Usage / Example                                                                               | Notes                                   |          |                           |
| ----------- | ------------ | --------------------------------------------------------------------------------------------- | --------------------------------------- | -------- | ------------------------- |
| **`cat`**   | 📄 Blue      | `cat file.txt` <br> `cat file1.txt file2.txt > combined.txt`                                  | Display or combine files                |          |                           |
| **`tac`**   | 🔄 Purple    | `tac file.txt`                                                                                | Reads file **bottom → top**             |          |                           |
| **`head`**  | ⬆️ Green     | `head -n 10 file.txt`                                                                         | Show top lines                          |          |                           |
| **`tail`**  | ⬇️ Green     | `tail -n 10 file.txt` <br> `tail -f /var/log/syslog`                                          | Show last lines / live monitoring       |          |                           |
| **`cut`**   | ✂️ Orange    | `cut -d',' -f1,3 file.csv`                                                                    | Extract columns by delimiter            |          |                           |
| **`sort`**  | 🔀 Teal      | `sort file.txt` <br> `sort -n file.txt` <br> `sort -t',' -k2 file.csv`                        | Alphabetical / numeric / column sorting |          |                           |
| **`uniq`**  | 🧩 Yellow    | `sort file.txt                                                                                | uniq`<br>`sort file.txt                 | uniq -c` | Filter duplicates / count |
| **`grep`**  | 🔍 Red       | `grep 'error' file.log` <br> `grep -i 'error' file.log` <br> `grep -v 'DEBUG' file.log`       | Search patterns                         |          |                           |
| **`awk`**   | 🛠️ Purple   | `awk '{print $1}' file.txt` <br> `awk -F',' '{print $2}' file.csv`                            | Column extraction / calculations        |          |                           |
| **`sed`**   | ✏️ Pink      | `sed 's/error/ERROR/g' file.txt` <br> `sed -n '1,5p' file.txt` <br> `sed '/DEBUG/d' file.txt` | Replace / delete / edit text inline     |          |                           |
| **Combine** | ⚡ Rainbow    | `grep 'ERROR' logfile.txt \| sort \| uniq -c \| sort -nr`                                     | Powerful pipelines                      |          |                           |

💡 Master these commands, and you’ll turn text processing questions into **interview-winning answers**!

---

| Command    | Icon | Description          | Use Case                                    | Rating |
| ---------- | ---- | -------------------- | ------------------------------------------- | ------ |
| **`grep`** | 🔍   | Search patterns      | Find text in files                          | ⭐⭐⭐⭐⭐  |
| **`sed`**  | ✏️   | Stream editor        | Replace or modify text inline               | ⭐⭐⭐⭐⭐  |
| **`awk`**  | 🛠️  | Pattern processing   | Work with columns, calculations             | ⭐⭐⭐⭐⭐  |
| **`cut`**  | ✂️   | Remove sections      | Extract specific fields                     | ⭐⭐⭐⭐   |
| **`sort`** | 🔀   | Sort lines           | Organize data alphabetically or numerically | ⭐⭐⭐⭐   |
| **`uniq`** | 🧩   | Remove duplicates    | Deduplicate repeated lines                  | ⭐⭐⭐⭐   |
| **`wc`**   | 📊   | Word/line/char count | Quick statistics on files                   | ⭐⭐⭐⭐   |
| **`tr`**   | 🔄   | Translate characters | Transform or replace characters             | ⭐⭐⭐    |

---

🎨 Visual Notes
Icons represent functionality:
🔍 grep → search
✏️ sed → edit
🛠️ awk → processing tool
✂️ cut → remove/cut fields
🔀 sort → organize
🧩 uniq → deduplicate
📊 wc → statistics
🔄 tr → transform
Star rating shows interview importance (5★ = must-know).

---

# 🔍 `grep` – Search Patterns Cheat Sheet

`grep` is your **go-to tool for searching text patterns** in files and directories. Perfect for log analysis and troubleshooting! 🕵️‍♂️

---

## 📄 Basic Search

### 🔹 Search for a Pattern

```bash id="g1p9rv"
grep "error" logfile.txt
```

👀 *Finds all lines containing "error".*

### 🔹 Case-Insensitive Search

```bash id="g2i8kl"
grep -i "error" logfile.txt
```

🔤 *Matches "Error", "ERROR", or "error".*

---

## 📂 Recursive & File Searching

### 🔹 Recursive Search in Directory

```bash id="g3r7mn"
grep -r "error" /var/log/
```

📁 *Searches all files under `/var/log/` for "error".*

### 🔹 Show Line Numbers

```bash id="g4n5py"
grep -n "error" logfile.txt
```

🔢 *Displays line numbers alongside matches.*

### 🔹 Count Matches

```bash id="g5c3lk"
grep -c "error" logfile.txt
```

📊 *Counts the number of matching lines.*

---

## 🚫 Invert Match

### 🔹 Exclude Lines Containing a Pattern

```bash id="g6v2qt"
grep -v "info" logfile.txt
```

❌ *Shows lines that **do NOT contain "info"**.*

---

## ↔️ Context Around Matches

### 🔹 Lines Before a Match

```bash id="g7b4sr"
grep -B 2 "error" logfile.txt
```

⬅️ *Shows 2 lines before each match.*

### 🔹 Lines After a Match

```bash id="g8a6ty"
grep -A 2 "error" logfile.txt
```

➡️ *Shows 2 lines after each match.*

---

## ✨ Extended Regex

### 🔹 Search for Multiple Patterns (OR)

```bash id="g9e8wx"
grep -E "error|warning" logfile.txt
```

⚡ *Matches either "error" or "warning".*

---

## 💡 Pro Tips

* Combine with `tail` to monitor live logs:

```bash id="gp1rt9"
tail -f /var/log/syslog | grep "error"
```

* Use `grep -H` to always display filenames with matches in multiple files.
* Pipe output to `less` for easier navigation:

```bash id="gq2lp8"
grep -r "error" /var/log/ | less
```

---

## 🎯 Quick Summary

| Command               | Purpose                   |
| --------------------- | ------------------------- |
| `grep "pattern" file` | Basic search              |
| `grep -i`             | Case-insensitive search   |
| `grep -r`             | Recursive search          |
| `grep -n`             | Show line numbers         |
| `grep -c`             | Count matches             |
| `grep -v`             | Invert match              |
| `grep -B/-A`          | Lines before/after match  |
| `grep -E`             | Extended regex (OR, etc.) |

---

### 🔐 Why Use `grep`?

* Debug logs quickly
* Search large directories efficiently
* Combine with other commands for powerful monitoring 🛠️

Stay sharp—grep makes you the Sherlock of your logs! 🕵️‍♀️

---
# 📝 `sed` – Stream Editor Cheat Sheet

`sed` is a **powerful stream editor** for modifying and analyzing text files line by line. Perfect for quick edits, automation, and log processing! ⚡

---

## 🔄 Text Replacement

### 🔹 Replace First Occurrence Per Line

```bash id="s1r9pl"
sed 's/old/new/' file.txt
```

✏️ *Replaces only the first "old" on each line with "new".*

### 🔹 Replace All Occurrences (Global)

```bash id="s2g8kt"
sed 's/old/new/g' file.txt
```

⚡ *Replaces every "old" with "new" in each line.*

### 🔹 Replace In-Place (Modify File)

```bash id="s3i7vr"
sed -i 's/old/new/g' file.txt
```

💾 *Updates the file directly without printing to stdout.*

---

## ❌ Delete Lines

### 🔹 Delete Lines Containing a Pattern

```bash id="s4p6dq"
sed '/pattern/d' file.txt
```

🗑️ *Removes all lines that contain "pattern".*

### 🔹 Delete Specific Line by Number

```bash id="s5d8fy"
sed '5d' file.txt
```

📝 *Deletes the 5th line in the file.*

---

## 👀 Print Specific Lines

### 🔹 Print Specific Line

```bash id="s6p9lx"
sed -n '5p' file.txt
```

🔹 *Displays only the 5th line.*

### 🔹 Print Range of Lines

```bash id="s7p4qw"
sed -n '5,10p' file.txt
```

📄 *Shows lines 5 through 10.*

---

## ✨ Clean-Up Tricks

### 🔹 Remove Blank Lines

```bash id="s8b2mk"
sed '/^$/d' file.txt
```

🧹 *Deletes empty lines for cleaner output.*

---

## 💡 Pro Tips

* Combine `sed` with `grep` for powerful filtering:

```bash id="s9g3pv"
grep "error" file.txt | sed 's/error/ERROR/g'
```

* Use `-i.bak` to backup files when modifying in-place:

```bash id="s10i8jx"
sed -i.bak 's/old/new/g' file.txt
```

* `sed` supports **regular expressions** for advanced pattern matching.

---

## 🎯 Quick Summary

| Command       | Purpose                           |
| ------------- | --------------------------------- |
| `s/old/new/`  | Replace first occurrence per line |
| `s/old/new/g` | Replace all occurrences per line  |
| `-i`          | Modify file in-place              |
| `/pattern/d`  | Delete lines containing pattern   |
| `Nd`          | Delete line N                     |
| `-n Np`       | Print line N                      |
| `-n N,Mp`     | Print lines N through M           |
| `/^$/d`       | Remove blank lines                |

---

### 🔐 Why Use `sed`?

* Automate text edits
* Process logs or config files
* Apply changes without opening editors

`sed` turns text manipulation into a **fast, scriptable, and powerful workflow**! ⚡

---

# 📊 `awk` – Pattern Processing & Text Manipulation Cheat Sheet

`awk` is a **powerful text processing tool** for analyzing columns, performing calculations, and filtering patterns in files. Perfect for logs, CSVs, and reports! ⚡

---

## 🗂️ Column Operations

### 🔹 Print Specific Column

```bash id="a1c9pl"
awk '{ print $1 }' file.txt
```

📄 *Displays only the first column of each line.*

### 🔹 Print Multiple Columns

```bash id="a2c7kt"
awk '{ print $1, $3 }' file.txt
```

⚡ *Shows the first and third columns.*

### 🔹 Custom Field Separator

```bash id="a3f8vr"
awk -F ': ' '{ print $1 }' /etc/passwd
```

🛠️ *Splits fields using `: ` instead of whitespace.*

---

## ⚡ Conditional & Pattern-Based Printing

### 🔹 Conditional Printing

```bash id="a4c6dq"
awk '$3 > 100 { print $1 }' file.txt
```

✅ *Prints the first column only if the third column is greater than 100.*

### 🔹 Pattern Matching

```bash id="a5p9lx"
awk '/error/ { print $0 }' logfile.txt
```

🔍 *Prints all lines containing the word "error".*

---

## 🔢 Line Numbers & Columns

### 🔹 Print Line Numbers

```bash id="a6n4qw"
awk '{ print NR, $0 }' file.txt
```

🧾 *Adds line numbers before each line.*

### 🔹 Print Last Column

```bash id="a7l2mk"
awk '{ print $NF }' file.txt
```

➡️ *Displays the last column of each line.*

---

## ➕ Arithmetic & Aggregation

### 🔹 Sum a Column

```bash id="a8s3pv"
awk '{ sum += $1 } END { print sum }' numbers.txt
```

💰 *Calculates the total of the first column.*

---

## 💡 Pro Tips

* Use `awk` with `grep` for powerful filtering:

```bash id="a9g4jx"
grep "error" logfile.txt | awk '{ print $2, $5 }'
```

* Combine with `sort` and `uniq` for summary reports.
* Use `-F` to handle CSV or custom-delimited files easily.

---

## 🎯 Quick Summary

| Command                           | Purpose                     |
| --------------------------------- | --------------------------- |
| `{ print $1 }`                    | Print first column          |
| `{ print $1, $3 }`                | Print multiple columns      |
| `-F`                              | Custom field separator      |
| `$3 > 100 { print $1 }`           | Conditional column printing |
| `NR, $0`                          | Print line numbers          |
| `{ print $NF }`                   | Print last column           |
| `{ sum += $1 } END { print sum }` | Sum a column                |
| `/pattern/ { print $0 }`          | Pattern matching            |

---

### 🔐 Why Use `awk`?

* Analyze structured text efficiently
* Perform calculations without external scripts
* Extract, filter, and summarize logs or reports

`awk` turns simple text files into **insightful data** at lightning speed! ⚡

---
# 🛠️ Linux Text Processing Cheat Sheet: `cut`, `sort`, `uniq`, `wc`, `tr`

These commands are **essential for extracting, sorting, counting, and transforming text** in Linux. Perfect for logs, CSVs, and automation! ⚡

---

## ✂️ `cut` – Extract Fields

### 🔹 Extract First Field Using Separator

```bash id="c1d9pl"
cut -d ': ' -f1 /etc/passwd
```

📄 *Extracts the first field from `/etc/passwd` using `:` as the delimiter.*

### 🔹 Extract Multiple Fields

```bash id="c2d7kt"
cut -d ',' -f1,3 data.csv
```

⚡ *Displays the 1st and 3rd columns from a CSV file.*

---

## 🔃 `sort` – Sort Lines

### 🔹 Alphabetical Sort

```bash id="s1a8vr"
sort file.txt
```

### 🔹 Numeric Sort

```bash id="s2n6dq"
sort -n numbers.txt
```

### 🔹 Reverse Sort

```bash id="s3r9lx"
sort -r file.txt
```

### 🔹 Sort & Remove Duplicates

```bash id="s4u4qw"
sort -u file.txt
```

---

## 🔹 `uniq` – Remove Duplicate Lines

> ⚠️ **Use with `sort`** to remove duplicates reliably.

### 🔹 Remove Duplicates

```bash id="u1r2mk"
sort file.txt | uniq
```

### 🔹 Count Occurrences

```bash id="u2c3pv"
sort file.txt | uniq -c
```

---

## 📝 `wc` – Word/Line Count

### 🔹 Count Lines

```bash id="w1l4jx"
wc -l file.txt
```

### 🔹 Count Words

```bash id="w2w6rm"
wc -w file.txt
```

---

## 🔤 `tr` – Translate/Transform Characters

### 🔹 Convert to Uppercase

```bash id="t1u3vk"
echo "hello" | tr 'a-z' 'A-Z'
```

### 🔹 Delete Characters

```bash id="t2d5py"
echo "hello" | tr -d 'l'
```

➡️ *Removes all occurrences of "l".*

---

## 💡 Pro Tips

* Combine commands for powerful pipelines:

```bash id="p1c8qw"
cut -d ',' -f2 data.csv | sort | uniq -c | sort -nr
```

* Use `wc -l` with `grep` to count matches:

```bash id="p2w4jx"
grep "error" logfile.txt | wc -l
```

* `tr` is great for cleaning text or converting formats in scripts.

---

## 🎯 Quick Summary

| Command             | Purpose                           |
| ------------------- | --------------------------------- |
| `cut -d DELIM -f N` | Extract fields/columns            |
| `sort`              | Alphabetical sort                 |
| `sort -n`           | Numeric sort                      |
| `sort -r`           | Reverse sort                      |
| `sort -u`           | Sort & remove duplicates          |
| `uniq`              | Remove duplicates (use with sort) |
| `uniq -c`           | Count occurrences                 |
| `wc -l`             | Count lines                       |
| `wc -w`             | Count words                       |
| `tr 'a-z' 'A-Z'`    | Convert to uppercase              |
| `tr -d CHAR`        | Delete characters                 |

---

### 🔐 Why Use These Tools?

* Process text quickly and efficiently
* Analyze logs, CSVs, or reports
* Build powerful command-line pipelines for automation

Mastering these tools makes you a **Linux text-processing ninja**! 🥷

---
---

## ⚡ Interview Gold: Power Command Combinations

| 🔢 # | 🛠️ Command Combination | 📝 Description / Use Case |
|------|----------------------|---------------------------|
| 1    | `awk '{ print $1 }' access.log \| sort \| uniq -c \| sort -rn` | Find unique IPs and count occurrences in a log |
| 2    | `cut -d ':' -f1 /etc/passwd` | Extract usernames from the passwd file |
| 3    | `grep -c "error" logfile.txt` | Count the number of errors in a log file |
| 4    | `sort file.txt \| uniq -d` | Find duplicate lines in a file |
| 5    | `sed -i 's/old/new/g' *.txt` | Replace text across multiple files |

---

### 💡 Pro Tip

> Combine these commands with pipelines for **fast and powerful log and text analysis**.  
> Example: `grep "error" logfile.txt | awk '{print $2}' | sort | uniq -c` 🔥  

---

