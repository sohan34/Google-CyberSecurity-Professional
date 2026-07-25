# Google Cybersecurity Certificate
# Course 3 - Module 4
# Network Hardening, Cloud Security & Brute Force Attacks
---

# Module Objectives

After completing this module, you should be able to:

- Understand brute force attacks and how they work.
- Differentiate between simple brute force and dictionary attacks.
- Explain virtual machines (VMs) and sandbox environments.
- Identify methods used to prevent brute force attacks.
- Understand defense in depth.
- Compare Firewall, IDS, IPS, and SIEM.
- Understand cloud security considerations.
- Explain the Shared Responsibility Model.
- Learn cloud security hardening techniques.
- Understand cryptography basics used in cloud security.

---

# 1. Brute Force Attacks

## Definition

A **Brute Force Attack** is a trial-and-error attack where an attacker repeatedly attempts different credentials until the correct one is found.

Think of it like repeatedly trying every key on a keychain until one opens the lock.

---

## Types of Brute Force Attacks

### 1. Simple Brute Force Attack

The attacker manually or automatically tries many username/password combinations.

Example:

```
admin / admin
admin / password
admin / 123456
admin / welcome
...
```

Eventually one may work.

---

### 2. Dictionary Attack

Instead of trying every possible password, attackers use a predefined list of commonly used passwords.

Examples:

```
password
Password123
qwerty
admin123
welcome
letmein
12345678
```

Attackers also use leaked credentials from previous data breaches.

---

# Why Brute Force Attacks Work

Common reasons:

- Weak passwords
- Password reuse
- Default credentials
- No MFA
- Unlimited login attempts

---

# Assessing Vulnerabilities

Organizations test systems before attackers do.

Two common testing environments:

- Virtual Machines (VMs)
- Sandboxes

---

# 2. Virtual Machines (VMs)

## Definition

A **Virtual Machine (VM)** is software that behaves like an independent computer.

```
Physical Computer
      │
Hypervisor
      │
 ┌─────────────┐
 │ Windows VM  │
 ├─────────────┤
 │ Linux VM    │
 ├─────────────┤
 │ Kali Linux  │
 └─────────────┘
```

Each VM is isolated.

---

## Why Security Analysts Use VMs

- Malware analysis
- Safe testing
- Vulnerability assessment
- Software testing
- Reverse engineering

---

## Advantages

✅ Isolation

Malware usually stays inside the VM.

✅ Snapshots

Return to a previous clean state instantly.

✅ Easy testing

Run different operating systems simultaneously.

---

## Risks

Very advanced malware may detect:

- Virtual Machines
- Sandbox environments

Some malware refuses to execute if it detects virtualization.

---

# 3. Sandbox

## Definition

A sandbox is an isolated testing environment used to safely execute unknown or suspicious software.

Think of it as a quarantine room.

---

## Uses

- Malware analysis
- Patch testing
- Vulnerability testing
- Application testing
- Simulating cyber attacks

---

## Types

### Physical Sandbox

Separate computer

```
No Internet
No Company Network
```

---

### Virtual Sandbox

Cloud VM or local VM

Most organizations use virtual sandboxes because they are faster and cheaper.

---

# VM vs Sandbox

| Virtual Machine | Sandbox |
|----------------|----------|
| Virtual computer | Isolated testing environment |
| Runs complete operating system | Runs isolated software |
| Good for OS testing | Good for malware testing |
| Can revert snapshots | Safe execution environment |

---

# Preventing Brute Force Attacks

## 1. Hashing

Hashing converts data into a fixed-length value.

Example:

```
Password

↓

5f4dcc3b5aa765d61d8327deb882cf99
```

Properties:

- One-way
- Cannot be reversed
- Used for password storage

---

## 2. Salting

A salt is random data added before hashing.

Without salt:

```
Password123

↓

Same hash every time
```

With salt:

```
Password123 + x8#L@

↓

Different hash
```

Benefits:

- Prevents rainbow table attacks
- Makes password cracking much harder

---

# 3. Multi-Factor Authentication (MFA)

Requires multiple authentication methods.

Example:

```
Password

+

Phone verification

+

Fingerprint
```

Authentication factors:

### Something you know

- Password
- PIN

### Something you have

- Phone
- Security token

### Something you are

- Fingerprint
- Face scan

---

# 4. Two-Factor Authentication (2FA)

Uses exactly two authentication factors.

Example:

```
Password

+

OTP sent to phone
```

Remember:

```
2FA ⊂ MFA
```

All 2FA is MFA.

Not all MFA is 2FA.

---

# 5. CAPTCHA

CAPTCHA:

**Completely Automated Public Turing Test to Tell Computers and Humans Apart**

Purpose:

Stop bots from brute forcing passwords.

Examples:

- Select traffic lights
- Type distorted text
- Solve image puzzle

