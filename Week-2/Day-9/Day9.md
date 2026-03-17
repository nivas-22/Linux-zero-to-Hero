### DAY 9: Process Management

Viewing and Controlling System Processes

# ⚙️ What is a Process?

## 📖 Definition

A **process** is a **running instance of a program**.

When a program is executed, the operating system creates a process to manage its execution.

---

## 🔑 Key Attributes of a Process

Every process has the following attributes:

| Attribute | Description |
|----------|-------------|
| PID      | Process ID – unique identifier |
| PPID     | Parent Process ID |
| UID      | User ID of the owner |
| State    | Current status of the process |
| Priority | CPU scheduling priority |

---

## 🔄 Process States

A process can exist in different states:

| Code | State Description |
|------|------------------|
| R    | Running or runnable |
| S    | Sleeping (interruptible) |
| D    | Sleeping (uninterruptible I/O) |
| T    | Stopped |
| Z    | Zombie (terminated but not cleaned up) |

---

## 🧠 Quick Concept

Program → Execution → Process

---

## 💡 Notes

- Each process is uniquely identified by its **PID**
- Processes are created in a **parent-child relationship (PPID)**
- Zombie processes indicate improper cleanup by the parent process
- Use commands like `ps`, `top`, and `htop` to monitor processes

---

```copy

# Current shell ’ s processes
$ ps
PID TTY TIME CMD
1234 pts /0 00:00:00 bash
5678 pts /0 00:00:00 ps

# All processes ( BSD style - most common !)
$ ps aux
USER PID % CPU % MEM VSZ RSS TTY STAT START TIME
COMMAND
root 1 0.0 0.1 169456 9876 ? Ss Jan10 0:05 / sbin /
init
root 2 0.0 0.0 0 0 ? S Jan10 0:00 [
kthreadd ]
raman 1234 0.0 0.2 21456 5432 pts /0 Ss 09:00 0:00 - bash

# All processes ( UNIX style )
$ ps -ef
UID PID PPID C STIME TTY TIME CMD
root 1 0 0 Jan10 ? 00:00:05 / sbin / init

# Processes for specific user
$ ps -u raman

# Show specific process
$ ps -p 1234

# Show process tree
$ ps -ef -- forest

# Custom output format
$ ps -eo pid , user , cmd ,% cpu ,% mem -- sort = -% cpu
PID USER CMD % CPU % MEM
5678 raman firefox 5.2 8.1
1234 root / usr / sbin / apache2 2.1 3.2

# Find process by name
$ ps aux | grep nginx
$ ps -C nginx
```
---
