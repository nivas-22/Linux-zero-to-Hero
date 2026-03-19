# 🏁 ✅ Complete Script: Disk Monitoring + Auto Cleanup + Alert

### 💥 Problem Statement (Use in Class)

 **“Server disk becomes full frequently, causing application downtime.
 Build a script to detect, clean, log, and alert automatically.”**


 ```bash
 #!/bin/bash

# =========================
# CONFIGURATION
# =========================
THRESHOLD=80
LOG_FILE="./disk_monitor.log"
ALERT_EMAIL="admin@example.com"
CLEANUP_DIR="/var/log"
DAYS_OLD=7

# =========================
# FUNCTIONS
# =========================

log() {
    echo "$(date '+%F %T') : $1" | tee -a "$LOG_FILE"
}

send_alert() {
    msg=$1
    echo "$msg" | mail -s "Disk Alert" "$ALERT_EMAIL"
}

get_disk_usage() {
    df / | awk 'NR==2 {print $5}' | sed 's/%//'
}

cleanup_logs() {
    log "Cleaning logs older than $DAYS_OLD days in $CLEANUP_DIR"
    find "$CLEANUP_DIR" -type f -name "*.log" -mtime +$DAYS_OLD -exec rm -f {} \;
}

show_top_files() {
    log "Top 5 largest files:"
    du -ah / 2>/dev/null | sort -hr | head -5 >> "$LOG_FILE"
}

# =========================
# MAIN LOGIC
# =========================

usage=$(get_disk_usage)

log "Current disk usage: $usage%"

if [ "$usage" -ge "$THRESHOLD" ]; then
    log "WARNING: Disk usage exceeded threshold ($THRESHOLD%)"

    send_alert "Disk usage is high: $usage%"

    cleanup_logs

    usage_after=$(get_disk_usage)
    log "Disk usage after cleanup: $usage_after%"

    show_top_files

    # Second alert if still high
    if [ "$usage_after" -ge "$THRESHOLD" ]; then
        send_alert "Disk still high after cleanup: $usage_after%"
    fi

else
    log "Disk usage is under control"
fi
```
# ⚙️ How to Run

```bash
chmod +x disk_monitor.sh
./disk_monitor.sh
```
# ⏰ Automate with Cron

```
crontab -e
```

Add:

```copy
*/5 * * * * /path/to/disk_monitor.sh
```
👉 Runs every 5 minutes

---