---

# 6. reCAPTCHA

Google's CAPTCHA service.

Examples:

```
☑ I'm not a robot
```

Invisible versions also analyze user behavior.

---

# 7. Password Policies

Organizations enforce rules like:

- Minimum length
- Complexity
- Password expiration
- Password history
- Account lockout after failed attempts

Example:

```
Minimum length:
12 characters

Uppercase:
Required

Numbers:
Required

Symbols:
Required
```

---

# Defense in Depth

Definition:

Using multiple security controls instead of relying on only one.

Example:

```
Firewall

↓

IDS

↓

IPS

↓

SIEM

↓

SOC Analyst
```

Each layer provides additional protection.

---

# 4. Firewall

## Definition

A firewall filters incoming and outgoing network traffic.

```
Internet

↓

Firewall

↓

Internal Network
```

---

## Function

Allows or blocks traffic based on rules.

Checks:

- IP
- Port
- Protocol

NGFW also inspects packet payload.

---

## Advantages

- First line of defense
- Blocks unwanted traffic
- Easy rule-based filtering

---

## Limitations

Cannot detect every sophisticated attack.

Traditional firewalls mainly inspect packet headers.

---

# 5. Intrusion Detection System (IDS)

## Definition

IDS monitors traffic and alerts administrators when suspicious activity is detected.

```
Internet

↓

Firewall

↓

IDS

↓

LAN
```

---

## Functions

- Detect attacks
- Detect anomalies
- Generate alerts

Does NOT block attacks.

---

## Detection Methods

### Signature-based

Matches known attack signatures.

### Anomaly-based

Detects abnormal behavior.

---

## Advantages

- Detects attacks
- Sends alerts
- Helps incident response

---

## Disadvantages

- Cannot stop attacks
- Misses unknown threats
- False positives possible

---

# 6. Intrusion Prevention System (IPS)

## Definition

IPS detects and actively blocks malicious traffic.

```
Internet

↓

Firewall

↓

IPS

↓

LAN
```

---

## Functions

- Detect
- Alert
- Drop packets
- Block attackers

Unlike IDS, IPS is active.

---

## Advantages

- Stops attacks automatically
- Prevents malicious traffic
- Better protection

---

## Disadvantages

- Inline device
- If IPS fails, network traffic stops
- False positives may block legitimate traffic

---

# IDS vs IPS

| IDS | IPS |
|------|------|
| Detects | Detects |
| Alerts | Alerts |
| Does NOT block | Blocks attacks |
| Passive | Active |
| Out-of-band | Inline |

---

# 7. Full Packet Capture Devices

Purpose:

Record **every network packet**.

Useful for:

- Incident response
- Forensics
- Investigating IDS alerts
- Malware analysis

---

# 8. SIEM

Security Information and Event Management

---

## Definition

SIEM collects logs from many devices into one dashboard.

Sources include:

- Firewalls
- IDS
- IPS
- VPN
- DNS
- Proxy
- Servers

```
Firewall

IDS

IPS

VPN

DNS

↓

SIEM Dashboard
```

---

## Benefits

- Centralized monitoring
- Correlation of events
- Real-time alerts
- Faster investigations

Known as:

**Single Pane of Glass**

---

## Popular SIEM Tools

- Splunk
- Google Chronicle
- Microsoft Sentinel
- QRadar

---

## Limitation

SIEM reports events.

It does **not automatically stop attacks.**

---

# Device Comparison

| Tool | Detect | Block | Alert |
|------|---------|--------|-------|
| Firewall | Limited | Yes | No |
| IDS | Yes | No | Yes |
| IPS | Yes | Yes | Yes |
| SIEM | Yes | No | Yes |

---

# Cloud Security

Cloud computing introduces unique security challenges.

---

## Major Cloud Security Considerations

### Identity and Access Management (IAM)

Controls:

- Authentication
- Authorization
- User roles
- Permissions

Poor IAM configuration is a major source of cloud breaches.

---

### Configuration

Misconfigured cloud services are one of the biggest causes of security incidents.

Examples:

- Public storage buckets
- Weak permissions
- Open ports

---

### Attack Surface

Each cloud service increases potential attack vectors.

More services

↓

More complexity

↓

More monitoring required

---

### Zero-Day Attacks

A **Zero-Day Attack** exploits a vulnerability before a patch is available.

Cloud providers often patch infrastructure quickly.

---

### Visibility

Organizations cannot directly monitor CSP infrastructure.

Instead they use:

- Flow logs
- Packet mirroring
- Cloud monitoring tools

---

### Frequent Changes

Cloud providers continuously update services.

Organizations must adapt configurations accordingly.

---

# Shared Responsibility Model

Defines who secures what.

---

## CSP Responsibilities

Cloud Provider secures:

- Physical data centers
- Hardware
- Networking
- Hypervisors
- Host operating systems

