# Google Cybersecurity Professional Certificate

# Course 3

# Module 1: Networks, Cloud Computing, TCP/IP, OSI Model & IP Packets

---

# Table of Contents

1. Introduction
2. Network Architecture
3. Network Devices
4. Client-Server Model
5. Network Diagrams
6. Types of Networks
7. Cloud Computing
8. Cloud Service Providers (CSPs)
9. Cloud Service Models
10. Hybrid & Multi-Cloud
11. Software Defined Networking (SDN)
12. Benefits of Cloud Computing
13. Key Takeaways

---

# Introduction

Every organization depends on computer networks to communicate, share information, and deliver services. Whether users browse the internet, send emails, access cloud storage, or log into a company's internal systems, they rely on a well-designed network infrastructure.

For cybersecurity professionals, understanding **how networks function** is one of the most important foundational skills. Before protecting a network, an analyst must understand:

- How devices communicate
- How data travels
- Which devices forward traffic
- Where attacks can occur
- How security controls defend the network

Network architecture provides the blueprint of how all devices communicate with one another.

---

# What is a Network?

A **network** is a collection of interconnected devices that exchange information and share resources.

Examples of connected devices include:

- Desktop computers
- Laptops
- Smartphones
- Tablets
- Servers
- Printers
- IoT devices
- Security cameras

Devices communicate by sending **data packets** across the network.

Each packet contains information such as:

- Source Address
- Destination Address
- Protocol
- Data Payload

---

# What is Network Architecture?

Network architecture (also called **network design**) is the structure and layout of devices that make up a network.

It defines:

- How devices connect
- How data flows
- Which devices route traffic
- Which security controls protect communication

Network architecture helps organizations:

- Improve performance
- Increase availability
- Reduce latency
- Improve scalability
- Enhance cybersecurity

---

# Example Home Network

```
                 Internet
                     │
                  ISP Modem
                     │
                 Firewall
                     │
                  Router
                     │
          ┌──────────┴──────────┐
          │                     │
      Wireless AP           Network Switch
          │                     │
 ┌────────┼────────┐      ┌─────┴────────────┐
 │        │        │      │      │           │
Laptop  Phone   Tablet  Desktop Server  Printer
```

This simple architecture demonstrates how data flows from the internet to internal devices.

---

# How Data Travels

Every communication follows this general process:

```
User
   │
Creates Request
   │
Router
   │
Internet
   │
Destination Server
   │
Response
   │
Router
   │
User
```

Instead of sending an entire file at once, computers divide information into **small packets**.

Each packet travels independently before being reassembled at its destination.

---

# Data Packets

A **data packet** is the smallest unit of data sent over a network.

Each packet generally contains two sections:

```
+-------------------------+
| Header                  |
+-------------------------+
| Actual Data (Payload)   |
+-------------------------+
```

The header stores information such as:

- Source IP
- Destination IP
- Protocol
- Packet Length
- Sequence Information

The payload contains the actual information:

- Website data
- Email content
- Images
- Documents
- Streaming data

---

# Network Devices

Network devices are specialized hardware responsible for forwarding, securing, and managing communication across a network.

Some devices connect users.

Others control traffic.

Others enforce security.

---

# 1. Desktop Computers & End Devices

End-user devices include:

- Desktop computers
- Laptops
- Smartphones
- Tablets
- Smart TVs
- IoT Devices

Every device connected to a network has two important addresses.

## MAC Address

A **MAC (Media Access Control) Address** is the permanent physical address assigned to a network interface card.

Example:

```
00:1A:2B:3C:4D:5E
```

Characteristics:

- Unique worldwide
- Layer 2 address
- Used inside local networks

---

## IP Address

An **IP Address** identifies a device on a network.

Example:

```
192.168.1.15
```

Characteristics:

- Logical address
- Can change
- Used for routing across networks

---

# 2. Firewalls

A firewall is one of the most important security devices.

It monitors traffic entering and leaving a network.

Its primary goal is to prevent unauthorized access.

```
Internet
     │
 Firewall
     │
Internal Network
```

Firewalls inspect traffic using predefined security rules.

Examples:

Allow:

- HTTPS (443)
- DNS (53)

Block:

- Suspicious IP addresses
- Malware traffic
- Unauthorized ports

Firewalls provide:

- Traffic filtering
- Access control
- Intrusion prevention
- Network segmentation

They are considered the **first line of defense** for most organizations.

---

# 3. Servers

A server is a computer that provides services to other devices.

