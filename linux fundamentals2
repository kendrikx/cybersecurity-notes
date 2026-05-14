# Linux Fundamentals: Basic Commands & Navigation

## Navigation Commands

- `pwd` — Show current working directory (Print Working Directory)
- `ls` — List files and folders in the current directory
- `cd` — Change directory (move between folders)

### Common `cd` Usage
- `cd <folder>` → Go into a folder
- `cd ..` → Go up one level
- `cd \~` → Go to home directory
- `cd -` → Go back to previous directory

---

## Getting Help

- `man <command>` — Open the full manual page for a command (e.g., `man ls`)
- `<command> --help` — Quick help menu with options (e.g., `ls --help`)

---

## File and Directory Management

- `touch <filename>` — Create an empty file
- `mkdir <foldername>` — Create a new directory
- `cp <source> <destination>` — Copy files or folders
- `mv <source> <destination>` — Move or rename files/folders
- `rm <filename>` — Remove (delete) a file
- `rm -r <folder>` — Remove a folder recursively (use with caution)

### Hidden Files
- `ls -a` — Show hidden files (files starting with `.`)

### Wildcards
- `*` — Matches any number of characters (e.g., `*.txt` for all text files)

---

## File Information

- `file <filename>` — Determine the type of a file

---

## Flags (Options)

Flags change how a command behaves.

- **Short flags**: `-l` (e.g., `ls -l`)
- **Long flags**: `--list` (e.g., `ls --list`)

---

## File Permissions (`ls -l` output)

### 1) Common Permission: `-rw-r--r--`
**Meaning**: Everyone can read the file, but only the owner can edit it.

**Breakdown**:
- `-` → Regular file
- `rw-` → Owner: Read + Write
- `r--` → Group: Read only
- `r--` → Others: Read only

### 2) Strict Permission: `-rw-------` (Numeric: **600**)
**Meaning**: Only the owner can read or write. Very secure.

**Used for**: SSH private keys, passwords, API keys, secret config files.

### 3) Directory Example: `drwx------` (Numeric: **700**)
**Meaning**: Only the owner can access this folder.

**Common Numeric Permissions**:
- `777` → Everyone can do everything (very permissive)
- `755` → Owner full access, others read & execute (common for folders)
- `644` → Owner can edit, others read only (common for files)
- `600` → Only owner can read/write
- `700` → Only owner can access directory

---

## Important System Directories

- `/` → Root directory (start of the entire filesystem)
- `/home` → User home directories
- `/etc` → Configuration files
- `/var` → Logs and variable data
- `/tmp` → Temporary files

---

## SSH

SSH allows secure remote connection to Linux servers.

---

## User & Privilege Commands

- `su` — Switch User
  - `su -` or `su -l` → Proper login as another user (loads full environment)
- `sudo` — Superuser do (run a single command as root)
  - `sudo -i` or `sudo su` → Get a full root shell

---

## Why Permissions Matter

Linux is a multi-user system. Permissions help:
- Control who can read, modify, or execute files
- Prevent accidents and unauthorized access
- Keep the system secure

---

## Reflection

**What I understood well**:
- Navigation commands
- Basic file management (`touch`, `mkdir`, `cp`, `mv`, `rm`)
- SSH basics
- File permissions concepts

**What was difficult**:
- Merging files
- Initial navigation confusion
- Remembering permission numbers

**Progress**: Completed basic navigation and file management topics.

---

**Next Topics to Cover**: Process management, package management, cron jobs, logs, and advanced permissions.