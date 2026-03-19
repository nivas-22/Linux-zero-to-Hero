## Exercise 1: Install and Manage Web Server


**Install nginx**
$ sudo apt - get install nginx #Ubuntu
$ sudo yum install nginx # CentOS

**Check status**
$ sudo systemctl status nginx

**Start/stop/restart**
$ sudo systemctl stop nginx
$ systemctl is - active nginx
$ sudo systemctl start nginx
$ systemctl is - active nginx

**Enable at boot**
$ sudo systemctl enable nginx
$ systemctl is - enabled nginx

---

## Exercise 2: Explore Running Services

$ systemctl list - units -- type = service | head -20
$ systemctl list - units -- failed
$ systemctl cat sshd . service

---
## Exercise 3: Compare systemctl and service

$ sudo systemctl status nginx
$ sudo service nginx status
**Both work on modern systems !**

---
# 🎯 Interview Questions (systemd)

---

## ❓ Q1: What is the difference between `systemctl enable` and `systemctl start`?

> start starts the service immediately for the current session only. enable creates symbolic links
> so the service starts automatically at boot, but doesn’t start it now. Use enable –now to do both.

- `systemctl start`  
  - Starts the service immediately  
  - Affects only the current session  
  - Does not persist after reboot  

- `systemctl enable`  
  - Configures the service to start automatically at boot  
  - Does not start the service immediately  
  - Creates symbolic links for auto-start  

✅ To do both at once:
```bash id="e1n2a3"
systemctl enable --now SERVICE
```

---

## ❓ Q2: How do you check why a service failed to start?

>Use systemctl status service-name to see recent logs, or journalctl -u service-name for
>full logs. Check journalctl -xe for the most recent errors with explanations.

Check service status:

`systemctl status SERVICE`

View detailed logs:

`journalctl -u SERVICE`

View recent system errors:

`journalctl -xe`

---

## ❓ Q3: What is the difference between restart and reload?

> restart stops and starts the service (brief downtime). reload tells the service to re-read its
> configuration without stopping (no downtime). Not all services support reload.

`systemctl restart`

- Stops and then starts the service

- Causes brief downtime

`systemctl reload`

- Reloads configuration without stopping the service (No downtime)

- Not supported by all services