Devices requesting services are called **clients**.

This architecture is called the **Client-Server Model**.

Common server types include:

| Server | Purpose |
|----------|----------|
| Web Server | Hosts websites |
| File Server | Stores files |
| Mail Server | Sends and receives email |
| DNS Server | Resolves domain names |
| Database Server | Stores structured data |
| Authentication Server | Verifies users |

---

# Client-Server Communication

```
Client
   │
Request
   │
▼
Server
   │
Processes Request
   │
▼
Response
   │
Client
```

Example:

```
Browser
    │
HTTPS Request
    │
Web Server
    │
Returns HTML
    │
Browser Displays Website
```

---

# 4. Switches

A switch connects devices within the same Local Area Network (LAN).

Unlike hubs, switches send packets **only to the intended device**.

They maintain a **MAC Address Table**.

Example:

```
PC1
    │
PC2 ─ Switch ─ Printer
    │
Server
```

Advantages:

- Faster communication
- Better bandwidth utilization
- Improved security
- Reduced collisions

Switches operate primarily at:

**OSI Layer 2 (Data Link Layer)**

---

# 5. Hubs

A hub is an older networking device.

Unlike switches, hubs do not inspect packet destinations.

Instead, hubs broadcast incoming traffic to **every connected device**.

Example:

```
PC1
     │
PC2--Hub--PC3
     │
Printer
```

Every device receives every packet.

Disadvantages:

- Slow
- Inefficient
- Vulnerable to packet sniffing
- Poor security

Because of these limitations, hubs are rarely used today.

---
---

# 6. Routers

A **router** is a networking device that connects **different networks** together and forwards data packets based on **IP addresses**.

Unlike a switch, which works within a local network using MAC addresses, a router determines the **best path** for data to travel between networks.

Example:

```
           Internet
               │
           ISP Network
               │
            Router
        ┌──────┴──────┐
        │             │
    Home Network   Office Network
```

### Responsibilities of a Router

- Connects multiple networks
- Routes packets to their destination
- Reads destination IP addresses
- Determines the best path
- Can perform Network Address Translation (NAT)
- Often includes firewall functionality

### OSI Layer

**Layer 3 – Network Layer**

### TCP/IP Layer

**Internet Layer**

---

# How Routers Work

Suppose your computer wants to access:

```
https://www.google.com
```

The process is:

```
Computer
     │
Creates Packet
     │
Router
     │
Internet
     │
Google Router
     │
Google Server
```

Every router along the path examines the **destination IP address** and forwards the packet closer to its destination.

---

# 7. Modems

A **modem** connects a home or office network to an **Internet Service Provider (ISP).**

The word **modem** comes from:

> MOdulator + DEModulator

It converts signals between:

- ISP transmission signals
- Digital computer signals

### Typical Connection

```
Internet
     │
ISP
     │
Modem
     │
Router
     │
Local Network
```

Without a modem, your router cannot communicate with your ISP.

---

# 8. Wireless Access Point (WAP)

A **Wireless Access Point (WAP)** allows wireless devices to connect to a wired network using **Wi-Fi**.

Examples of wireless devices:

- Smartphones
- Laptops
- Tablets
- Smart TVs
- IoT devices

Example:

```
Router
     │
Wireless Access Point
     │
~~~~~~~~~~~~~~~~~~~~~~~~
 Laptop   Phone   Tablet
```

### Benefits

- Wireless connectivity
- Increased mobility
- Easy expansion
- Supports multiple wireless clients

---

# Wi-Fi

Wi-Fi is a collection of standards that allows devices to communicate using **radio waves** instead of cables.

Advantages:

- No physical cables
- Mobility
- Easy deployment
- High-speed communication

---

# Client-Server Architecture

Nearly every modern application follows the **Client-Server Model**.

The client requests services.

The server processes those requests.

```
Client
     │
Request
     ▼
Server
     │
Process Request
     ▼
Response
     │
Client
```

---

# Examples of Client-Server Applications

| Client | Server |
|----------|---------|
| Browser | Web Server |
| Outlook | Mail Server |
| Phone | DNS Server |
| Computer | File Server |
| Banking App | Banking Server |

---

# Network Diagrams

A **network diagram** is a visual representation of a network.

It illustrates:

- Devices
- Connections
- Traffic flow
- Security controls
- Network zones

Example:

```
Internet
     │
Firewall
     │
Router
     │
Switch
 ┌───┼────┐
 │   │    │
PC Server Printer
```

