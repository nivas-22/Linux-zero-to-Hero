# 🚨 Server Crash at 3 AM? Can You Diagnose It in 60 Seconds?

Most DevOps beginners can’t.

---

# 🖥️ Day 17 — Linux Process & System Monitoring

Today I learned how to **see what’s really happening inside a server** instead of guessing.

These commands are not just theory — they are used daily in real production environments.

---

## 🔍 Process Monitoring with `ps`

When a server slows down or behaves strangely, this is my **first step**:

```bash
ps -e        # View all running processes
ps aux       # Check CPU & memory usage per process
ps -ef       # See parent–child process relationships
ps -u user   # View processes for a specific user
```

🔍 Why This Matters

Instead of guessing what’s wrong inside a server, today I learned how to:

📊 Inspect running processes
⚡ Identify performance bottlenecks
🔐 Track user activity for security
🧠 Understand system behavior in real-time

These are real production-level skills, not just theory.

🔍 Process Monitoring with ps

When a server slows down or behaves unexpectedly, this is my first step:

```bash
ps -e          # View all running processes
ps aux         # Check CPU & memory usage per process
ps -ef         # View parent–child process relationships
ps -u username # Processes for a specific user
```

🧠 Real Use Case

If the server becomes slow:

👉 Run:

```bash
ps aux
```
✔ Instantly identify high CPU or memory-consuming processes
✔ Take action before the system crashes

🛠️ Quick System Information Commands

Before debugging, always verify the system environment:

```bash
uname -a   # Kernel version & architecture
hostname   # Server name
date       # Current system date & time
cal        # Calendar in terminal
```
⚡ Why It Matters
Confirms you're on the correct machine
Helps avoid environment-related mistakes
Critical when working on remote servers

👥 User Activity & System Access

Monitoring users is crucial for both security and troubleshooting:

```bash
who   # Currently logged-in users
w     # What each user is doing
last  # Login history
```

🔐 Pro Tip

After any incident:

👉 Run:

```bash
last
```

✔ See who accessed the system
✔ Identify suspicious logins
✔ Correlate activity with issues

💡 Key Takeaways

✅ ps aux → Detect resource-heavy processes instantly
✅ uname -a → Verify system details quickly
✅ who & last → Track user activity and investigate incidents


> **Note:**
>1. Server is slow / high load / hanging
> SSH still works (maybe slow)
>Commands respond (even if delayed)

✅ You can run:

ps aux
top / htop
free -m
uptime
