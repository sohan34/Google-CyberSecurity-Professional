# Google Cybersecurity Professional Certificate
# Course 3 – Module 3
# Network Attacks and Traffic Analysis

---

# Module Overview

In this module you learn:

- Common network attacks
- Network interception attacks
- Packet sniffing
- IP spoofing
- Denial of Service (DoS)
- Distributed Denial of Service (DDoS)
- Botnets
- Backdoor attacks
- Network protocol analyzers
- tcpdump
- Network attack mitigation
- Real-world DDoS attack case study
- Important cybersecurity terminology

---

# Why Networks Are Attacked

Every network has vulnerabilities.

Attackers continuously search for weaknesses that allow them to:

- Steal confidential data
- Interrupt business operations
- Install malware
- Gain long-term access
- Demand ransom
- Damage reputation
- Cause political or social disruption

## Common motivations

### Financial
- Steal money
- Sell stolen information
- Deploy ransomware

### Political
- Cyber warfare
- Government attacks
- Activism (Hacktivism)

### Personal
- Revenge
- Disgruntled employees
- Competitors

---

# Types of Network Attacks

Major attacks covered:

- Network interception attacks
- Packet sniffing
- IP spoofing
- On-path attacks
- Replay attacks
- Smurf attacks
- SYN Flood
- ICMP Flood
- Ping of Death
- DoS
- DDoS
- Backdoor attacks

---

# Network Interception Attacks

## Definition

A network interception attack occurs when an attacker captures or alters network traffic while it travels between systems.

Instead of attacking the destination directly, the attacker attacks the communication itself.

---

## Goals

Attackers attempt to:

- Read confidential information
- Modify data
- Redirect users
- Inject malware
- Steal credentials

---

## Examples

- Packet sniffing
- Replay attacks
- On-path attacks
- DNS spoofing

---

# Packet Sniffing

## Definition

Packet sniffing is the practice of capturing and inspecting data packets moving across a network.

Think of it like reading everyone's mail before it reaches them.

---

## Legitimate Uses

Security professionals use packet sniffing to:

- Troubleshoot networks
- Detect attacks
- Analyze traffic
- Monitor bandwidth
- Investigate incidents

---

## Malicious Uses

Attackers use packet sniffing to steal:

- Passwords
- Session cookies
- Credit card numbers
- Emails
- Authentication tokens

---

# Types of Packet Sniffing

## Passive Packet Sniffing

### Definition

The attacker simply listens to traffic.

Characteristics:

- No packet modification
- Hard to detect
- Common on hubs

---

## Active Packet Sniffing

### Definition

The attacker manipulates network traffic.

Characteristics:

- Modifies packets
- More dangerous
- Common on switched networks

---

# Network Interface Card (NIC)

A NIC connects a computer to a network.

Normally:

The NIC only accepts packets addressed to itself.

---

## Promiscuous Mode

In promiscuous mode:

The NIC accepts every packet on the network.

This allows packet sniffing software like Wireshark to capture everything.

---

# IP Spoofing

## Definition

IP spoofing occurs when an attacker changes the source IP address of a packet to impersonate another device.

---

## Purpose

Attackers spoof IP addresses to:

- Bypass security
- Hide identity
- Launch DoS attacks
- Perform interception attacks

---

# Common IP Spoofing Attacks

---

# 1. On-Path Attack

Also called:

- Man-in-the-Middle (MITM)
- Meddler-in-the-Middle

---

## Definition

The attacker secretly places themselves between two trusted systems.

```
Client
   ↓
Attacker
   ↓
Server
```

Everything passes through the attacker.

---

## What Can Be Stolen?

- Passwords
- Banking information
- Session cookies
- Emails
- Personal data

---

## DNS Spoofing

The attacker intercepts a DNS request.

Instead of returning the legitimate IP address,

they return:

```
google.com

↓

Attacker Server
```

The victim unknowingly visits a fake website.

---

## Prevention

- HTTPS
- TLS encryption
- Certificate validation
- VPNs

---