---

# Why Network Diagrams Matter

Security analysts use network diagrams to:

- Identify critical assets
- Locate vulnerable systems
- Understand traffic flow
- Plan security controls
- Investigate incidents
- Document infrastructure

Without network diagrams, troubleshooting becomes significantly more difficult.

---

# Types of Networks

Networks are commonly categorized by the geographical area they cover.

---

# Local Area Network (LAN)

A **LAN** connects devices within a small geographical area.

Examples:

- Home
- School
- Office
- Hospital

```
Office
 │
Switch
 ├──PC1
 ├──PC2
 ├──Printer
 └──Server
```

### Characteristics

- High speed
- Low latency
- Privately managed
- Limited geographical coverage

---

# Wide Area Network (WAN)

A **WAN** connects multiple LANs over large geographical distances.

Example:

```
New York Office
        │
    Internet
        │
London Office
```

### Characteristics

- Large geographical coverage
- Connects multiple cities or countries
- Uses routers extensively
- Often leased from telecommunications providers

Example:

The Internet is the world's largest WAN.

---

# Comparison: LAN vs WAN

| Feature | LAN | WAN |
|----------|-----|-----|
| Coverage | Small | Large |
| Speed | Faster | Slower |
| Ownership | Private | Often ISP-managed |
| Cost | Lower | Higher |
| Examples | Home, Office | Internet |

---

# Cloud Computing

Traditional organizations owned and managed all hardware inside their own buildings.

This approach is called:

> **On-Premise Infrastructure**

Example:

```
Company Office

Servers
Storage
Networking
Applications
```

Today, organizations increasingly rely on **Cloud Computing**.

---

# What is Cloud Computing?

Cloud computing is the delivery of computing resources over the internet.

Instead of buying hardware, organizations rent resources from cloud providers.

Resources include:

- Storage
- Servers
- Databases
- Networking
- Security
- Applications

---

# Traditional Infrastructure vs Cloud

## Traditional

```
Company
   │
Own Servers
Own Storage
Own Networking
Own Maintenance
```

## Cloud

```
Company
     │
Internet
     │
Cloud Provider
```

---

# Cloud Service Providers (CSPs)

A **Cloud Service Provider (CSP)** owns massive data centers that provide cloud services to customers.

Popular CSPs include:

- Amazon Web Services (AWS)
- Microsoft Azure
- Google Cloud Platform (GCP)

These providers maintain:

- Physical servers
- Storage systems
- Virtual machines
- Networking infrastructure
- Security services

Organizations simply consume the resources they need.

---

# Cloud Data Centers

Cloud providers operate enormous facilities containing millions of servers.

```
Cloud Data Center

Server Server Server
Server Server Server
Server Server Server
Storage Arrays
Networking Equipment
Power Backup
Cooling Systems
```

These data centers provide:

- High availability
- Fault tolerance
- Disaster recovery
- Global connectivity

---

# Cloud Service Models

Cloud services are divided into three major categories:

- SaaS
- PaaS
- IaaS

---

# Software as a Service (SaaS)

SaaS provides software applications over the internet.

Users only use the software.

The provider manages everything else.

Examples:

- Gmail
- Google Docs
- Microsoft 365
- Dropbox
- Slack

### Advantages

- No installation
- Automatic updates
- Accessible anywhere
- Subscription-based

---

# Platform as a Service (PaaS)

PaaS provides a complete environment for software development.

Developers focus on writing code.

The provider manages:

- Servers
- Operating Systems
- Networking
- Runtime Environment

Examples:

- Google App Engine
- Azure App Service
- Heroku

---

# Infrastructure as a Service (IaaS)

IaaS provides virtualized computing infrastructure.

Customers manage:

- Operating Systems
- Applications
- Security

Provider manages:

- Physical hardware
- Networking
- Storage

Examples:

- AWS EC2
- Azure Virtual Machines
- Google Compute Engine

---

# Comparing SaaS, PaaS & IaaS

| Feature | SaaS | PaaS | IaaS |
|----------|------|------|------|
| User Controls | Software Only | Applications | Entire OS & Apps |
| Provider Manages | Everything | Infrastructure | Physical Hardware |
| Flexibility | Low | Medium | High |
| Examples | Gmail | App Engine | AWS EC2 |

---
---

# Hybrid Cloud Environment

A **Hybrid Cloud** combines **on-premises infrastructure** with **cloud services**.

