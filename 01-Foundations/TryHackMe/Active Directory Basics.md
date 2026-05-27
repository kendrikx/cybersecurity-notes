# Active Directory Basics

---

# Windows Domain

A Windows Domain is a group of:
- users
- computers
- devices

managed centrally under a single database.

Domains help organizations manage users, security, and resources efficiently.

---

# Advantages of Active Directory

## Centralized Identity Management
Administrators can manage all users and devices from one location.

---

## Security Policy Management
Security policies can be configured centrally and applied across the network.

Examples:
- password policies
- firewall rules
- software restrictions

---

# Active Directory Domain Services (AD DS)

AD DS is the core Windows service running on a:
- Domain Controller

It stores and manages information about network objects.

Examples of objects:
- users
- computers
- groups
- printers

---

# Active Directory Users

Users represent digital identities for people inside a corporate network.

---

# Component 1: Identity

Represents who the user is.

Includes:
- username
- password
- login credentials
- domain information

---

# Component 2: Permissions

Controls what the user can access.

Examples:
- files
- systems
- applications

---

# Main Benefits of AD Users

## Log In Anywhere
Users can access company resources from multiple devices within the domain.

---

## Instant Access Control
Administrators can disable user access immediately if required.

---

# Active Directory Machines

Computers also have identities inside Active Directory.

Each device has:
- a computer name
- authentication credentials
- assigned policies

---

# Device Policies

Administrators can enforce:
- firewall rules
- security updates
- USB restrictions
- configuration settings

even when users are not logged in.

---

# Main Benefits of AD Machines

## Bulk Administration
Administrators can manage many systems simultaneously.

---

## Easy Department Changes
Devices and users can be reorganized efficiently.

---

# Organizational Units (OUs)

Organizational Units are containers used to organize:
- users
- groups
- computers

inside Active Directory.

---

# Benefits of OUs

## Targeted Policies
Policies can be applied to specific departments or teams.

Example:
- Finance Department
- Human Resources
- IT Department

---

## Delegated Control
Administrative responsibilities can be assigned to specific teams.

---

# Access Control & Permissions

Permissions determine what users are allowed to:
- access
- modify
- use

Users can belong to multiple groups at the same time.

---

# Reflection

This module introduced:
- Windows Domains
- Active Directory
- AD users
- domain machines
- organizational units
- centralized administration

Main challenge areas:
- PowerShell user management
- password management commands
- enterprise administration syntax

Overall understanding:
Approximately 70% to 80%.