# 2. Replay Attack

## Definition

The attacker captures a valid packet and sends it again later.

Example:

A login request is captured.

Hours later,

the attacker replays it.

The server thinks it is legitimate.

---

## Prevention

- Nonces
- Session tokens
- Timestamp validation
- Encryption

---

# 3. Smurf Attack

## Definition

A Smurf attack combines:

- IP spoofing
- ICMP
- Broadcast traffic

---

## Process

Step 1

Spoof victim's IP.

↓

Step 2

Send ICMP request to broadcast address.

↓

Step 3

Every computer replies.

↓

Step 4

Victim receives thousands of replies.

↓

Server crashes.

---

## Prevention

- Disable IP broadcasts
- NGFW
- ICMP filtering

---

# Denial of Service (DoS)

## Definition

A DoS attack floods a server until it cannot respond to legitimate users.

Goal:

Prevent normal service.

---

## Effects

- Website unavailable
- Server overload
- Lost revenue
- Customer dissatisfaction

---

# Distributed Denial of Service (DDoS)

## Definition

A DDoS attack uses multiple systems simultaneously to attack one target.

Instead of one attacker:

```
100,000 computers

↓

One server
```

---

## Why DDoS Is Worse

- Massive traffic
- Difficult to block
- Global attack sources
- Large botnets

---

# Botnet

## Definition

A botnet is a group of malware-infected computers controlled by one attacker (bot-herder).

---

## Bot-Herder

Controls every infected device remotely.

Can launch:

- Spam campaigns
- DDoS attacks
- Credential theft
- Malware delivery

---

# Real Example: 2016 Dyn DNS DDoS Attack

## Background

A DNS provider hosted DNS services for many popular websites.

Examples included:

- Twitter
- Netflix
- Reddit
- GitHub
- Spotify

---

## What Happened?

A massive botnet sent:

Millions of DNS requests.

↓

DNS servers became overwhelmed.

↓

DNS service failed.

↓

Users couldn't reach websites.

---

## Timeline

- October 21, 2016
- Around 7:00 AM
- Tens of millions of DNS requests
- Approximately two hours of downtime

---

## Lessons Learned

Organizations should:

- Use redundancy
- Load balancing
- Scalable infrastructure
- DDoS mitigation services

---

# Common DoS Attacks

---

# ICMP Flood

Uses:

ICMP Echo Requests (Ping)

The attacker sends thousands of ping requests.

Server spends all resources replying.

---

# Ping of Death

The attacker sends:

Oversized ICMP packets

Greater than:

64 KB

The oversized packet crashes vulnerable systems.

---

# SYN Flood

Targets:

TCP Three-Way Handshake

---

## Normal TCP

```
SYN

↓

SYN-ACK

↓

ACK
```

Connection established.

---

## SYN Flood

Attacker sends:

Thousands of SYN packets

Never completes the handshake.

Server waits forever.

Connection table fills.

New users cannot connect.

---

# Backdoor Attack

## Definition

A backdoor is a hidden method of bypassing normal authentication.

---

## Why Backdoors Exist

Sometimes developers create them for:

- Troubleshooting
- Maintenance
- Testing

Attackers also install them after compromising systems.

---

## Risks

Attackers gain:

- Persistent access
- Malware installation
- Data theft
- Remote control

---

# Consequences of Network Attacks

## Financial

- Revenue loss
- Ransom payments
- Legal settlements
- Recovery costs

---

## Reputation

Customers lose trust.

Brand image suffers.

Business decreases.

---

## Public Safety

Critical infrastructure attacks can affect:

- Hospitals
- Power grids
- Water systems
- Transportation
- Military

---

# Network Protocol Analyzer

## Definition

A tool that captures and analyzes network traffic.

Also called:

- Packet Sniffer
- Packet Analyzer

---

## Popular Tools

- Wireshark
- tcpdump
- SolarWinds NetFlow Traffic Analyzer
- ManageEngine OpManager
- Azure Network Watcher

---

# tcpdump

## Definition

A command-line packet analyzer.

