# Networking Security Protocols

## Overview

Networking security protocols protect data as it travels across networks by providing:

- Confidentiality
- Integrity
- Authentication
- Secure communication

These protocols are fundamental in cybersecurity because they prevent attackers from reading, modifying or impersonating communications.

---

# Transport Layer Security (TLS)

## What is TLS?

Transport Layer Security (TLS) is a cryptographic protocol that encrypts communication between applications over an untrusted network.

TLS protects:

- Passwords
- Cookies
- Banking information
- Emails
- Web traffic

---

## OSI Placement

```text
Layer 7  Application
        ▲
        │
      TLS
        │
        ▼
Layer 4  TCP
```

TLS sits between the Application Layer and the Transport Layer.

---

## TLS Handshake

Before encrypted communication begins, both devices establish trust.

```text
Client
   │
1. Client Hello
   │
   ▼
Server
   │
2. Server Hello
   │
   ▼
Certificate Sent
   │
3. Authentication
   │
   ▼
4. Key Exchange
   │
   ▼
5. Secure Encrypted Session
```

---

## TLS Provides

### Confidentiality

Data is encrypted.

### Integrity

Data cannot be modified without detection.

### Authentication

The client verifies it is talking to the legitimate server.

---

# HTTP vs HTTPS

## HTTP

Protocol:

```text
Hypertext Transfer Protocol
```

Port:

```text
80
```

Characteristics

- No encryption
- Plain text
- Vulnerable to interception

---

## HTTPS

Protocol:

```text
HTTP Secure
```

Port

```text
443
```

HTTPS simply means:

```text
HTTP
      ↓
Wrapped inside
      ↓
TLS Encryption
```

---

## Diagram

```text
Browser
    │
HTTPS Request
    │
TLS Encryption
    │
Secure Internet
    │
Web Server
```

---

# Secure Email Protocols

Email communication uses different protocols for sending and receiving messages.

---

## SMTP

Purpose

Send email.

Ports

```text
25
```

Traditional SMTP

```text
465 / 587
```

Secure SMTP

---

## POP3

Purpose

Download emails to one device.

Ports

```text
110
```

Secure version

```text
995
```

Diagram

```text
Mail Server
      │
Downloads
      ▼
Laptop
```

---

## IMAP

Purpose

Synchronize emails across devices.

Ports

```text
143
```

Secure version

```text
993
```

Diagram

```text
          Mail Server
         /           \
     Phone         Laptop
         \           /
          Tablet
```

Email remains stored on the server.

---

# Secure Remote Access

## Telnet

Port

```text
23
```

Characteristics

- Plain text
- No encryption
- Legacy protocol

---

## SSH

Port

```text
22
```

Characteristics

- Encrypted
- Secure authentication
- Remote administration
- Secure file transfer

Diagram

```text
Administrator
      │
Encrypted SSH Tunnel
      │
Remote Server
```

---

# Secure File Transfer

## FTP

Ports

```text
21
```

Command Channel

```text
20
```

Data Channel

No encryption.

---

## FTPS

Uses TLS to encrypt FTP communication.

Ports

```text
989
990
```

---

## SFTP

Runs over SSH.

Port

```text
22
```

Diagram

```text
Client
     │
Encrypted SSH Tunnel
     │
Server
```

Only one encrypted connection is required.

---

# VPN (Virtual Private Network)

## What is a VPN?

A VPN creates an encrypted tunnel through the Internet.

Instead of exposing your traffic directly, everything travels inside the tunnel.

---

## VPN Diagram

```text
Computer
      │
Encrypted VPN Tunnel
      │
VPN Server
      │
Internet
```

---

## VPN Benefits

### Confidentiality

Traffic is encrypted.

### IP Masking

Your real public IP is hidden.

### Secure Tunneling

Private traffic safely crosses the public Internet.

---

## VPN Types

### Remote Access VPN

Employee connects securely to company.

```text
Laptop
    │
VPN
    │
Company Network
```

---

### Site-to-Site VPN

Two offices connected securely.

```text
Office A
     │
Encrypted Tunnel
     │
Office B
```

---

# Port Forwarding

## What is Port Forwarding?

Port Forwarding allows external traffic to reach an internal device.

Normally:

```text
Internet

❌ Cannot reach

192.168.1.10
```

With Port Forwarding:

```text
Internet
      │
Router
Port 8080
      │
192.168.1.10
```

The router forwards incoming traffic to the correct internal device.

---

# Firewalls

## What is a Firewall?

A firewall monitors and filters incoming and outgoing network traffic according to security rules.

Diagram

```text
Internet
     │
Firewall
     │
Internal Network
```

---

## Types of Firewalls

### Stateless Firewall

Checks every packet independently.

Looks only at:

- Source IP
- Destination IP
- Port

Fast but limited.

---

### Stateful Firewall

Tracks the entire connection.

Example

```text
Client
    │
Connection Started
    │
Firewall remembers session
    │
Allows return traffic
```

More secure than Stateless.

---

### Next Generation Firewall (NGFW)

Modern firewall that adds:

- Deep Packet Inspection
- Intrusion Prevention
- Malware Detection
- Application Awareness
- User Identity

---

# LAN Networking Devices

## Hub

OSI Layer

```text
Layer 1
```

Behavior

Broadcasts data to every connected device.

Diagram

```text
        Hub
     /  |  \
PC1 PC2 PC3
```

Everyone receives the frame.

---

## Switch

OSI Layer

```text
Layer 2
```

Uses MAC addresses.

Diagram

```text
PC1
   │
Switch
   │
PC2
```

Only the intended device receives the frame.

---

## Router

OSI Layer

```text
Layer 3
```

Uses IP addresses.

Diagram

```text
Home Network
      │
Router
      │
Internet
```

Routers connect different networks together.

---

# Secure vs Insecure Protocols

| Function | Insecure | Secure |
|-----------|----------|---------|
| Web Browsing | HTTP (80) | HTTPS (443) |
| Remote Access | Telnet (23) | SSH (22) |
| File Transfer | FTP (20/21) | FTPS (989/990), SFTP (22) |
| Email Sending | SMTP (25) | SMTPS (465/587) |
| Email Retrieval | POP3 (110), IMAP (143) | POP3S (995), IMAPS (993) |

---

# Key Takeaways

- TLS encrypts communication between applications.
- HTTPS is HTTP protected by TLS.
- SSH replaces Telnet for secure remote access.
- SFTP securely transfers files over SSH.
- FTPS secures traditional FTP using TLS.
- VPNs create encrypted tunnels across public networks.
- Port Forwarding exposes internal services through a router.
- Firewalls inspect and control network traffic.
- Hubs broadcast traffic to every device.
- Switches forward traffic using MAC addresses.
- Routers connect different IP networks using routing tables.