# Course 5 — Module 3

## Table of Contents

- [CI/CD Security](#cicd-security)
- [OWASP Top 10](#owasp-top-10)
- [Open-Source Intelligence (OSINT)](#open-source-intelligence-osint)
- [Vulnerability Scanners](#vulnerability-scanners)
- [Software Updates and Patching](#software-updates-and-patching)
- [Attacker Mindset and Vulnerability Assessment](#attacker-mindset-and-vulnerability-assessment)
- [Threat Actors and Attack Vectors](#threat-actors-and-attack-vectors)
- [Terms and Definitions](#terms-and-definitions-course-5-module-3)

---

## CI/CD Security

Building upon your understanding of vulnerability management, this reading focuses on a critical area of modern software development: CI/CD pipelines. CI/CD pipelines automate the software release process, and they require rigorous vulnerability management to stay secure.

Continuous Integration, Continuous Delivery, and Continuous Deployment (CI/CD) pipelines are essential for modern software development. They help teams deliver software faster and more efficiently. But like any powerful tool, CI/CD pipelines can also introduce security risks if not properly managed.

Understanding CI/CD vulnerabilities and applying vulnerability management principles can help secure the software delivery process.

### What Is CI/CD and Why Does It Matter?

CI/CD automates the software release process from code creation to deployment. This automation enables modern development teams to be agile and respond quickly to user needs.

#### Continuous Integration (CI)

Continuous Integration is about frequently merging code changes from different developers into a central location. This triggers automated processes like building the software and running tests.

CI catches problems through an automated process. Every time code is integrated, the system automatically builds and tests it. This immediate feedback loop reveals integration problems as soon as they occur.

#### Continuous Delivery (CD)

Continuous Delivery means code is always ready to be released to users. After passing automated tests, code is automatically deployed to a staging environment or prepared for final release. Typically, a manual approval step is still needed before going live to production.

#### Continuous Deployment (CD)

Continuous Deployment automates the entire release process. Changes that pass all automated checks are automatically deployed directly to the live production environment, with no manual approval.

### Security Benefits of Continuous Delivery and Deployment

Continuous Delivery and Deployment can enhance security by allowing security checks to be built into the deployment pipeline. This ensures that only thoroughly vetted software versions are released.

Automated security checks can include:

- Dynamic Application Security Testing (DAST)
- Security compliance checks
- Infrastructure security validations

### Why a Secure CI/CD Pipeline Is Non-Negotiable

Pipeline protection is essential.

#### Secure Automation

CI/CD automates repetitive tasks like building, testing, and deploying. When automation is implemented securely, it reduces errors from manual work, speeds processes, and reduces human errors that create vulnerabilities. However, insecure automation automates the introduction of vulnerabilities at scale.

#### Improved Code Quality via Security Checks

Automated tests in CI/CD rigorously check code before release, including automated security tests. This leads to fewer bugs and security weaknesses in final software, but only if security tests integrate effectively within the pipeline.

#### Faster Time to Market for Security Updates

CI/CD accelerates releases. This enables faster delivery of new features, bug fixes, and security updates, improving response time to both user needs and security threats.

#### Enhanced Collaboration and Feedback with a Safety Focus

CI/CD encourages collaboration between development, security, testing, and operations teams. Quick feedback loops help identify and resolve vulnerabilities early in development.

#### Reduced Risk

Frequent, smaller releases are less risky than large, infrequent releases. If issues arise, pinpointing and fixing the problem becomes easier. Smaller releases also limit the potential impact of a security flaw introduced in any single release, provided monitoring and testing remain continuous.

### Common CI/CD Pipeline Vulnerabilities

#### Insecure Dependencies

CI/CD pipelines often use many third-party libraries and components. If these components have known vulnerabilities, those vulnerabilities can be unknowingly added to your application during the automated build process.

Action step: Regularly scan and update dependencies.

#### Misconfigured Permissions

Weak access controls in CI/CD tools, code repositories, and related systems are a major vulnerability. Unauthorized access can allow attackers to modify code, pipeline configurations, or inject malicious content.

Action step: Implement strong access management using Role-Based Access Control (RBAC).

#### Lack of Automated Security Testing

Failing to include automated security testing in your CI/CD pipeline is a serious error. Without tools like SAST and DAST, vulnerable software may be released and problems may go undetected until after deployment.

Action step: Integrate automated security testing into your CI/CD pipeline.

#### Exposed Secrets

Hardcoding sensitive data like API keys, passwords, and tokens directly into code or pipeline settings is a serious security mistake.

Action step: Never hardcode secrets. Use secure vaults or dedicated secrets management tools.

#### Unsecured Build Environments

The CI/CD environment itself needs to be secure. If it is vulnerable, attackers can compromise it to alter builds, inject malicious code, or steal sensitive data.

Action step: Harden build environments and use secure containers or virtual machines.

### Building a Secure CI/CD Pipeline: Defense in Depth

#### Integrate Security from the Start

Adopt a DevSecOps mindset. Build security into every stage of development, from planning to deployment and beyond.

#### Implement Strong Access Controls

Use strict permission policies based on the principle of least privilege. Only grant necessary access to code, pipeline settings, and deployment configurations. Use MFA and RBAC.

#### Automate Security Testing Everywhere

Make automated security scans and tests a fundamental part of your build and deployment process. Tools like SAST, Software Composition Analysis (SCA), and DAST are essential.

#### Keep Dependencies Updated

Maintain a current inventory of third-party dependencies, libraries, and CI/CD plugins. Regularly update them to patch vulnerabilities.

#### Secure Secrets Management

Never hardcode sensitive information. Use dedicated secrets management tools such as HashiCorp Vault or AWS Secrets Manager.

### Conclusion

By proactively addressing CI/CD vulnerabilities and implementing security best practices, software teams can build and release applications with a stronger security posture.

### Key Takeaways

- Secure CI/CD improves software release processes.
- Security built into CI/CD supports resilience against threats.
- Secure pipelines help teams release features, improvements, and critical updates rapidly and reliably.

---

## OWASP Top 10

OWASP, recently renamed Open Worldwide Application Security Project, is a nonprofit foundation that works to improve the security of software. It is an open platform used by security professionals around the world to share information, tools, and events focused on securing the web.

### The OWASP Top 10

One of OWASP’s most valuable resources is the OWASP Top 10. OWASP has published this list since 2003 to spread awareness of the web’s most targeted vulnerabilities.

The Top 10 mainly applies to new or custom-made software. Many large organizations reference the OWASP Top 10 during application development to help ensure their programs address common security mistakes.

**Pro tip:** OWASP’s Top 10 is updated every few years as technologies evolve. Rankings are based on how often the vulnerabilities are discovered and the level of risk they present.

**Note:** Auditors also use the OWASP Top 10 as one point of reference when checking for regulatory compliance.

### Common Vulnerabilities

#### Broken Access Control

Access controls limit what users can do in a web application. Failures can lead to unauthorized information disclosure, modification, or destruction.

#### Cryptographic Failures

Sensitive data should be protected with effective encryption methods. Vulnerabilities can occur when businesses fail to encrypt things like personally identifiable information (PII). Weak hashing algorithms like MD5 increase risk.

#### Injection

Injection occurs when malicious code is inserted into a vulnerable application. Injection attacks can give threat actors a backdoor into an organization’s information system.

#### Insecure Design

Applications should be designed to be resilient to attack. Insecure design refers to missing or poorly implemented security controls that should have been programmed into an application during development.

#### Security Misconfiguration

Misconfigurations occur when security settings are not properly set or maintained. A common example is deploying equipment using default settings.

#### Vulnerable and Outdated Components

Developers often use open-source libraries to complete projects faster. Applications that use vulnerable components that have not been maintained are at greater risk of exploitation.

#### Identification and Authentication Failures

When applications fail to recognize who should have access and what they are authorized to do, serious problems can occur.

#### Software and Data Integrity Failures

These are instances when updates or patches are inadequately reviewed before implementation. Attackers might exploit these weaknesses to deliver malicious software. A supply chain attack is one example of the downstream effects.

A famous example is the SolarWinds cyber attack in 2020, where hackers injected malicious code into updates that the company unknowingly released to customers.

#### Security Logging and Monitoring Failures

Logging and tracing events is critical for finding and fixing problems. Sufficient monitoring and incident response are equally important.

#### Server-Side Request Forgery

SSRF occurs when attackers manipulate server operations to read or update other resources on the server. Malicious code can be carried by a vulnerable app to the host server, which then fetches unauthorized data.

### Key Takeaways

- OWASP Top 10 is a useful resource for learning about common web vulnerabilities.
- It mainly helps organizations designing new software.
- It is widely used in application development and compliance review.

---

## Open-Source Intelligence (OSINT)

Cyber attacks can sometimes be prevented with the right information, which starts with knowing where your systems are vulnerable. Open-source intelligence, commonly known as OSINT, is the collection and analysis of information from publicly available sources to generate usable intelligence.

### Information vs. Intelligence

- **Information:** Raw data or facts about a specific subject
- **Intelligence:** Analysis of information to produce knowledge or insights that support decision-making

### Why OSINT Matters

OSINT plays a significant role in information security (InfoSec), which is the practice of keeping data in all states away from unauthorized users.

OSINT can be used to:

- Provide insights into cyber attacks
- Detect potential data exposures
- Evaluate existing defenses
- Identify unknown vulnerabilities

Collecting intelligence is sometimes part of the vulnerability management process.

### OSINT Sources and Tools

Information can be gathered from:

- Search engines
- Social media
- Discussion boards
- Blogs
- Other public sources

Some commonly used OSINT tools and resources include:

- VirusTotal
- MITRE ATT&CK
- OSINT Framework
- Have I Been Pwned

### Key Takeaways

- OSINT helps security teams make evidence-based decisions.
- It supports identifying threats and vulnerabilities.
- Familiarity with OSINT tools makes research easier.

---

## Vulnerability Scanners

Previously, you learned about vulnerability assessments, which are internal review processes of an organization’s security systems. Vulnerability scanning tools simulate threats by finding vulnerabilities in an attack surface.

### What Is a Vulnerability Scanner?

A vulnerability scanner is software that automatically compares known vulnerabilities and exposures against the technologies on the network. These tools scan systems to find misconfigurations or programming flaws.

Scanning tools are used to analyze five attack surfaces:

- Perimeter layer
- Network layer
- Endpoint layer
- Application layer
- Data layer

When a scan begins, the scanning tool compares the findings against databases of security threats. At the end of the scan, the tool flags vulnerabilities and adds them to its reference database.

**Note:** Vulnerability databases are routinely updated by the company that designed the scanning software.

### Performing Scans

Vulnerability scanners are meant to be non-intrusive. They do not break or take advantage of a system like an attacker would. Instead, they simply scan a surface and alert you to potential weaknesses.

**Note:** While vulnerability scanners are non-intrusive, a scan can sometimes inadvertently cause issues, like crashing a system.

### External vs. Internal Scans

These simulate an attacker’s approach.

- **External scans** test the perimeter layer outside the internal network. They analyze outward-facing systems like websites and firewalls.
- **Internal scans** examine an organization’s internal systems. For example, they may analyze application software for weaknesses in how it handles user input.

### Authenticated vs. Unauthenticated Scans

These simulate whether or not a user has access to a system.

- **Authenticated scans** might test a system by logging in with a real user account or admin account.
- **Unauthenticated scans** simulate external threat actors without access to business resources.

### Limited vs. Comprehensive Scans

These focus on particular devices or all devices connected to a network.

- **Limited scans** analyze particular devices on a network, like a firewall
- **Comprehensive scans** analyze all devices connected to a network, including operating systems and user databases

**Pro tip:** Discovery scanning should be done prior to limited or comprehensive scans. Discovery scanning identifies the computers, devices, and open ports on a network.

### Key Takeaways

- Vulnerability scans vary depending on the surface being evaluated.
- Analysts and security professionals use scan results to guide compliance efforts, procedural changes, and patching.
- Understanding common scan types helps you participate in proactive security exercises.

---

## Software Updates and Patching

Software updates address security vulnerabilities that can place users, devices, and networks at risk.

### Patching Gaps in Security

A patch update is a software or operating system update that addresses security vulnerabilities within a program or product. Patches usually contain bug fixes that address common vulnerabilities and exposures.

**Note:** Patches may address vulnerabilities before malicious hackers find them, but some are developed after a zero-day is discovered.

### Common Update Strategies

#### Manual Updates

Manual deployment relies on IT departments or users obtaining updates from developers.

- **Advantage:** More control
- **Disadvantage:** Critical updates can be forgotten or ignored

#### Automatic Updates

Automatic deployment means the system or application finds, downloads, and installs updates.

**Pro tip:** CISA recommends using automatic options whenever they are available.

- **Advantage:** Simplified deployment and timely critical patches
- **Disadvantage:** Instability issues may occur if patches were not thoroughly tested

### End-of-Life Software

End-of-life (EOL) software no longer receives support from the manufacturer.

- Patches and updates are different from upgrades.
- CISA recommends discontinuing EOL software because it poses an unfixable risk to systems.

Replacing EOL technology can be costly, but the risk continues to grow as more connected devices enter the marketplace.

### Key Takeaways

- Updating software and patching vulnerabilities is critical.
- Many major cyber attacks might have been prevented if systems were kept updated.
- WannaCry in 2017 affected computers in more than 150 countries and caused an estimated $4 billion in damages. Researchers later found it could have been prevented if systems were patched months earlier.

---

## Attacker Mindset and Vulnerability Assessment

Cybersecurity is fast-paced, and new threats and technologies can disrupt plans at any moment. Security professionals need to be prepared by anticipating change.

### Being Prepared for Anything

Teams often conduct simulations of things that can go wrong as part of their vulnerability management strategy. One way this is done is by applying an attacker mindset to discovered weaknesses.

Applying an attacker mindset is like conducting an experiment. It is about causing problems in a controlled environment and evaluating the outcome to gain insights.

### Simulating Threats

Attack simulations are normally performed in two ways:

- **Proactive simulations**: Assume the role of an attacker by exploiting vulnerabilities and breaking through defenses. This is sometimes called a red team exercise.
- **Reactive simulations**: Assume the role of a defender responding to an attack. This is sometimes called a blue team exercise.

### Scanning for Trouble

A vulnerability scanner automatically compares common vulnerabilities and exposures against technologies on the network.

A reactive simulation might follow these steps:

1. **Identification:** A vulnerable server is flagged because it is running an outdated operating system
2. **Vulnerability analysis:** Research is done on the outdated OS and its vulnerabilities
3. **Risk assessment:** The severity of each vulnerability is scored and the impact of not fixing it is evaluated
4. **Remediation:** The information gathered is used to address the issue

During these exercises, teams often produce reports of their findings. Clearly communicating results is an important security skill.

### Finding Innovative Solutions

Many security controls were created as reactive responses to risks. Criminals continually look for ways to bypass existing defenses, so security professionals need to stay knowledgeable about trends and emerging technologies.

**Pro tip:** Resources like NIST’s National Vulnerability Database (NVD) can help you stay current on common vulnerabilities.

### Key Takeaways

- Vulnerability assessments are an important part of security risk planning.
- Analysts may participate in proactive and reactive simulations.
- Staying informed about new technologies helps you think with an innovative mindset.

---

## Threat Actors and Attack Vectors

Defending an attack surface starts with thinking like a threat actor. It is important to understand why someone would pose a threat to organizational assets and how they might gain access.

### Threat Actors

A threat actor is any person or group who presents a security risk. This includes people inside and outside an organization, and people who intentionally pose a threat or accidentally put assets at risk.

Threat actors are divided into five categories based on motivation:

- **Competitors:** Rival companies that may benefit from leaked information
- **State actors:** Government intelligence agencies
- **Criminal syndicates:** Organized groups who make money from criminal activity
- **Insider threats:** Individuals with or who had authorized access to an organization’s resources
- **Shadow IT:** Individuals who use technologies that lack IT governance

### Types of Hackers

A hacker is any person who uses computers to gain unauthorized access to computer systems, networks, or data.

In security, the term applies to three types of individuals based on intent:

- **Unauthorized hackers:** Malicious hackers who use their skills to commit crimes
- **Authorized or ethical hackers:** Individuals who use their programming skills to improve an organization’s security
- **Semi-authorized hackers:** Individuals who might violate ethical standards but are not considered malicious

Examples:

- **Script kiddies:** Hackers with limited skills who use pre-written malicious code
- **Bug bounty participants:** Freelance hackers encouraged to find and report vulnerabilities
- **Hacktivists:** Individuals who use their skills to achieve a political goal

### Advanced Persistent Threats (APTs)

An advanced persistent threat (APT) is when a threat actor maintains unauthorized access to a system for an extended period of time.

APTs are mostly associated with nation states and state-sponsored actors. They often target private organizations first as a step toward gaining access to larger entities.

### Access Points

Threat actors may gain access through one or more of these attack vector categories:

- Direct access
- Removable media
- Social media platforms
- Email
- Wireless networks on premises
- Cloud services
- Supply chains

Recognizing a threat actor’s intentions helps determine which access points they might target.

### Key Takeaways

- Threat actors can be inside or outside an organization.
- Not every threat actor is intentionally malicious.
- Recognizing intentions and attack vectors is important for defending systems.
- Thinking like a threat actor strengthens security planning.

---

## Terms and Definitions — Course 5, Module 3

| Term | Definition |
|---|---|
| Advanced persistent threat (APT) | An instance when a threat actor maintains unauthorized access to a system for an extended period of time |
| Attack surface | All the potential vulnerabilities that a threat actor could exploit |
| Attack tree | A diagram that maps threats to assets |
| Attack vector | The pathways attackers use to penetrate security defenses |
| Bug bounty | Programs that encourage freelance hackers to find and report vulnerabilities |
| Common Vulnerabilities and Exposures (CVE®) list | An openly accessible dictionary of known vulnerabilities and exposures |
| Common Vulnerability Scoring System (CVSS) | A measurement system that scores the severity of a vulnerability |
| CVE Numbering Authority (CNA) | An organization that volunteers to analyze and distribute information on eligible CVEs |
| Defense in depth | A layered approach to vulnerability management that reduces risk |
| Exploit | A way of taking advantage of a vulnerability |
| Exposure | A mistake that can be exploited by a threat |
| Hacker | Any person who uses computers to gain access to computer systems, networks, or data |
| MITRE | A collection of non-profit research and development centers |
| Security hardening | The process of strengthening a system to reduce its vulnerability and attack surface |
| Threat actor | Any person or group who presents a security risk |
| Vulnerability | A weakness that can be exploited by a threat |
| Vulnerability assessment | The internal review process of a company’s security systems |
| Vulnerability management | The process of finding and patching vulnerabilities |
| Vulnerability scanner | Software that automatically compares existing common vulnerabilities and exposures against the technologies on the network |
| Zero-day | An exploit that was previously unknown |
