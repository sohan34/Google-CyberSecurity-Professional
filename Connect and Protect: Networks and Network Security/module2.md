# 🌐 Network Protocols, Security Protocols & Network Protection

---

# What is a Network Protocol?

A **network protocol** is a standardized set of rules that determines how devices communicate across a network.

Protocols define:

- How data is formatted
- How data is transmitted
- How data is received
- Error handling
- Timing of communication

Think of protocols as a **common language** that allows computers, routers, phones, servers, and other devices to understand each other.

Without protocols, devices from different manufacturers would never be able to communicate.

---

# Categories of Network Protocols

Network protocols are generally divided into three categories.

```
                Network Protocols
                       │
      ┌────────────────┼────────────────┐
      │                │                │
Communication     Management       Security
Protocols         Protocols        Protocols
```

---

## 1. Communication Protocols

These protocols are responsible for moving data between devices.

Examples:

- TCP
- UDP
- HTTP
- HTTPS
- DNS
- FTP
- SMTP

---

## 2. Management Protocols

These protocols monitor and manage network devices.

Examples:

- SNMP
- ICMP
- DHCP

---

## 3. Security Protocols

These protect data during transmission.

Examples:

- HTTPS
- SSH
- SFTP
- IPSec
- TLS

---

# Transmission Control Protocol (TCP)

TCP is a **connection-oriented transport protocol**.

Before sending data, TCP first establishes a reliable connection.

## Characteristics

- Reliable
- Ordered delivery
- Error checking
- Packet retransmission
- Flow control

Used for:

- Websites
- Email
- Banking
- File transfers

---

## TCP Three-Way Handshake

TCP establishes a connection using three steps.

```
Client                  Server

SYN   ------------------>

      <------------------ SYN + ACK

ACK   ------------------>
```

### Step 1

Client sends

```
SYN
```

asking to establish a connection.

---

### Step 2

Server responds

```
SYN + ACK
```

meaning

"I received your request."

---

### Step 3

Client replies

```
ACK
```

Connection established.

Only after this process does actual data transfer begin.

---

## Advantages

✔ Reliable

✔ Error detection

✔ Packet recovery

✔ Ordered delivery

---

## Disadvantages

- Slower
- More overhead

---

# User Datagram Protocol (UDP)

UDP is a **connectionless protocol**.

No handshake.

Packets are simply sent.

```
Client -----------------> Server
```

---

## Characteristics

- Very fast
- No retransmission
- No ordering
- No reliability guarantee

---

## Used For

- Live streaming
- Video conferencing
- Gaming
- DNS queries
- VoIP

---

## TCP vs UDP

| Feature | TCP | UDP |
|----------|-----|-----|
| Reliable | ✅ | ❌ |
| Fast | ❌ | ✅ |
| Connection Required | ✅ | ❌ |
| Packet Ordering | ✅ | ❌ |
| Error Recovery | ✅ | ❌ |

---

# Hypertext Transfer Protocol (HTTP)

HTTP is the protocol web browsers use to communicate with web servers.

```
Browser
     │
 HTTP Request
     │
Website Server
```

Uses:

```
Port 80
```

HTTP sends data in **plain text**.

This means anyone intercepting the traffic can read it.

Because of this, HTTP is considered insecure.

---

# HTTPS

HTTPS is the secure version of HTTP.

It encrypts all communication using:

- SSL
- TLS

Uses:

```
Port 443
```

Benefits

- Encryption
- Authentication
- Data integrity

Always prefer:

```
https://
```

instead of

```
http://
```

---

# Domain Name System (DNS)

Humans remember names.

Computers remember IP addresses.

DNS converts names into IP addresses.

Example

```
google.com

↓

142.250.x.x
```

---

## DNS Process

```
Browser

   │

DNS Request

   │

DNS Server

   │

Returns IP

   │

Browser connects to website
```

---

## DNS Port

Normally uses

```
UDP 53
```

If response becomes too large,

DNS switches to

```
TCP 53
```

---

# Simple Network Management Protocol (SNMP)

SNMP monitors and manages network devices.

Administrators can:

- Check bandwidth
- Monitor switches
- Monitor routers
- Reset passwords
- Change configurations

---

Example

```
Administrator

      │

 SNMP Request

      │

Router

      │

Status Report
```

---

# Internet Control Message Protocol (ICMP)

ICMP reports network errors.

Examples

- Host unreachable
- Network unreachable
- Time exceeded
- Redirect messages

---

Most common use:

```
ping
```

Example

```
ping google.com
```

ICMP measures:

- Connectivity
- Delay
- Packet loss

---

# Secure File Transfer Protocol (SFTP)

SFTP securely transfers files.

Uses

```
SSH

TCP Port 22
```

Unlike FTP,

SFTP encrypts all data.

Commonly used by:

- Cloud storage
- Linux servers
- Enterprises

---

# Common Network Ports

| Protocol | Port |
|----------|------|
| HTTP | 80 |
| HTTPS | 443 |
| DNS | 53 |
| SSH | 22 |
| Telnet | 23 |
| SMTP | 25 / 587 |
| POP3 | 110 / 995 |
| IMAP | 143 / 993 |
| DHCP Server | 67 |
| DHCP Client | 68 |
| FTP | 21 |
| SFTP | 22 |

---

# Network Address Translation (NAT)

Devices inside your home use **private IP addresses**.

The internet only sees your **public IP**.

NAT translates between them.

```
Laptop
192.168.1.5

↓

Router (NAT)

↓

Public IP

↓

Internet
```

---

## Why NAT?

Advantages

- Conserves IPv4 addresses
- Hides internal devices
- Adds basic security

---

## Private IP Ranges

