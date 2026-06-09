# Linux Shell Scripting Fundamentals

## Overview

Linux Shell Scripting allows users to automate tasks by writing commands into a file and executing them as a program.

Shell scripting is commonly used for:

- System administration
- Security monitoring
- Log analysis
- Automation
- DevOps
- Cybersecurity operations

---

# Script Structure

Most Bash scripts begin with:

```bash
#!/bin/bash
```

This is called a shebang.

It tells Linux to execute the script using the Bash interpreter.

---

# Hello World Script

Create a file:

```bash
nano hello.sh
```

Content:

```bash
#!/bin/bash

echo "Hello World"
```

Make executable:

```bash
chmod +x hello.sh
```

Run:

```bash
./hello.sh
```

Output:

```text
Hello World
```

---

# Variables

Variables store data.

Example:

```bash
#!/bin/bash

name="Henry"

echo $name
```

Output:

```text
Henry
```

---

# User Input

Scripts can receive information from users.

Example:

```bash
#!/bin/bash

echo "Enter your name:"
read name

echo "Hello $name"
```

Output:

```text
Enter your name:
Henry

Hello Henry
```

---

# Display System Information

Current user:

```bash
#!/bin/bash

whoami
```

Current directory:

```bash
#!/bin/bash

pwd
```

Operating system:

```bash
#!/bin/bash

uname -a
```

---

# Conditional Statements

Used for decision making.

Example:

```bash
#!/bin/bash

age=20

if [ $age -ge 18 ]
then
    echo "Adult"
fi
```

Output:

```text
Adult
```

---

# If Else Statement

```bash
#!/bin/bash

age=15

if [ $age -ge 18 ]
then
    echo "Adult"
else
    echo "Minor"
fi
```

Output:

```text
Minor
```

---

# For Loop

Used when repeating actions a known number of times.

```bash
#!/bin/bash

for i in 1 2 3 4 5
do
    echo $i
done
```

Output:

```text
1
2
3
4
5
```

---

# While Loop

Repeats while a condition remains true.

```bash
#!/bin/bash

counter=1

while [ $counter -le 5 ]
do
    echo $counter
    counter=$((counter+1))
done
```

Output:

```text
1
2
3
4
5
```

---

# Creating Directories Automatically

```bash
#!/bin/bash

mkdir testfolder

echo "Folder created"
```

---

# Creating Multiple Directories

```bash
#!/bin/bash

for i in 1 2 3
do
    mkdir Folder$i
done
```

Creates:

```text
Folder1
Folder2
Folder3
```

---

# Working With Files

Create file:

```bash
touch notes.txt
```

Copy file:

```bash
cp notes.txt backup.txt
```

Move file:

```bash
mv notes.txt Documents/
```

Delete file:

```bash
rm notes.txt
```

---

# Searching With Grep

Search text inside files.

File:

```text
apple
banana
orange
```

Command:

```bash
grep banana fruits.txt
```

Output:

```text
banana
```

---

# File Permissions

View permissions:

```bash
ls -l
```

Example:

```text
-rw-r--r--
```

Permission changes:

```bash
chmod 755 script.sh
```

```bash
chmod 644 notes.txt
```

Common permissions:

| Permission | Meaning |
|------------|----------|
| 777 | Full access to everyone |
| 755 | Owner full, others read and execute |
| 644 | Owner read/write, others read |
| 600 | Owner only |

---

# Ownership

View ownership:

```bash
ls -l
```

Change owner:

```bash
sudo chown user file.txt
```

Change owner and group:

```bash
sudo chown user:group file.txt
```

Purpose:

- Controls who owns files
- Controls access management

---

# Basic Networking Script

Check internet connectivity:

```bash
#!/bin/bash

ping -c 4 google.com
```

---

# Display Network Information

```bash
#!/bin/bash

ip addr
```

---

# Simple Backup Script

```bash
#!/bin/bash

cp important.txt important_backup.txt

echo "Backup completed"
```

Output:

```text
Backup completed
```

---

# Log Monitoring Example

View login logs:

```bash
cat /var/log/auth.log
```

Search failed logins:

```bash
grep "Failed" /var/log/auth.log
```

Cybersecurity Use:

- Detect brute force attacks
- Investigate unauthorized access attempts

---

# Cybersecurity Applications

Linux scripting is used for:

- Log analysis
- Threat hunting
- User auditing
- Security monitoring
- Backup automation
- Incident response
- Vulnerability management

---

# Key Commands Learned

## Navigation

```bash
pwd
cd
ls
```

## File Management

```bash
cp
mv
rm
touch
mkdir
```

## Searching

```bash
grep
find
```

## Permissions

```bash
chmod
chown
```

## Networking

```bash
ping
ip addr
```

## Scripting

```bash
#!/bin/bash
read
if
else
for
while
```

---

# Key Takeaways

- Shell scripts automate tasks.
- Bash is the most common Linux shell.
- Variables store data.
- Loops repeat actions.
- Conditions make decisions.
- chmod manages permissions.
- chown manages ownership.
- grep searches text.
- Linux scripting is heavily used in cybersecurity and system administration.