Instead of moving everything to the cloud, organizations keep some resources in their own data centers while using cloud services for additional computing, storage, or applications.

## Architecture

```
                Company
                   │
      ┌────────────┴────────────┐
      │                         │
On-Premise Servers         Cloud Provider
(Local Data Center)             (AWS/Azure/GCP)
```

## Why Organizations Use Hybrid Cloud

- Maintain control over sensitive data
- Reduce infrastructure costs
- Scale resources when needed
- Improve disaster recovery
- Meet regulatory compliance requirements

### Advantages

- Greater flexibility
- Better business continuity
- Easy cloud migration
- Cost-effective scaling

---

# Multi-Cloud Environment

A **Multi-Cloud** environment uses services from **multiple Cloud Service Providers (CSPs)**.

Example:

```
             Organization
                  │
      ┌───────────┼───────────┐
      │           │           │
     AWS       Azure       Google Cloud
```

## Reasons to Use Multi-Cloud

- Avoid vendor lock-in
- Increase redundancy
- Improve availability
- Optimize costs
- Choose the best service from each provider

### Example

- AWS → Storage
- Azure → Identity Management
- Google Cloud → Machine Learning

---

# Software-Defined Networking (SDN)

Traditional networking relies heavily on **physical hardware** such as routers, switches, and firewalls.

**Software-Defined Networking (SDN)** replaces much of this hardware management with software.

Instead of configuring each device individually, administrators manage the entire network through a centralized software controller.

## Traditional Network

```
Switch
Router
Firewall
Configured Individually
```

## Software-Defined Network

```
SDN Controller
       │
 ┌─────┼─────┐
 │     │     │
Switch Router Firewall
```

---

## Benefits of SDN

- Centralized management
- Easy automation
- Faster deployment
- Better scalability
- Improved monitoring
- Dynamic traffic routing
- Simplified security policy management

---

# Benefits of Cloud Computing

Cloud computing has become the preferred solution for organizations because it provides several significant advantages.

## 1. Reliability

Cloud providers offer highly available infrastructure.

Features include:

- Multiple data centers
- Redundant hardware
- Automatic failover
- Backup systems

This ensures that services remain available even if one server fails.

---

## 2. Cost Savings

Traditional infrastructure requires organizations to purchase:

- Servers
- Storage
- Networking equipment
- Backup systems
- Cooling
- Physical space

Cloud computing eliminates many of these upfront costs.

Organizations pay only for the resources they consume.

This pricing model is commonly called:

> **Pay-as-you-go**

---

## 3. Scalability

One of cloud computing's greatest advantages is **elastic scalability**.

Organizations can quickly increase or decrease resources depending on demand.

Example:

```
Holiday Season
      │
Traffic Increases
      │
Cloud Automatically Adds Servers
```

When demand decreases, unused resources are removed.

This prevents unnecessary expenses.

---

## 4. Security

Major cloud providers offer built-in security services such as:

- Firewalls
- Identity Management
- Encryption
- Multi-Factor Authentication (MFA)
- Intrusion Detection Systems (IDS)
- Intrusion Prevention Systems (IPS)
- Web Application Firewalls (WAF)

These security services can often be enabled with minimal configuration.

---

# Key Takeaways: Cloud Computing

- Cloud computing replaces physical infrastructure with internet-based services.
- Cloud Service Providers (CSPs) manage large-scale data centers.
- SaaS, PaaS, and IaaS provide different levels of service.
- Hybrid cloud combines on-premises infrastructure with cloud resources.
- Multi-cloud uses multiple cloud providers.
- Software-Defined Networking (SDN) enables centralized and automated network management.
- Cloud computing improves scalability, reliability, security, and cost efficiency.

---

# TCP/IP Model

The **Transmission Control Protocol/Internet Protocol (TCP/IP) Model** is the standard framework used to describe how data travels across networks and the Internet.

It explains how devices communicate and how data is organized during transmission.

The TCP/IP model consists of **four layers**:

```
+---------------------------+
| 4. Application Layer      |
+---------------------------+
| 3. Transport Layer        |
+---------------------------+
| 2. Internet Layer         |
+---------------------------+
| 1. Network Access Layer   |
+---------------------------+
```

Each layer performs a specific role during communication.

---

# Why the TCP/IP Model Matters

Cybersecurity professionals use the TCP/IP model to:

- Understand how communication occurs
- Troubleshoot network problems
- Identify attack locations
- Analyze malicious traffic
- Investigate security incidents

---

# Data Encapsulation