```
10.0.0.0 – 10.255.255.255

172.16.0.0 – 172.31.255.255

192.168.0.0 – 192.168.255.255
```

These addresses are **not routable** on the internet.

---

# Dynamic Host Configuration Protocol (DHCP)

DHCP automatically assigns:

- IP address
- Subnet mask
- Gateway
- DNS server

Without DHCP,

every device would require manual configuration.

---

## DHCP Uses

Server:

```
UDP Port 67
```

Client:

```
UDP Port 68
```

---

## DHCP Process

```
Device joins network

↓

DHCP Discover

↓

DHCP Offer

↓

DHCP Request

↓

DHCP Acknowledgement
```

---

# Address Resolution Protocol (ARP)

Devices communicate locally using MAC addresses.

But they usually know only IP addresses.

ARP solves this.

```
IP Address

↓

ARP

↓

MAC Address
```

---

Example

```
192.168.1.20

↓

00:1A:2B:3C:4D:5E
```

ARP maintains an **ARP Cache**.

---

# Telnet

Telnet remotely controls another computer.

Uses

```
TCP Port 23
```

Problem:

Everything is sent as plain text.

Including passwords.

Today,

SSH replaces Telnet.

---

# Secure Shell (SSH)

SSH provides secure remote access.

Uses

```
TCP Port 22
```

Features

- Encryption
- Authentication
- Secure command execution
- Secure file transfer

Widely used for Linux server administration.

---

# Email Protocols

Email uses three major protocols.

---

## SMTP

Used for

Sending email.

Ports

```
25
587 (TLS)
```

---

## POP3

Downloads emails.

Usually removes them from the server.

Ports

```
110
995 (SSL/TLS)
```

---

## IMAP

Keeps emails on the server.

Allows synchronization across multiple devices.

Ports

```
143
993 (SSL/TLS)
```

---

# Wireless Networking (Wi-Fi)

Wi-Fi follows IEEE standards:

```
IEEE 802.11
```

Wireless communication uses radio waves instead of cables.

---

# Evolution of Wi-Fi Security

```
WEP

↓

WPA

↓

WPA2

↓

WPA3
```

Each version improved security.

---

## WEP

Released:

1999

Problems:

- Weak encryption
- Easily cracked
- Obsolete today

Never use WEP.

---

## WPA

Released:

2003

Improvements

- TKIP encryption
- Better authentication

Still vulnerable to:

KRACK attack

---

## WPA2

Released:

2004

Uses

AES Encryption

CCMP

Most widely used today.

Modes

### Personal

Home networks

Shared password

---

### Enterprise

Businesses

Uses centralized authentication.

Much more secure.

---

## WPA3

Newest Wi-Fi standard.

Advantages

- Stronger encryption
- Better password protection
- Resistant to KRACK
- SAE authentication

Best wireless security available today.

---

# Subnetting

Subnetting divides one large network into smaller networks.

```
Large Network

↓

Subnet A

Subnet B

Subnet C

Subnet D
```

Benefits

- Better organization
- Improved performance
- Better security
- Easier management

---

# CIDR Notation

CIDR means

Classless Inter-Domain Routing.

Example

```
192.168.1.0/24
```

The

```
/24
```

indicates the network prefix.

CIDR allows flexible subnet creation.

---

# Firewalls

A firewall monitors network traffic.

```
Internet

↓

Firewall

↓

Private Network
```

Firewalls allow or block packets based on rules.

---

## Types of Firewalls

### Stateless Firewall

Checks every packet independently.

No memory.

---

### Stateful Firewall

Tracks active connections.

Smarter.

More secure.

---

### Next Generation Firewall (NGFW)

Advanced firewall capable of

- Deep Packet Inspection
- Application Awareness
- Intrusion Prevention
- Malware Detection
- URL Filtering
- DNS Filtering

---

# Proxy Servers

A proxy sits between users and the internet.

```
User

↓

Proxy

↓

Internet
```

---

## Forward Proxy

Protects users accessing the internet.

Used for

- Content filtering
- Blocking websites
- Logging activity

---

## Reverse Proxy

Protects servers.

Clients never communicate directly with servers.

Common uses

- Load balancing
- DDoS protection
- SSL termination

---

# Virtual Private Network (VPN)

VPN encrypts internet traffic.

```
Computer

↓

Encrypted Tunnel

↓

VPN Server

↓

Internet
```

Benefits

- Privacy
- Encryption
- Hide IP address
- Secure public Wi-Fi

---

## Types of VPN

### Remote Access VPN

One user connects securely.

```
Laptop

↓

VPN Server
```

---

### Site-to-Site VPN

Connects entire offices.

```
Office A

↓

VPN Tunnel

↓

Office B
```

---

# VPN Protocols

## IPSec

Older

Very secure

Common in enterprises

Supports site-to-site VPNs

---

## WireGuard

Modern VPN protocol.

Advantages

- Faster
- Simpler
- Open source
- Less code
- Excellent performance

Supports

- Remote Access VPN
- Site-to-Site VPN

---

# Summary

This section covered:

- Network Protocols
- TCP vs UDP
- HTTP & HTTPS
- DNS
- DHCP
- NAT
- ARP
- SNMP
- ICMP
- SSH
- Telnet
- Email Protocols (SMTP, POP3, IMAP)
- Wireless Security (WEP → WPA → WPA2 → WPA3)
- Subnetting & CIDR
- Firewalls
- Proxy Servers
- VPNs
- WireGuard
- IPSec

These protocols and technologies form the backbone of modern networking and cybersecurity. Understanding them is essential for Security+, Google Cybersecurity, CompTIA Network+, and real-world Security Operations Center (SOC) roles.
