## 1. Show System Info

# Concept: system commands

```bash
#!/bin/bash

echo "Current Date: $(date)"
echo "Logged in user: $(whoami)"
echo "Current Directory: $(pwd)"
```

---

## 2. Hello + User Input Script
# Concept: variables, input, echo

```copy
#!/bin/bash

echo "Enter your name:"
read name

echo "Hello, $name! Welcome to Linux scripting."
```
---

## 3. Simple Calculator

# Concept: arithmetic

```bash
#!/bin/bash

echo "Enter first number:"
read a

echo "Enter second number:"
read b

sum=$((a + b))

echo "Sum: $sum"
```
---

## 4. Count Files in a Directory

# Concept: command substitution

```bash
#!/bin/bash

echo "Enter directory path:"
read dir

count=$(ls "$dir" | wc -l)

echo "Number of files: $count"
```
---

## 5. Website Status Checker
📌 Idea:

Check if a website is up

```bash
#!/bin/bash

echo "Enter website URL:"
read url

status=$(curl -o /dev/null -s -w "%{http_code}" "$url")

if [ "$status" -eq 200 ]; then
    echo "✅ Website is up"
else
    echo "❌ Website is down (Status: $status)"
fi
```
---

## 6. System Health Report

```bash
#!/bin/bash

echo "===== SYSTEM REPORT ====="
echo "User: $(whoami)"
echo "Uptime: $(uptime -p)"
echo "Memory Usage:"
free -h
echo "Disk Usage:"
df -h
```
---

## 7. Simple User Manager
📌 Idea:

Create and delete Linux users

```bash
#!/bin/bash

echo "1. Create User"
echo "2. Delete User"
read choice

echo "Enter username:"
read username

if [ "$choice" -eq 1 ]; then
    sudo useradd "$username"
    echo "User created"
elif [ "$choice" -eq 2 ]; then
    sudo userdel "$username"
    echo "User deleted"
else
    echo "Invalid choice"
fi
```
---