When a user sends data across a network, each TCP/IP layer adds its own information.

This process is called **Encapsulation**.

```
Application Data
        │
Transport Header Added
        │
IP Header Added
        │
Frame Header Added
        │
Bits Sent Across Network
```

At the destination, the reverse process occurs.

This is called **Decapsulation**.

---

# Layer 1 — Network Access Layer

The Network Access Layer is responsible for the **physical transmission of data** across a network.

It combines the responsibilities of the **Physical Layer** and **Data Link Layer** from the OSI model.

### Responsibilities

- Physical communication
- Frame transmission
- MAC addressing
- Error detection
- Local network communication

### Devices

- Switches
- Hubs
- Network Interface Cards (NICs)
- Ethernet cables
- Fiber optic cables
- Wireless adapters

### Protocols

- Ethernet
- Wi-Fi (IEEE 802.11)
- ARP (Address Resolution Protocol)

---

# Address Resolution Protocol (ARP)

ARP maps:

```
IP Address
      ↓
MAC Address
```

Example:

```
IP:
192.168.1.25

↓

MAC:
00:1A:2B:3C:4D:5E
```

Without ARP, devices on the same local network would not know each other's physical addresses.

---

# Layer 2 — Internet Layer

The Internet Layer is responsible for **routing packets between networks**.

It determines the path that packets take from the source to the destination.

### Responsibilities

- Logical addressing
- Routing
- Packet forwarding
- Path selection
- Fragmentation

### Protocols

- Internet Protocol (IP)
- Internet Control Message Protocol (ICMP)

---

# Internet Protocol (IP)

IP is responsible for:

- Assigning logical addresses
- Routing packets
- Delivering packets between networks

IP does **not** guarantee delivery.

That responsibility belongs to TCP.

---

# Internet Control Message Protocol (ICMP)

ICMP provides:

- Error reporting
- Network diagnostics
- Connectivity testing

Common uses include:

- Ping
- Traceroute

Example:

```
ping google.com
```

ICMP determines whether a destination is reachable.

---
---

# Layer 3 — Transport Layer

The **Transport Layer** is responsible for **end-to-end communication** between devices.

It ensures that data is delivered to the correct application running on the destination device.

This layer is responsible for:

- Segmentation
- Flow control
- Error checking
- Reliability
- Port addressing
- Data reassembly

The two primary protocols at this layer are:

- **Transmission Control Protocol (TCP)**
- **User Datagram Protocol (UDP)**

---

# Transmission Control Protocol (TCP)

TCP is a **connection-oriented** protocol that guarantees reliable communication.

Before data is transmitted, TCP establishes a connection between the sender and receiver.

## Features of TCP

- Reliable communication
- Connection-oriented
- Error detection
- Error recovery
- Flow control
- Ordered packet delivery
- Packet retransmission

### TCP Three-Way Handshake

TCP establishes a connection using the **Three-Way Handshake**.

```
Client                    Server

SYN --------------------->

     <------------------- SYN + ACK

ACK --------------------->
```

After the handshake is complete, data transmission begins.

---

# Advantages of TCP

- Reliable delivery
- Guaranteed packet order
- Error correction
- Suitable for important data

---

# Common TCP Applications

| Application | Protocol |
|-------------|----------|
| Web Browsing | HTTP / HTTPS |
| Email | SMTP |
| File Transfer | FTP |
| Remote Login | SSH |
| Database Connections | SQL |

---

# User Datagram Protocol (UDP)

UDP is a **connectionless** transport protocol.

Unlike TCP, UDP does **not establish a connection** before transmitting data.

It sends packets without waiting for acknowledgments.

## Features

- Very fast
- Low overhead
- No error correction
- No retransmission
- No packet ordering

---

# Advantages of UDP

- Faster than TCP
- Low latency
- Minimal bandwidth overhead

---

# Common UDP Applications

| Application | Reason |
|-------------|--------|
| Video Streaming | Speed |
| Online Gaming | Low latency |
| Voice over IP (VoIP) | Real-time communication |
| DNS Queries | Fast lookups |

---

# TCP vs UDP

| Feature | TCP | UDP |
|----------|-----|-----|
| Connection | Yes | No |
| Reliability | High | Low |
| Speed | Slower | Faster |
| Packet Ordering | Yes | No |
| Error Recovery | Yes | No |
| Streaming | No | Yes |
| Gaming | Rarely | Common |
| File Transfer | Yes | No |

---

# Ports