---

## Customer Responsibilities

Customer secures:

- Applications
- Data
- User accounts
- IAM
- Configurations
- Encryption keys (if customer-managed)

---

## Easy Memory Trick

```
Security OF the Cloud
↓

Cloud Provider

Security IN the Cloud
↓

Customer
```

---

# Cloud Security Hardening

Cloud hardening strengthens cloud environments.

---

## IAM

Least privilege

Role-based access

Strong authentication

---

## Hypervisors

Hypervisor separates hardware from virtual machines.

---

### Type 1 Hypervisor

Runs directly on hardware.

Examples:

- VMware ESXi
- Hyper-V

Used by CSPs.

---

### Type 2 Hypervisor

Runs on top of an operating system.

Examples:

- VirtualBox
- VMware Workstation

Common for personal labs.

---

## VM Escape

A VM Escape occurs when malware escapes a virtual machine and accesses:

- Host OS
- Hypervisor
- Other VMs

Rare but dangerous.

---

## Baselining

A baseline is the secure reference configuration.

Examples:

- Enable encryption
- Restrict admin access
- Enable SQL threat detection
- Password policies

---

# Cryptography in Cloud

Purpose:

Protect:

- Confidentiality
- Integrity
- Availability

---

## Encryption

Plaintext

↓

Encryption

↓

Ciphertext

↓

Decryption

↓

Plaintext

---

Encryption protects:

- Data at rest
- Data in transit

---

# Cryptographic Erasure

Also called:

Crypto-shredding

Instead of deleting data,

Destroy the encryption key.

Without the key,

The encrypted data becomes unreadable forever.

---

# Key Management

Encryption is only as secure as the encryption keys.

---

## Trusted Platform Module (TPM)

Hardware chip that stores:

- Passwords
- Certificates
- Encryption keys

---

## CloudHSM

Cloud Hardware Security Module

Provides:

- Secure key storage
- Encryption
- Decryption
- Cryptographic operations

---

# Cloud Security Summary

```
IAM
↓

Least Privilege
↓

Hypervisor Security
↓

Baselining
↓

Encryption
↓

Key Management
↓

Continuous Monitoring
```

---

# Important Exam Differences

| Topic | Remember |
|---------|----------|
| Brute Force | Tries every possibility |
| Dictionary Attack | Uses common password list |
| VM | Virtual computer |
| Sandbox | Isolated testing environment |
| Hashing | One-way transformation |
| Salting | Adds randomness before hashing |
| MFA | Two or more authentication factors |
| 2FA | Exactly two authentication factors |
| CAPTCHA | Stops bots |
| Firewall | Allows/blocks traffic |
| IDS | Detects & alerts |
| IPS | Detects, alerts & blocks |
| SIEM | Centralized log analysis |
| IAM | Identity & permission management |
| Hypervisor | Runs virtual machines |
| VM Escape | Malware escapes VM |
| Baseline | Secure reference configuration |
| Shared Responsibility | CSP secures cloud, customer secures data/configurations |
| Cryptographic Erasure | Destroy encryption keys |

---

# Quick Revision (1-Minute)

- Brute force = Trial-and-error password guessing.
- Dictionary attack = Uses common password lists.
- VM = Virtual computer for safe testing.
- Sandbox = Isolated environment for suspicious software.
- Hashing = One-way password protection.
- Salting = Adds random data before hashing.
- MFA = Multiple authentication factors.
- Firewall = Filters network traffic.
- IDS = Detects and alerts only.
- IPS = Detects and blocks attacks.
- SIEM = Centralized log collection and monitoring.
- IAM = Controls user identities and permissions.
- Shared Responsibility = CSP secures **the cloud**, customer secures **what's in the cloud**.
- Hypervisors run virtual machines (Type 1 on hardware, Type 2 on an OS).
- Cryptography protects cloud data using encryption.
- Cryptographic erasure securely destroys encrypted data by deleting the encryption keys.

---

# Key Terms

- Brute Force Attack
- Dictionary Attack
- Virtual Machine (VM)
- Sandbox
- Hashing
- Salting
- Multi-Factor Authentication (MFA)
- Two-Factor Authentication (2FA)
- CAPTCHA
- reCAPTCHA
- Defense in Depth
- Firewall
- Intrusion Detection System (IDS)
- Intrusion Prevention System (IPS)
- Full Packet Capture
- Security Information and Event Management (SIEM)
- Identity and Access Management (IAM)
- Hypervisor
- Type 1 Hypervisor
- Type 2 Hypervisor
- VM Escape
- Baseline
- Shared Responsibility Model
- Encryption
- Cryptography
- Cryptographic Erasure (Crypto-shredding)
- Trusted Platform Module (TPM)
- Cloud Hardware Security Module (CloudHSM)

---
**End of Course 3 Module 4 Notes**
