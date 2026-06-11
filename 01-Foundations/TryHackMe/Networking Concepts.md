# Networking Concepts

## Overview

Networking is the foundation of cybersecurity. Every device, server, website, and application communicates through networks.

Understanding networking helps security professionals:

- Analyze network traffic
- Investigate incidents
- Configure firewalls
- Troubleshoot connectivity issues
- Detect malicious activity
- Secure enterprise environments

---

# The OSI Model

The Open Systems Interconnection (OSI) Model is a conceptual framework created by ISO to explain how data travels across a network.

The model contains seven layers.

```text
+-----------------------+
| 7. Application        |
+-----------------------+
| 6. Presentation       |
+-----------------------+
| 5. Session            |
+-----------------------+
| 4. Transport          |
+-----------------------+
| 3. Network            |
+-----------------------+
| 2. Data Link          |
+-----------------------+
| 1. Physical           |
+-----------------------+
```

### Mnemonic

```text
Please
Do
Not
Throw
Spinach
Pizza
Away
```

---

# OSI Layer Summary

| Layer | Name | Function | Examples |
|---------|---------|---------|---------|
| 7 | Application | User-facing network services | HTTP, FTP, DNS, SMTP |
| 6 | Presentation | Formatting, encryption, compression | JPEG, PNG, MIME |
| 5 | Session | Creates and manages sessions | RPC, NFS |
| 4 | Transport | End-to-end communication | TCP, UDP |
| 3 | Network | Logical addressing and routing | IP, ICMP |
| 2 | Data Link | Local network communication | Ethernet, WiFi |
| 1 | Physical | Physical transmission of data | Electrical signals, Fiber |

---

# The TCP/IP Model

The TCP/IP Model is the practical networking model used on the Internet.

```text
+---------------------+
| Application Layer   |
+---------------------+
| Transport Layer     |
+---------------------+
| Internet Layer      |
+---------------------+
| Link Layer          |
+---------------------+
```

### Layer Functions

### Application Layer

Provides services to users and applications.

Examples:

- HTTP
- HTTPS
- DNS
- SSH
- Telnet

---

### Transport Layer

Responsible for host-to-host communication.

Protocols:

- TCP
- UDP

---

### Internet Layer

Responsible for routing traffic between networks.

Protocols:

- IP
- ICMP

---

### Link Layer

Handles communication on local networks.

Examples:

- Ethernet
- WiFi

---

# IP Addresses

An IP address identifies a device on a network.

## IPv4

IPv4 uses 32 bits.

Example:

```text
192.168.1.1
```

Structure:

```text
192 . 168 . 1 . 1
 |     |     |    |
Octet Octet Octet Octet
```

Each octet ranges from:

```text
0 - 255
```

Total IPv4 addresses:

```text
≈ 4.3 Billion
```

---

## IPv6

IPv6 uses 128 bits.

Example:

```text
2001:db8::1
```

IPv6 was introduced because the world is running out of IPv4 addresses.

Benefits:

- More addresses
- Better scalability
- Improved efficiency

---

# Subnetting

Subnetting divides a large network into smaller networks.

Benefits:

- Better organization
- Improved security
- Reduced network congestion

Example:

```text
IP Address:
192.168.1.50

Subnet Mask:
255.255.255.0
```

Result:

```text
Network Portion:
192.168.1

Host Portion:
50
```

Diagram:

```text
192.168.1.50
|-------|
 Network

          |--|
          Host
```

---

# TCP vs UDP

Both operate at Layer 4 (Transport Layer).

## TCP

TCP establishes a connection before sending data.

Characteristics:

- Reliable
- Ordered delivery
- Error checking
- Guaranteed delivery
- Slower

Used for:

- Websites
- Email
- File transfers
- Banking applications

---

### TCP Three-Way Handshake

```text
Client          Server

SYN --------->

     <--------- SYN/ACK

ACK --------->
```

Connection Established

---

## UDP

UDP does not establish a connection.

Characteristics:

- Fast
- Lightweight
- No delivery guarantee
- No error recovery

Used for:

- Gaming
- Streaming
- VoIP
- Video calls

---

# Encapsulation

Encapsulation is the process where each networking layer adds information before passing data to the next layer.

Flow:

```text
Application Layer
        |
       Data
        |
Transport Layer
        |
     Segment
        |
Internet Layer
        |
      Packet
        |
 Link Layer
        |
      Frame
        |
Physical Layer
        |
       Bits
```

---

## Encapsulation Process

```text
Data
 ↓
Segment
 ↓
Packet
 ↓
Frame
 ↓
Bits
```

### Added Information

| Layer | Data Unit | Added Information |
|---------|---------|---------|
| Application | Data | User Data |
| Transport | Segment | Port Numbers |
| Network | Packet | IP Addresses |
| Data Link | Frame | MAC Addresses |
| Physical | Bits | Binary Transmission |

---

# De-Encapsulation

The receiving device reverses the process.

```text
Bits
 ↓
Frame
 ↓
Packet
 ↓
Segment
 ↓
Data
```

This allows the original information to be reconstructed.

---

# Telnet

Telnet is a remote administration protocol.

### Default Port

```text
TCP 23
```

### Purpose

Allows administrators to remotely connect to systems using a command-line interface.

Example:

```bash
telnet 192.168.1.10
```

---

## Security Problem

Telnet sends everything in plain text.

This includes:

- Usernames
- Passwords
- Commands

Attackers monitoring traffic can read everything.

Diagram:

```text
Client
   |
   | Plain Text
   |
Network
   |
Attacker Reads Traffic
   |
Server
```

---

# SSH (Secure Shell)

SSH replaced Telnet.

Default Port:

```text
TCP 22
```

Benefits:

- Encryption
- Secure authentication
- Secure remote administration

Diagram:

```text
Client
   |
Encrypted Traffic
   |
Network
   |
Server
```

---

# Key Takeaways

- The OSI model contains 7 layers.
- The TCP/IP model contains 4 layers.
- IPv4 uses 32 bits.
- IPv6 uses 128 bits.
- Subnetting divides networks into smaller sections.
- TCP is reliable and connection-oriented.
- UDP is fast and connectionless.
- Encapsulation adds headers as data moves down the stack.
- De-encapsulation removes headers as data moves up the stack.
- Telnet uses TCP Port 23 and is insecure.
- SSH uses TCP Port 22 and provides secure remote access.

---

