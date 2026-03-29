
## 🛠️ Hands-On Practice

### 🔹 Practice Exercises

| 🔢 # | 📝 Task Description           | ⚡ Command Example                          |
|------|-----------------------------|--------------------------------------------|
| 1    | View recent system logs      | `sudo journalctl --since "10 min ago"`     |
| 2    | Follow SSH logs in real-time | `sudo journalctl -u sshd -f`               |
| 3    | Find users on port 22        | `sudo lsof -i :22`                          |
| 4    | Monitor memory usage         | `watch -n 1 free -h`                        |
| 5    | Check I/O statistics         | `iostat -x 2 3`                             |

---

### 💡 Tip

> Combine these commands to **actively monitor and troubleshoot your system** in real-time.  
> Example: `watch -n 2 "sudo journalctl -xe | tail -n 20"` 🔍

---

---

## 🎤 Interview Question

**Q:** How do you troubleshoot a slow Linux system?  

**A:** I follow a **systematic approach** to pinpoint the issue:

| 🔢 Step | 🛠️ Action                        | ⚡ Command Example                               |
|---------|---------------------------------|-------------------------------------------------|
| 1       | Check recent errors in logs      | `journalctl -p err --since "1 hour ago"`        |
| 2       | Monitor CPU usage                | `mpstat -P ALL 1`                               |
| 3       | Check I/O performance            | `iostat -x 1`                                   |
| 4       | Identify heavy resource processes| `pidstat -u -r -d 1`                             |
| 5       | Monitor memory in real-time      | `watch -n 1 'free -h'`                          |

> 💡 This approach helps determine whether the system is **CPU-bound, memory-bound, or disk-bound**, allowing targeted troubleshooting.  

---