Features:

- Lightweight
- Open source
- Linux
- macOS
- Uses libpcap

---

## Information Displayed

Each packet includes:

- Timestamp
- Source IP
- Source Port
- Destination IP
- Destination Port
- Protocol

Example:

```
10:15:31.123456

192.168.1.5.443

>

192.168.1.10.50432
```

---

# Uses of tcpdump

Security analysts use tcpdump to:

- Monitor traffic
- Detect attacks
- Investigate incidents
- Troubleshoot networks
- Establish traffic baselines

---

# Attackers Also Use Packet Analyzers

They capture:

- Passwords
- Cookies
- Tokens
- Email
- Authentication data

Always encrypt sensitive traffic.

---

# Mitigation Strategies

## Against Packet Sniffing

- HTTPS
- TLS
- VPN
- SSH

---

## Against IP Spoofing

- Firewall filtering
- Packet validation
- Ingress filtering

---

## Against On-Path Attacks

- TLS
- HTTPS
- VPN
- Certificate validation

---

## Against Smurf Attacks

- Disable broadcasts
- Block ICMP
- NGFW anomaly detection

---

## Against DoS/DDoS

- Load balancing
- CDN
- DDoS mitigation
- Rate limiting
- Traffic filtering
- Auto scaling

---

## Against Backdoors

- Patch systems
- Remove unused accounts
- Monitor logs
- Endpoint detection
- Principle of Least Privilege

---

# Defense in Depth

No single defense stops every attack.

Layer multiple controls:

```
Firewall

↓

IDS/IPS

↓

VPN

↓

TLS

↓

Authentication

↓

Monitoring

↓

Logging

↓

SIEM
```

---

# Important Exam Definitions

## Packet Sniffing

Capturing and inspecting network packets.

---

## Passive Packet Sniffing

Listening without modifying traffic.

---

## Active Packet Sniffing

Capturing while manipulating traffic.

---

## IP Spoofing

Changing source IP to impersonate another system.

---

## On-Path Attack

Intercepting communication between trusted systems.

---

## Replay Attack

Capturing and retransmitting valid packets later.

---

## Smurf Attack

Broadcast ICMP attack using a spoofed victim IP.

---

## DoS Attack

One attacker overwhelms one target.

---

## DDoS Attack

Many systems overwhelm one target.

---

## Botnet

A collection of malware-infected computers controlled remotely.

---

## SYN Flood

Floods a server with TCP SYN packets without completing the handshake.

---

## ICMP Flood

Floods a server with ping requests.

---

## Ping of Death

Oversized ICMP packet attack (>64 KB).

---

## Backdoor

Hidden access mechanism bypassing authentication.

---

## tcpdump

Command-line network protocol analyzer.

---

# Quick Revision Table

| Concept | Key Point |
|----------|-----------|
| Packet Sniffing | Capture network packets |
| Passive Sniffing | Observe traffic only |
| Active Sniffing | Manipulate traffic |
| IP Spoofing | Fake source IP |
| On-Path Attack | Intercept trusted communication |
| Replay Attack | Resend captured packets |
| Smurf Attack | Broadcast ICMP flood |
| DoS | Single-source flooding |
| DDoS | Multi-source flooding |
| Botnet | Malware-controlled devices |
| SYN Flood | Exploits TCP handshake |
| ICMP Flood | Ping-based DoS |
| Ping of Death | Oversized ICMP packets |
| Backdoor | Hidden access |
| tcpdump | Command-line packet analyzer |

---

# Module Summary

After completing Module 3, you should understand:

✅ Why attackers target networks

✅ Packet sniffing

✅ Active vs Passive sniffing

✅ IP spoofing

✅ On-path attacks

✅ Replay attacks

✅ Smurf attacks

✅ DoS attacks

✅ DDoS attacks

✅ Botnets

✅ Backdoor attacks

✅ Real-world Dyn DNS attack

✅ tcpdump fundamentals

✅ Network attack mitigation strategies

✅ Important cybersecurity terminology
