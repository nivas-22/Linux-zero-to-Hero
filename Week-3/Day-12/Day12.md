# Services and Daemons

**Managing Background Services with systemd**

# ⚙️ Services and Daemons in Linux

- **Daemon:**  
  A background process that runs continuously.  
  Typically, daemon names end with a `d` (e.g., `sshd`, `httpd`, `mysqld`).

- **Service:**  
  A managed daemon that can be controlled using commands such as start, stop, and status.

- **systemd:**  
  The modern init system used in most Linux distributions.  
  It manages:
  - Services  
  - System startup  
  - Logging  
  - System state  

- **Unit Files:**  
  Configuration files used by systemd to define services.  
  Locations:
  - `/etc/systemd/system/`
  - `/lib/systemd/system/`

---

## 🔄 Service States

- **active (running):**  
  The service is currently running.

- **inactive (dead):**  
  The service is stopped.

- **enabled:**  
  The service is configured to start automatically at boot.

- **disabled:**  
  The service will not start automatically at boot.

- **masked:**  
  The service is completely blocked and cannot be started (even manually).

---

# ⚙️ Service Control Commands (systemd)

## 🔧 Basic Service Commands

1. `systemctl start SERVICE` — Start a service immediately  
2. `systemctl stop SERVICE` — Stop a service immediately  
3. `systemctl restart SERVICE` — Stop and then start a service  
4. `systemctl reload SERVICE` — Reload configuration without restarting  
5. `systemctl status SERVICE` — Show service status  
6. `systemctl enable SERVICE` — Enable service to start at boot  
7. `systemctl disable SERVICE` — Disable service from starting at boot  
8. `systemctl enable --now SERVICE` — Enable AND start the service immediately  
9. `systemctl is-active SERVICE` — Check if the service is running  
10. `systemctl is-enabled SERVICE` — Check if the service is enabled at boot  
11. `systemctl mask SERVICE` — Completely disable a service (cannot be started)  
12. `systemctl unmask SERVICE` — Remove masking from a service  

---

## 📋 Listing and Information Commands

13. `systemctl list-units` — List all active units  
14. `systemctl list-units --type=service` — List only services  
15. `systemctl list-units --failed` — List failed services  
16. `systemctl list-unit-files` — List all unit files  
17. `systemctl cat SERVICE` — Show the contents of a unit file  
18. `systemctl show SERVICE` — Display all properties of a service  
19. `systemctl daemon-reload` — Reload systemd configuration (after changes to unit files)
    
# 🔌 System Control Commands (systemd)

## ⚡ Power Management Commands

1. `systemctl reboot` — Reboot the system  
2. `systemctl poweroff` — Shut down the system  
3. `systemctl suspend` — Suspend the system (sleep mode)  
4. `systemctl hibernate` — Hibernate the system (save state to disk and power off)  

---

## 🎯 Target Management Commands

5. `systemctl get-default` — Show the current default target  
6. `systemctl set-default TARGET` — Set the default target (boot mode)  

---

# Commands:

**Check service status ( most common command )**

$ sudo systemctl status nginx
nginx . service - A high performance web server
Loaded : loaded (/ lib / systemd / system / nginx . service ; enabled )
Active : active ( running ) since Mon 2024 -01 -15 10:00:00 UTC
Process : 1234 ExecStart =/ usr / sbin / nginx ( code = exited , status =0)
Main PID : 1235 ( nginx )
Tasks : 2 ( limit : 4915)
Memory : 3.5 M
CGroup : / system . slice / nginx . service

+ -1235 nginx : master process / usr / sbin / nginx
+ -1236 nginx : worker process

**Start a service**
$ sudo systemctl start nginx

**Stop a service**
$ sudo systemctl stop nginx

**Restart a service ( stop + start )**
$ sudo systemctl restart nginx

**Reload configuration without stopping**
$ sudo systemctl reload nginx

**Reload OR restart ( reload if supported )** 
$ sudo systemctl reload - or - restart nginx

**Enable service to start at boot**
$ sudo systemctl enable nginx
Created symlink / etc / systemd / system / multi - user . target. wants / nginx. service

**Disable service from starting at boot**
$ sudo systemctl disable nginx
Removed / etc / systemd / system / multi - user . target. wants / nginx. service

**Enable AND start in one command**
$ sudo systemctl enable -- now nginx

**Check if service is running**
$ systemctl is - active nginx
active

**Check if service is enabled**
$ systemctl is - enabled nginx
enabled

---