TCP and UDP use **port numbers** to identify services running on a device.

Examples:

| Port | Protocol | Service |
|------|----------|---------|
| 20/21 | TCP | FTP |
| 22 | TCP | SSH |
| 25 | TCP | SMTP |
| 53 | TCP/UDP | DNS |
| 80 | TCP | HTTP |
| 110 | TCP | POP3 |
| 143 | TCP | IMAP |
| 443 | TCP | HTTPS |

---

# Layer 4 — Application Layer

The **Application Layer** is the highest layer of the TCP/IP model.

It provides network services directly to users and applications.

Examples include:

- Web browsers
- Email clients
- Remote access software
- File transfer applications

---

# Common Application Layer Protocols

## HTTP (Hypertext Transfer Protocol)

Purpose:

Transfers web pages between web browsers and web servers.

Example:

```
http://example.com
```

Characteristics:

- Uses TCP
- Default Port: **80**
- Not encrypted

---

## HTTPS (Hypertext Transfer Protocol Secure)

HTTPS is the secure version of HTTP.

Features:

- Encryption using TLS/SSL
- Authentication
- Data integrity

Default Port:

**443**

---

## DNS (Domain Name System)

DNS translates human-readable domain names into IP addresses.

Example:

```
www.google.com

↓

142.250.xxx.xxx
```

Without DNS, users would need to remember numerical IP addresses.

---

## SMTP (Simple Mail Transfer Protocol)

SMTP is responsible for **sending emails**.

Default Port:

25

---

## FTP (File Transfer Protocol)

FTP transfers files between computers.

Default Ports:

20 and 21

Disadvantage:

FTP transmits data without encryption.

---

## SSH (Secure Shell)

SSH provides secure remote access to systems.

Default Port:

22

Advantages:

- Encrypted communication
- Secure administration
- File transfer support (SCP/SFTP)

---

# Summary of TCP/IP Layers

| Layer | Responsibilities | Common Protocols |
|--------|------------------|------------------|
| Application | User services | HTTP, HTTPS, FTP, DNS, SMTP, SSH |
| Transport | Reliable communication | TCP, UDP |
| Internet | Routing | IP, ICMP |
| Network Access | Physical communication | Ethernet, Wi-Fi, ARP |

---

# OSI Model

The **Open Systems Interconnection (OSI) Model** is a conceptual networking framework developed by ISO.

It divides network communication into **seven layers**.

Unlike the TCP/IP model, the OSI model is primarily used for:

- Learning
- Troubleshooting
- Standardizing communication
- Explaining networking concepts

---

# OSI Layers

```
+----------------------+
| 7 Application        |
+----------------------+
| 6 Presentation       |
+----------------------+
| 5 Session            |
+----------------------+
| 4 Transport          |
+----------------------+
| 3 Network            |
+----------------------+
| 2 Data Link          |
+----------------------+
| 1 Physical           |
+----------------------+
```

---

# Layer 7 — Application

Provides services directly to users.

Protocols:

- HTTP
- HTTPS
- FTP
- DNS
- SMTP

Examples:

- Web browsers
- Email applications
- Cloud applications

---

# Layer 6 — Presentation

Responsible for:

- Data formatting
- Encryption
- Compression
- Character encoding

Examples:

- SSL/TLS Encryption
- JPEG
- ASCII
- Unicode

---

# Layer 5 — Session

Responsible for:

- Establishing sessions
- Maintaining sessions
- Terminating sessions

Functions:

- Authentication
- Synchronization
- Recovery checkpoints

---

# Layer 4 — Transport

Responsible for:

- Reliable delivery
- Segmentation
- Flow control
- Error recovery

Protocols:

- TCP
- UDP

---

# Layer 3 — Network

Responsible for:

- Logical addressing
- Routing
- Packet forwarding

Devices:

- Routers

Protocols:

- IP
- ICMP

---

# Layer 2 — Data Link

Responsible for communication inside the same network.

Functions:

- MAC Addressing
- Error detection
- Frame delivery

Devices:

- Switches
- NICs

Protocols:

- Ethernet
- HDLC
- PPP

---

# Layer 1 — Physical

Responsible for transmitting raw bits across physical media.

Examples:

- Ethernet cables
- Fiber optic cables
- Hubs
- Repeaters

Data is transmitted as:

```
101011010110101...
```

---

# OSI vs TCP/IP

