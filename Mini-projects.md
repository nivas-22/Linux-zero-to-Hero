### 🛠️ 1. Log Monitor (Error Alert System)
📌 Idea:

Scan a log file and alert if errors are found

```bash
#!/bin/bash

logfile="/var/log/syslog"

if [ ! -f "$logfile" ]; then
    echo "Log file not found!"
    exit 1
fi

errors=$(grep -i "error" "$logfile")

if [ -n "$errors" ]; then
    echo "⚠️ Errors found in log!"
    echo "$errors"
else
    echo "✅ No errors found"
fi
```

----

### 2. Disk Usage Monitor

📌 Idea:

Warn if disk usage is high

```bash

#!/bin/bash

usage=$(df / | grep / | awk '{print $5}' | sed 's/%//')

if [ "$usage" -gt 80 ]; then
    echo "⚠️ Disk usage is above 80%!"
else
    echo "✅ Disk usage is normal"
fi

```

---

### 3. Auto Backup with Date

📌 Idea:

Create timestamped backups

```bash
#!/bin/bash

source_dir="$HOME/test"
backup_dir="$HOME/backup"

date=$(date +%Y-%m-%d_%H-%M-%S)

mkdir -p "$backup_dir"

cp -r "$source_dir" "$backup_dir/backup_$date"

echo "Backup created at $backup_dir/backup_$date"
```
---

### 4. Process Checker
📌 Idea:

Check if a service/process is running

```bash

#!/bin/bash

echo "Enter process name:"
read process

if pgrep "$process" > /dev/null
then
    echo "✅ Process is running"
else
    echo "❌ Process not running"
fi

```
---
