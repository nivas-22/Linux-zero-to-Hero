# 📚 Linux Command Quick Reference

## 🧾 Commands Overview

| Command  | Purpose                  | Common Usage              |
|----------|--------------------------|---------------------------|
| chmod    | Change permissions       | `chmod 755 file`          |
| stat     | File status              | `stat -c "%a" file`       |
| umask    | Default permissions      | `umask 022`               |
| chown    | Change owner             | `chown user:group file`   |
| chgrp    | Change group             | `chgrp group file`        |
| useradd  | Create user              | `useradd -m user`         |
| usermod  | Modify user              | `usermod -aG group user`  |
| passwd   | Change password          | `passwd user`             |
| ps       | Process status           | `ps aux`                  |
| top/htop | Monitor processes        | `top -u user`             |
| kill     | Terminate process        | `kill -9 PID`             |
| df       | Disk free space          | `df -hT`                  |
| du       | Disk usage               | `du -sh /path`            |
| lsblk    | List block devices       | `lsblk -f`                |
| mount    | Mount filesystem         | `mount /dev/sdb1 /mnt`    |

---

## 💡 Tips

- Use `-h` for human-readable output (e.g., `df -h`, `du -sh`)
- Use `-R` for recursive operations where applicable
- Be cautious with `kill -9` (force kill)
- Always verify before using `mount` or permission-changing commands

---