| TCP/IP | OSI |
|---------|-----|
| 4 Layers | 7 Layers |
| Practical implementation | Conceptual model |
| Internet standard | Educational reference |
| Developed by DoD | Developed by ISO |
| Widely used | Used for learning & troubleshooting |

---

# Mapping TCP/IP to OSI

| TCP/IP | OSI Equivalent |
|---------|----------------|
| Application | Application + Presentation + Session |
| Transport | Transport |
| Internet | Network |
| Network Access | Data Link + Physical |

---

# Why Security Analysts Use Both Models

The models help analysts:

- Identify attack locations
- Troubleshoot network failures
- Understand protocol behavior
- Perform packet analysis
- Investigate malware communication
- Explain networking issues clearly

---
# 5. Cloud Computing & Software-Defined Networks (SDN)

As organizations grow, managing physical infrastructure becomes expensive and difficult. Instead of purchasing and maintaining servers, storage, and networking equipment, businesses increasingly rely on **cloud computing**, where computing resources are delivered over the internet.

Cloud computing provides flexibility, scalability, and cost savings while allowing organizations to deploy applications much faster.

---

## What is Cloud Computing?

Cloud computing is the delivery of computing resources over the internet instead of using physical infrastructure located inside an organization.

Traditional Infrastructure:

```
Company
 ├── Servers
 ├── Storage
 ├── Routers
 ├── Firewalls
 └── Networking Equipment
```

Cloud Infrastructure:

```
Company
      │
      ▼
Internet
      │
      ▼
Cloud Service Provider
 ├── Virtual Servers
 ├── Storage
 ├── Databases
 ├── Firewalls
 ├── Networking
 └── Applications
```

Instead of buying hardware, organizations rent computing resources whenever they need them.

---

# On-Premise vs Cloud Computing

## On-Premise Network

Everything is owned and managed by the organization.

```
Company Office

Servers
Storage
Networking
Power
Cooling
Security
Maintenance
```

### Advantages

- Full control
- Better compliance
- Sensitive data remains local

### Disadvantages

- High initial cost
- Requires maintenance
- Difficult to scale
- Hardware upgrades are expensive

---

## Cloud Computing

Infrastructure belongs to the Cloud Service Provider (CSP).

```
Company
     │
     ▼
Cloud Provider
 ├── Servers
 ├── Storage
 ├── Databases
 ├── Networking
 └── Security
```

### Advantages

- Lower cost
- Easy scalability
- High availability
- Automatic updates
- Global accessibility

### Disadvantages

- Internet dependency
- Vendor lock-in
- Shared responsibility
- Compliance considerations

---

# Cloud Service Providers (CSP)

A **Cloud Service Provider (CSP)** owns large data centers containing thousands or millions of servers.

Examples include:

- Amazon Web Services (AWS)
- Microsoft Azure
- Google Cloud Platform (GCP)
- Oracle Cloud
- IBM Cloud

A company simply rents the resources it needs.

---

# Cloud Service Models

Cloud services are divided into three primary models.

---

# 1. Infrastructure as a Service (IaaS)

The cloud provider supplies:

- Virtual machines
- Networking
- Storage
- Virtual firewalls

The customer manages:

- Operating systems
- Applications
- Security configurations

Example:

```
Cloud Provider
    │
Provides:
Virtual Machines
Storage
Networking

Customer
    │
Installs:
Linux
Windows
Applications
```

Examples:

- AWS EC2
- Azure Virtual Machines
- Google Compute Engine

---

## Advantages

- Highly flexible
- Full operating system control
- Pay only for resources used

---

## Disadvantages

- Customer manages security
- Customer installs updates

---

# 2. Platform as a Service (PaaS)

The cloud provider manages:

- Servers
- Operating systems
- Databases
- Runtime environment

Developers only write application code.

```
Developer
      │
Writes Application
      │
      ▼
Cloud Platform
 ├── Operating System
 ├── Database
 ├── Web Server
 └── Runtime
```

Examples:

- Google App Engine
- Azure App Service
- Heroku

---

## Advantages

- Faster application development
- No infrastructure management
- Easy deployment

---

## Disadvantages

- Less system control
- Vendor dependency

---

# 3. Software as a Service (SaaS)

The provider manages everything.

Users simply use the application.

```
User
   │
   ▼
Browser
   │
   ▼
Cloud Software
```

Examples:

- Gmail
- Google Drive
- Microsoft 365
- Dropbox
- Salesforce

---

## Advantages

- No installation required
- Accessible anywhere
- Automatic updates

---

## Disadvantages

