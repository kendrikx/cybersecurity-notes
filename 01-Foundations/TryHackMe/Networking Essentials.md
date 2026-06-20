# Networking Essentials

## Overview

Networking Essentials covers the core protocols and technologies that allow devices to communicate on local networks and across the Internet.

Understanding these concepts is critical for:

- Cybersecurity
- Network Administration
- SOC Analysis
- Incident Response
- Penetration Testing

---

# DHCP (Dynamic Host Configuration Protocol)

## What is DHCP?

DHCP automatically assigns network settings to devices when they join a network.

Instead of manually configuring every device, DHCP provides:

- IP Address
- Subnet Mask
- Default Gateway
- DNS Server

Without DHCP, users would have to configure these settings manually.

---

## DHCP DORA Process

DHCP uses a four-step process called DORA.

```text
Device                     DHCP Server

Discover ---------------->

         <---------------- Offer

Request ----------------->

         <---------------- Acknowledge
```

### DORA Meaning

| Step | Purpose |
|--------|--------|
| Discover | Device asks for network configuration |
| Offer | DHCP server offers an IP address |
| Request | Device requests offered address |
| Acknowledge | DHCP server confirms assignment |

---

## Example

```text
Laptop joins WiFi
↓
DHCP assigns:

IP Address: 192.168.1.10
Subnet Mask: 255.255.255.0
Gateway: 192.168.1.1
DNS: 8.8.8.8
```

---

# ARP (Address Resolution Protocol)

## What is ARP?

ARP translates an IP address into a MAC address.

Devices communicate using MAC addresses on local networks.

When a device knows an IP but not the MAC address, ARP is used.

---

## ARP Process

```text
PC A wants:
192.168.1.20

PC A:
"Who has 192.168.1.20?"

Broadcast to everyone
          ↓

PC B:
"I do"

Returns MAC Address
```

---

## Why ARP is Important

IP Address:

```text
192.168.1.20
```

MAC Address:

```text
00:1A:2B:3C:4D:5E
```

ARP connects Layer 3 (IP) with Layer 2 (MAC).

```text
IP Address
     ↓
    ARP
     ↓
MAC Address
```

---

# ICMP (Internet Control Message Protocol)

## What is ICMP?

ICMP is used for troubleshooting and reporting network status.

It helps determine:

- Whether a device is reachable
- Network errors
- Network performance

---

# Ping

Ping uses ICMP.

Purpose:

```text
"Are you alive?"
```

Response:

```text
"Yes, I am."
```

Example:

```bash
ping google.com
```

Diagram:

```text
Computer
   ↓
ICMP Request
   ↓
Google
   ↓
ICMP Reply
   ↓
Computer
```

---

# Traceroute

Traceroute shows every router hop between your device and a destination.

Example:

```bash
tracert google.com
```

Output Example:

```text
PC
 ↓
Router
 ↓
ISP Router
 ↓
Internet Router
 ↓
Google
```

This helps identify where connectivity problems occur.

---

# Routing

## What is Routing?

Routing is the process of finding the best path between networks.

Routers use routing tables to determine where packets should go.

---

## Routing Example

```text
Your PC
   ↓
Home Router
   ↓
ISP
   ↓
Internet
   ↓
Destination Server
```

Each router makes a forwarding decision.

---

# Default Gateway

The Default Gateway is the local router your device uses when communicating outside its own network.

Example:

```text
PC:
192.168.1.100

Gateway:
192.168.1.1
```

Diagram:

```text
Your PC
     ↓
Default Gateway
     ↓
Internet
```

Without a gateway, devices cannot reach external networks.

---

# NAT (Network Address Translation)

## What is NAT?

NAT translates private IP addresses into a public IP address.

This allows many devices to share a single Internet connection.

---

## Example

Inside Home Network:

```text
Phone:
192.168.1.10

Laptop:
192.168.1.11

TV:
192.168.1.12
```

Router Public IP:

```text
154.120.50.25
```

Internet sees:

```text
154.120.50.25
```

instead of individual private addresses.

---

## NAT Diagram

```text
Phone
   \
Laptop ----> Router ----> Internet
   /
TV

Private IPs
192.168.1.x

↓

Public IP
154.120.50.25
```

---

## Benefits of NAT

### Conserves IPv4 Addresses

Without NAT, every device would require a unique public IP.

### Improves Security

External devices cannot directly see your internal network.

```text
Internet
    ↓
Public IP
    ↓
Router (NAT)
    ↓
Private Devices
```

---

# How Everything Works Together

```text
1. DHCP gives you an IP address

2. ARP finds MAC addresses

3. ICMP tests connectivity

4. Routing finds the path

5. NAT translates private IPs
   to public IPs

6. Data reaches the Internet
```

---

# Key Takeaways

- DHCP automatically assigns IP addresses.
- DHCP uses the DORA process.
- ARP converts IP addresses into MAC addresses.
- ICMP is used for troubleshooting.
- Ping uses ICMP to test connectivity.
- Traceroute maps the network path.
- Routing determines the best path to a destination.
- The Default Gateway connects local networks to external networks.
- NAT translates private IP addresses into public IP addresses.
- NAT conserves IPv4 addresses and improves security.

---

## Common Commands

```bash
ping google.com
```

```bash
tracert google.com
```

```bash
ipconfig
```

```bash
ipconfig /all
```

```bash
arp -a
```