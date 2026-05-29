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

# Active Directory Authentication & Group Policies

---

# Group Policies (GPOs)

Group Policies are collections of settings applied to:
- users
- computers
- organizational units (OUs)

GPOs help administrators enforce:
- security settings
- system configurations
- organizational policies

Examples:
- password policies
- firewall rules
- USB restrictions

---

# SYSVOL

SYSVOL is a network share used to distribute:
- Group Policies
- login scripts
- domain-wide configurations

across the network.

---

# Authentication Methods

Active Directory commonly uses two authentication protocols:
- Kerberos
- NetNTLM

---

# Kerberos Authentication

Kerberos is the default authentication protocol in modern Windows domains.

It uses a trusted third party called:
- Key Distribution Center (KDC)

Passwords are not repeatedly transmitted across the network.

---

# Kerberos Process

## Step 1
User logs in.

The KDC verifies credentials and issues:
- Ticket Granting Ticket (TGT)

---

## Step 2
When accessing a service:
- the client presents the TGT
- requests a Service Ticket

---

## Step 3
The Service Ticket is presented to the target server for access.

---

# Benefits of Kerberos

- centralized authentication
- improved security
- reduced password exposure
- scalable enterprise authentication

---

# NetNTLM Authentication

NetNTLM is an older legacy authentication protocol.

It uses:
- challenge-response authentication

instead of ticket-based authentication.

NetNTLM is mainly kept for compatibility purposes.

---

# Active Directory Tree

A Tree is a collection of domains sharing:
- a continuous namespace
- a parent-child relationship

Example:
- company.com
- hr.company.com
- it.company.com

Domains inside a tree automatically trust each other.

---

# Active Directory Forest

A Forest is the highest organizational boundary inside Active Directory.

It consists of:
- one or more separate domain trees

Different trees inside a forest may have different names but share:
- schema
- global catalog
- trust relationships

---

# Trusts

Trusts are authentication bridges between:
- domains
- trees
- forests

They allow users in one domain to access resources in another.

---

# Types of Trusts

## Transitive Trust
Trust automatically extends across connected domains.

---

## Non-Transitive Trust
Trust exists only between two specific domains.

---

## One-Way Trust
One domain can access another, but not vice versa.

---

## Two-Way Trust
Both domains can access each other.

---

# Reflection

This module focused heavily on:
- enterprise authentication
- Kerberos
- Active Directory infrastructure
- trust relationships
- Group Policies

Most challenging areas:
- Kerberos ticket flow
- forests and trusts
- enterprise authentication architecture

Overall understanding:
Approximately 50% to 60%.
