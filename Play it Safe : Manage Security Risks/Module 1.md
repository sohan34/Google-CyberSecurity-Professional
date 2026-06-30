## 📖 Overview

This module introduces the **CISSP's eight security domains**, the basics of **risk management**, and common **threats, risks, and vulnerabilities** that security analysts encounter.

---

# CISSP's Eight Security Domains

The **Certified Information Systems Security Professional (CISSP)** security domains represent key areas of cybersecurity knowledge.

## 1. Security and Risk Management

Focuses on developing and maintaining an organization's **security posture**, which is its ability to protect assets and respond to change.

### Includes

- Security goals and objectives
- Risk mitigation processes
- Compliance
- Business continuity plans
- Legal regulations
- Professional and organizational ethics

### Information Security (InfoSec)

InfoSec refers to the processes established to secure information.

Examples include:

- Incident response
- Vulnerability management
- Application security
- Cloud security
- Infrastructure security

> Organizations may modify security processes to comply with regulations such as GDPR.

---

## 2. Asset Security

Asset security focuses on managing organizational assets and their data throughout their lifecycle.

### Includes

- Storage
- Maintenance
- Retention
- Destruction

Security analysts help protect assets by:

- Creating backups
- Managing data exposure
- Supporting recovery plans
- Conducting security impact analysis

---

## 3. Security Architecture and Engineering

Focuses on protecting organizational data through secure systems, tools, and processes.

### Shared Responsibility

All individuals involved share responsibility for reducing security risks.

### Design Principles

- Threat modeling
- Least privilege
- Defense in depth
- Fail securely
- Separation of duties
- Keep it simple
- Zero trust
- Trust but verify

### Example

Using a **SIEM** tool to monitor unusual login or user activity.

---

## 4. Communication and Network Security

Focuses on securing:

- Physical networks
- Wireless communications
- Remote connections
- Cloud communications

Organizations implement network security controls to ensure secure access for remote and hybrid workers.

---

## 5. Identity and Access Management (IAM)

IAM ensures that:

- User identities are authenticated
- Access is authorized
- Unauthorized users are prevented from accessing systems

### Principle of Least Privilege

Users should receive only the minimum permissions required to perform their tasks.

---

## 6. Security Assessment and Testing

Focuses on identifying and reducing:

- Risks
- Threats
- Vulnerabilities

Common activities include:

- Security assessments
- Penetration testing
- Security control testing
- Security audits
- User permission reviews

---

## 7. Security Operations

Focuses on responding to and preventing security incidents.

### Includes

- Training and awareness
- Reporting and documentation
- Intrusion detection and prevention
- SIEM tools
- Log management
- Incident management
- Playbooks
- Post-breach forensics
- Lessons learned

Security teams investigate and respond to active threats while protecting organizational data.

---

## 8. Software Development Security

Focuses on developing secure software.

Security should be incorporated throughout the software development lifecycle:

- Design
- Development
- Testing
- Release

Common activities include:

- Application security testing
- Vulnerability identification
- Secure programming practices
- Quality assurance
- Penetration testing

Example:

Ensuring encryption is properly configured on a medical device storing patient data.

---

# Risk Management

Risk management helps organizations protect physical and digital assets.

## Examples of Assets

### Digital Assets

- Social Security Numbers (SSNs)
- Dates of birth
- Bank account numbers
- Mailing addresses

### Physical Assets

- Payment kiosks
- Servers
- Desktop computers
- Office spaces

---

## Risk Management Strategies

| Strategy | Description |
|----------|-------------|
| **Acceptance** | Accept the risk to avoid disrupting business continuity. |
| **Avoidance** | Eliminate the activity that creates the risk. |
| **Transference** | Transfer the risk to a third party. |
| **Mitigation** | Reduce the impact of a known risk. |

Organizations commonly use frameworks such as:

- NIST Risk Management Framework (RMF)
- HITRUST

---

# Threats

A **threat** is any circumstance or event that can negatively impact organizational assets.

### Common Threats

#### Insider Threats

Current employees, former employees, or vendors misuse authorized access.

#### Advanced Persistent Threats (APTs)

Threat actors maintain unauthorized access to systems over a long period.

---

# Risks

A **risk** is anything that can affect the confidentiality, integrity, or availability (CIA) of an asset.

### Types of Risks

#### External Risk

Threats originating outside the organization.

#### Internal Risk

Risks posed by employees, vendors, or trusted partners.

#### Legacy Systems

Older systems that remain connected and may introduce security weaknesses.

#### Multiparty Risk

Risks introduced by third-party vendors with access to organizational resources.

#### Software Compliance / Licensing

Risks caused by outdated software, missing updates, or unpatched systems.

> Organizations should stay informed about evolving cybersecurity risks through resources such as NIST and the OWASP Top 10.

---

# Vulnerabilities

A **vulnerability** is a weakness that can be exploited by a threat.

### Common Vulnerabilities

| Vulnerability | Description |
|--------------|-------------|
| **ProxyLogon** | Microsoft Exchange vulnerability allowing remote code execution. |
| **ZeroLogon** | Vulnerability affecting Microsoft's Netlogon authentication protocol. |
| **Log4Shell** | Allows attackers to execute Java code remotely or leak sensitive information. |
| **PetitPotam** | NTLM attack technique that forces authentication requests. |
| **Security Logging and Monitoring Failures** | Poor logging allows attackers to remain undetected. |
| **Server-Side Request Forgery (SSRF)** | Tricks servers into accessing unintended internal resources. |

Organizations reduce vulnerabilities through:

- Continuous monitoring
- Security updates
- Patch management
- Vulnerability management

The earlier vulnerabilities are identified and patched, the lower the organization's exposure to risk.

---

# Key Takeaways

- The **eight CISSP security domains** represent the core areas of cybersecurity.
- Security analysts help protect assets through risk management and secure processes.
- Organizations manage risks using **acceptance, avoidance, transference, and mitigation**.
- Common threats include **insider threats** and **advanced persistent threats (APTs)**.
- Risks may originate internally, externally, from legacy systems, third parties, or software issues.
- Vulnerabilities must be identified, monitored, and patched to reduce organizational risk.

---

# Important Terms

| Term | Definition |
|------|------------|
| **Security Posture** | An organization's ability to defend assets and react to change. |
| **Business Continuity** | Ability to maintain operations during disruptions. |
| **Shared Responsibility** | Everyone in an organization contributes to reducing security risks. |
| **Risk** | Anything affecting the confidentiality, integrity, or availability of an asset. |
| **Risk Mitigation** | Reducing the impact of a known risk. |
| **Threat** | An event or circumstance that can harm assets. |
| **Vulnerability** | A weakness that can be exploited by a threat. |
| **Internal Threat** | Risk from employees, vendors, or trusted partners. |
| **External Threat** | Risk originating outside the organization. |
| **Social Engineering** | Manipulating people to obtain sensitive information or access. |
| **Ransomware** | Malware that encrypts data and demands payment for recovery. |

