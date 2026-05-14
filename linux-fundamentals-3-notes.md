# Linux Fundamentals 3

## Process Management

### PID
Every running process has a unique Process ID (PID).

### ps Command
Used to view running processes.

### ps aux
- a = all users
- u = user-oriented format
- x = include processes without terminal

Difference:
- ps = current shell processes
- ps aux = detailed system-wide processes

---

## top Command

Used for:
- Real-time process monitoring
- CPU usage
- RAM usage
- System activity

Difference:
- ps aux = static snapshot
- top = live updating monitor

---

## Signals

### SIGTERM
Gracefully stop process.

### SIGKILL
Forcefully terminate process.

### SIGSTOP
Pause/suspend process.

---

## systemctl

Used to manage system services.

Examples:
- start services
- stop services
- enable services on boot

---

## Background & Foreground Processes

Foreground:
Runs directly in terminal.

Background:
Runs while terminal stays usable.

### fg Command
Brings background process to foreground.

---

## Cron Jobs

### crontab
Used for task automation and scheduling.

---

## Package Management

Concepts:
- installing software
- updating packages
- repositories

---

## Logs

Purpose:
- monitor system activity
- troubleshoot issues

---

## Reflection

Linux Fundamentals 3 was the hardest Linux module so far.

Strong areas:
- processes
- ps aux
- signals
- top command

Needs more practice:
- cron jobs
- logs
- package management
- systemctl