- Limited customization
- Subscription costs

---

# Comparing Cloud Service Models

| Feature | IaaS | PaaS | SaaS |
|----------|------|------|------|
| User manages OS | ✅ | ❌ | ❌ |
| User develops apps | ✅ | ✅ | ❌ |
| Provider manages hardware | ✅ | ✅ | ✅ |
| Provider manages applications | ❌ | ❌ | ✅ |
| Best for | IT teams | Developers | End users |

---

# Hybrid Cloud

A hybrid cloud combines:

- On-premise infrastructure
- Public cloud

```
Company Data Center
        │
        │ Secure Connection
        ▼
Cloud Provider
```

Sensitive data remains on-premise while other workloads move to the cloud.

### Benefits

- Better flexibility
- Improved disaster recovery
- Lower infrastructure cost
- Easier migration

---

# Multi-Cloud

A multi-cloud environment uses multiple cloud providers simultaneously.

Example:

```
AWS
   │
Azure
   │
Google Cloud
```

Reasons:

- Avoid vendor lock-in
- Improve reliability
- Choose best service from each provider

---

# Software-Defined Networking (SDN)

Traditional networking depends heavily on physical devices.

```
Router
Switch
Firewall
Load Balancer
```

Software-Defined Networking replaces many of these with software-controlled virtual devices.

Instead of manually configuring each device, administrators control the network centrally through software.

---

## Traditional Network

```
Router
   │
Switch
   │
Firewall
```

Each device must be configured separately.

---

## Software-Defined Network

```
Controller
      │
 ┌────┼────┐
 │    │    │
 ▼    ▼    ▼
Virtual Router
Virtual Switch
Virtual Firewall
```

A central controller manages all devices.

---

# Benefits of SDN

## Centralized Management

One controller manages the entire network.

---

## Automation

Configuration changes happen automatically.

---

## Scalability

New virtual devices can be created within minutes.

---

## Faster Deployment

Networks can be built quickly without purchasing hardware.

---

## Better Monitoring

Traffic visibility improves because software tracks all network activity.

---

# Cloud Security Services

Cloud providers also offer security tools such as:

- Firewalls
- Web Application Firewalls (WAF)
- Intrusion Detection Systems (IDS)
- Intrusion Prevention Systems (IPS)
- Identity and Access Management (IAM)
- Encryption services
- Security monitoring

These services improve security while reducing administrative effort.

---

# Benefits of Cloud Computing

## Reliability

Cloud providers maintain redundant infrastructure.

Benefits include:

- High availability
- Backup systems
- Disaster recovery
- Global access

---

## Cost Savings

Organizations avoid purchasing expensive hardware.

Pay only for:

- Storage used
- Compute power used
- Network traffic

---

## Scalability

Resources increase or decrease based on demand.

Example:

```
Holiday Sale

Traffic ↑

Cloud automatically adds:

Server 1
Server 2
Server 3
Server 4
```

When demand decreases, extra servers are removed.

---

# Cloud Security Responsibilities

Cloud security follows the **Shared Responsibility Model**.

### Cloud Provider

Responsible for:

- Physical data centers
- Networking hardware
- Hypervisors
- Infrastructure availability

### Customer

Responsible for:

- User accounts
- Passwords
- MFA
- Data security
- Application security
- Permissions
- Configurations

---

# Why Organizations Move to the Cloud

Organizations migrate because the cloud offers:

- Lower operational costs
- Faster deployment
- Global availability
- Better disaster recovery
- Improved scalability
- Easier collaboration
- Automatic infrastructure updates
- Flexible resource allocation

---

# Cybersecurity Perspective

Security analysts working with cloud environments commonly:

- Monitor cloud logs
- Configure IAM permissions
- Investigate cloud security alerts
- Review firewall rules
- Secure virtual machines
- Monitor cloud network traffic
- Protect cloud storage
- Respond to cloud incidents

Cloud security is now one of the most in-demand cybersecurity skills.

---

# Key Takeaways

- Cloud computing delivers computing resources over the internet.
- CSPs provide virtual servers, storage, networking, and applications.
- IaaS provides infrastructure.
- PaaS provides development platforms.
- SaaS provides complete software solutions.
- Hybrid cloud combines cloud and on-premise infrastructure.
- Multi-cloud uses multiple cloud providers.
- SDN virtualizes networking and enables centralized management.
- Cloud computing improves scalability, reliability, and cost efficiency.
- Security in the cloud follows the Shared Responsibility Model.
