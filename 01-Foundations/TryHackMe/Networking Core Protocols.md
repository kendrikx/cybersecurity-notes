# Networking Core Protocols

## Overview

Core networking protocols allow devices, applications, and users to communicate across networks and the Internet.

Understanding these protocols is essential for:

- Cybersecurity
- SOC Analysis
- Network Administration
- Incident Response
- Penetration Testing

---

# DNS (Domain Name System)

## What is DNS?

DNS is the Internet's phonebook.

Humans remember names:

```text
google.com
```

Computers communicate using IP addresses:

```text
142.250.190.78
```

DNS translates domain names into IP addresses.

---

## DNS Resolution Process

```text
User Types:

google.com
      ↓

DNS Query
      ↓

DNS Server
      ↓

Returns IP Address
      ↓

142.250.190.78
      ↓

Browser Connects
```

---

## DNS Port

| Protocol | Port |
|----------|------|
| DNS | 53 |

Transport:

```text
UDP 53
```

Used for speed.

```text
TCP 53
```

Used when responses are larger.

---

## DNS Record Types

### A Record

Maps a domain name to an IPv4 address.

```text
google.com
↓
142.250.190.78
```

---

### AAAA Record

Maps a domain name to an IPv6 address.

```text
google.com
↓
2001:4860:4860::8888
```

---

### CNAME Record

Creates an alias.

```text
www.company.com
↓
company.com
```

---

### MX Record

Identifies the mail server.

```text
company.com
↓
mail.company.com
```

---

# WHOIS

## What is WHOIS?

WHOIS is a protocol used to discover ownership information about domains and IP addresses.

---

## WHOIS Information

A WHOIS lookup can reveal:

- Domain Owner
- Registration Date
- Expiration Date
- Contact Information
- Nameservers

---

## WHOIS Process

```text
Domain Name
      ↓
WHOIS Query
      ↓
WHOIS Database
      ↓
Ownership Information
```

---

## WHOIS Port

| Protocol | Port |
|----------|------|
| WHOIS | 43 |

Transport:

```text
TCP 43
```

---

## Modern Replacement

WHOIS is gradually being replaced by:

```text
RDAP
(Registration Data Access Protocol)
```

---

# HTTP

## What is HTTP?

HTTP allows web browsers and web servers to communicate.

When you open a website:

```text
Browser
↓
HTTP Request
↓
Web Server
↓
HTTP Response
```

---

## HTTP Port

| Protocol | Port |
|----------|------|
| HTTP | 80 |

Transport:

```text
TCP 80
```

---

## HTTP Characteristics

### Plain Text

Everything is visible.

```text
Username
Password
Messages
```

can potentially be intercepted.

---

### Stateless

Every request is independent.

```text
Request
↓
Response
↓
Connection Ends
```

---

# HTTPS

## What is HTTPS?

HTTPS is secure HTTP.

It uses SSL/TLS encryption to protect communications.

---

## HTTPS Port

| Protocol | Port |
|----------|------|
| HTTPS | 443 |

Transport:

```text
TCP 443
```

---

## HTTPS Security Benefits

### Confidentiality

Only intended parties can read data.

---

### Authentication

Verifies website identity.

---

### Integrity

Detects tampering.

---

## HTTPS Flow

```text
Browser
     ↓
TLS Handshake
     ↓
Encrypted Tunnel
     ↓
Website
```

---

# FTP (File Transfer Protocol)

## What is FTP?

FTP is used to transfer files between systems.

---

## FTP Channels

FTP uses two separate connections.

### Command Channel

Used for commands.

Examples:

```text
ls
get
put
```

Port:

```text
TCP 21
```

---

### Data Channel

Used for actual file transfers.

Port:

```text
TCP 20
```

---

## FTP Architecture

```text
Client
   │
   ├── Command Channel (21)
   │
   └── Data Channel (20)
          ↓
       FTP Server
```

---

## FTP Modes

### Active Mode

```text
Server
↓
Initiates Data Connection
↓
Client
```

---

### Passive Mode

```text
Client
↓
Initiates Both Connections
↓
Server
```

Most firewall-friendly mode.

---

## Secure Alternative

```text
SFTP
```

Runs over:

```text
SSH Port 22
```

Provides encryption.

---

# Email Protocols

Email relies on multiple protocols working together.

---

# SMTP

## Role

SMTP sends email.

Think:

```text
Outbox
```

---

## SMTP Flow

```text
Your Device
      ↓
SMTP Server
      ↓
Recipient Mail Server
```

---

## SMTP Ports

| Port | Purpose |
|--------|--------|
| 25 | Server-to-Server |
| 587 | Modern Email Submission |

---

# POP3

## Role

POP3 downloads email to a device.

Think:

```text
Download and Keep
```

---

## POP3 Port

```text
TCP 110
```

---

## POP3 Diagram

```text
Mail Server
      ↓
Downloads Email
      ↓
Laptop
```

Usually removes mail from server.

---

# IMAP

## Role

IMAP synchronizes email.

Think:

```text
Sync Everywhere
```

---

## IMAP Port

```text
TCP 143
```

---

## IMAP Diagram

```text
          Mail Server
          /        \
         /          \
     Phone        Laptop
         \          /
          \        /
         Same Inbox
```

---

## Benefits

Read an email on:

```text
Phone
```

It automatically shows as read on:

```text
Laptop
Tablet
Desktop
```

---

# Protocol Mastery Table

| Protocol | Purpose | Transport | Port |
|-----------|-----------|-----------|---------|
| DNS | Name Resolution | UDP/TCP | 53 |
| WHOIS | Domain Information | TCP | 43 |
| HTTP | Web Browsing | TCP | 80 |
| HTTPS | Secure Web Browsing | TCP | 443 |
| FTP | File Transfer | TCP | 20/21 |
| SMTP | Send Email | TCP | 25 / 587 |
| POP3 | Download Email | TCP | 110 |
| IMAP | Synchronize Email | TCP | 143 |

---

# Real World Example

Opening:

```text
https://google.com
```

What happens?

1. DNS finds Google's IP.

```text
google.com
↓
142.250.x.x
```

2. Browser connects using HTTPS.

```text
TCP 443
```

3. TLS creates encryption.

4. HTTP requests travel inside the encrypted tunnel.

5. Webpage loads.

```text
DNS
↓
TCP
↓
HTTPS
↓
Google Website
```

---

# Key Takeaways

- DNS translates names into IP addresses.
- WHOIS identifies domain ownership.
- HTTP provides web communication in plain text.
- HTTPS secures web traffic using TLS encryption.
- FTP transfers files using two channels.
- SMTP sends email.
- POP3 downloads email to one device.
- IMAP synchronizes email across multiple devices.
- DNS, HTTP/HTTPS and Email protocols are among the most commonly investigated protocols in cybersecurity.