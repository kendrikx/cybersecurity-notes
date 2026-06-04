# Windows PowerShell

## Overview

Windows PowerShell is a cross-platform task automation solution consisting of:

- A command-line shell
- A scripting language
- A configuration management framework

Unlike traditional command prompts, PowerShell works with objects instead of plain text.

---

## Understanding Objects

In PowerShell, an object contains:

### Properties
Information about an item.

Examples:
- Name
- Size
- ID
- Status

### Methods
Actions that can be performed on an object.

Examples:
- Stop()
- Copy()
- Restart()

Objects make PowerShell powerful because data and functionality travel together through commands.

---

## Cmdlets

PowerShell commands are called Cmdlets.

They follow a Verb-Noun naming structure.

Examples:

### Get-Content
Retrieve and display file contents.

### Set-Location
Change the current directory.

### Get-Command
List available commands.

### Get-Help
Display documentation and examples.

### Get-Alias
Display command aliases.

### Find-Module
Search for modules in online repositories.

### Install-Module
Install modules from repositories.

---

## File System Navigation

### Get-ChildItem
List files and folders.

### New-Item
Create files or directories.

Common aliases:

| Command | Purpose |
|----------|----------|
| cd | Change directory |
| cd.. | Move up one directory |
| pwd | Print working directory |
| dir / ls | List files and folders |
| mkdir | Create directory |
| rmdir / rd | Remove directory |
| move | Move files |
| copy | Copy files |
| cls | Clear screen |
| ping | Test network connectivity |
| hostname | Display computer name |

---

# Core PowerShell Commands

## 1. Get-Command

Used to discover commands.

Examples:

### Search by Verb

```powershell
Get-Command -Verb New
```

### Search by Noun

```powershell
Get-Command -Noun File
```

---

## 2. Get-Help

Used to learn how commands work.

### Basic Information

```powershell
Get-Help Get-Process
```

### Examples

```powershell
Get-Help Get-Process -Examples
```

### Full Documentation

```powershell
Get-Help Get-Process -Full
```

---

## 3. Get-Member

Displays an object's properties and methods.

Example:

```powershell
Get-Process | Get-Member
```

Important concepts:

### Property

Stores information.

Examples:
- Name
- ID
- Company

### Method

Performs actions.

Examples:
- Kill()
- Start()

---

## 4. Select-Object

Used to display only desired information.

Example:

```powershell
Get-Process | Select-Object Name, Id, CPU
```

Display first five results:

```powershell
Get-Process | Select-Object -First 5
```

Combined:

```powershell
Get-Process | Select-Object Name, Id -First 5
```

---

## 5. Where-Object

Filters results based on conditions.

Common operators:

| Operator | Meaning |
|-----------|---------|
| -eq | Equals |
| -ne | Not Equal |
| -gt | Greater Than |
| -lt | Less Than |
| -like | Wildcard Match |

Examples:

### Find Stopped Services

```powershell
Get-Service | Where-Object Status -eq "Stopped"
```

### Find High Memory Processes

```powershell
Get-Process | Where-Object WorkingSet -gt 50MB
```

Shortcut:

```powershell
?
```

can replace:

```powershell
Where-Object
```

---

## 6. ForEach-Object

Performs an action on every item.

Example:

```powershell
Get-Service -Name xbox | ForEach-Object { Restart-Service }
```

Shortcut:

```powershell
%
```

can replace:

```powershell
ForEach-Object
```

---

# The Core Six PowerShell Commands

1. Get-Command → Find commands
2. Get-Help → Learn commands
3. Get-Member → Inspect objects
4. Select-Object → Select data
5. Where-Object → Filter data
6. ForEach-Object → Perform actions

---

# System Information Commands

## Get-ComputerInfo

Displays detailed system information.

Includes:
- Hardware
- BIOS
- Operating System

---

## Get-LocalUser

Displays local user accounts.

---

## Get-NetIPConfiguration

Displays network configuration details.

---

## Get-NetIPAddress

Displays IP address information.

---

# Network Monitoring

## Get-NetTCPConnection

Displays active TCP connections.

Useful for:
- Network troubleshooting
- Security investigations

---

# File Integrity

## Get-FileHash

Generates cryptographic hashes.

Common uses:

- File verification
- Malware analysis
- Integrity checking

---

# Key Takeaways

- PowerShell works with objects instead of plain text.
- Cmdlets use a Verb-Noun naming convention.
- The Core Six commands are essential for navigation and administration.
- PowerShell can automate administrative and security tasks.
- PowerShell is heavily used in enterprise environments and SOC operations.

---

## Reflection

This module introduced PowerShell fundamentals, object-based command execution, filtering, automation concepts, and system administration commands.

Understanding Level: ~60%

Next Target:
- Linux Command Line
- Bash Navigation
- Linux File Permissions
- Linux Process Management