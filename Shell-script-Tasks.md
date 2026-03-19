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

