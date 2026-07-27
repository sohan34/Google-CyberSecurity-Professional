# Course 6 — Module 3

## Table of Contents

- [Methods of Detection](#methods-of-detection)
- [Ongoing Monitoring of CI/CD](#ongoing-monitoring-of-cicd)
- [Indicators of Compromise and the Pyramid of Pain](#indicators-of-compromise-and-the-pyramid-of-pain)
- [Threat Intelligence and Investigative Tools](#threat-intelligence-and-investigative-tools)
- [Documentation](#documentation)
- [Triage](#triage)
- [Business Continuity Planning](#business-continuity-planning)
- [Post-incident Activity](#post-incident-activity)
- [Terms and Definitions](#terms-and-definitions-course-6-module-3)

---

## Methods of Detection

Security analysts use detection tools to help discover threats, but there are additional methods of detection that can be used as well.

Previously, you learned about how detection tools can identify attacks like data exfiltration. In this reading, you’ll be introduced to different detection methods that organizations can employ to discover threats.

### Detection and Analysis Phase

During the Detection and Analysis phase of the incident response lifecycle, security teams are notified of a possible incident and work to investigate and verify the incident by collecting and analyzing data.

- **Detection** refers to the prompt discovery of security events.
- **Analysis** involves the investigation and validation of alerts.

### Existing Detection Tools

Security analysts use several tools to detect threats:

- Intrusion detection systems (IDS)
- Security information and event management (SIEM) tools

However, detection tools can only detect what security teams configure them to monitor. If they are not properly configured, they can fail to detect suspicious activity, leaving systems vulnerable.

Additional detection methods help increase coverage and accuracy.

### Threat Hunting

Threat hunting is the proactive search for threats on a network.

Security professionals use threat hunting to:

- Uncover malicious activity that was not identified by detection tools
- Perform further analysis on detections
- Detect threats before they cause damage

Example:

- Fileless malware is difficult for detection tools to identify because it hides in memory instead of using files or applications. Threat hunting combines human analysis with technology to identify threats like fileless malware.

**Note:** Threat hunters research emerging threats and attacks, determine an organization’s vulnerability to specific attacks, and use a combination of threat intelligence, indicators of compromise, indicators of attack, and machine learning to search for threats.

### Threat Intelligence

Organizations can improve detection by staying updated on the evolving threat landscape and understanding the relationship between their environment and malicious actors.

**Threat intelligence** is evidence-based threat information that provides context about existing or emerging threats.

Threat intelligence can come from private or public sources such as:

- Industry reports
- Government advisories
- Threat data feeds

#### Industry Reports

Industry reports often include details about an attacker’s tactics, techniques, and procedures (TTP).

#### Government Advisories

Government advisories also include attacker TTP information.

#### Threat Data Feeds

Threat data feeds provide a stream of threat-related data that helps protect against sophisticated attackers like advanced persistent threats (APTs).

- **Advanced persistent threat (APT):** Instances when a threat actor maintains unauthorized access to a system for an extended period of time.

Threat data feeds usually include indicators such as:

- IP addresses
- Domains
- File hashes

### Threat Intelligence Platforms

Organizations can use a **threat intelligence platform (TIP)** to manage large volumes of threat intelligence.

A TIP is an application that:

- Collects threat intelligence
- Centralizes threat intelligence
- Analyzes threat intelligence from different sources

TIPs help organizations identify and prioritize relevant threats and improve security posture.

**Note:** Threat intelligence data feeds are best used to add context to detections. They should not drive detections completely and should be assessed before being applied to an organization.

### Cyber Deception

Cyber deception uses techniques that deliberately deceive malicious actors to increase detection and improve defensive strategies.

#### Honeypots

Honeypots are an example of an active cyber defense mechanism that uses deception technology.

- **Honeypot:** A system or resource created as a decoy vulnerable to attacks with the purpose of attracting potential intruders.

Example:

- A fake file labeled `Client Credit Card Information - 2022` may trick a malicious actor into accessing it, which alerts security teams.

### Key Takeaways

- Organizations should use a variety of detection methods, tools, and technologies.
- Threat hunting, threat intelligence, and cyber deception improve detection coverage.
- Human-driven methods help identify hidden threats that automated tools may miss.

---

## Ongoing Monitoring of CI/CD

CI/CD pipelines can open up new vulnerabilities for attackers. Ongoing monitoring helps protect the software supply chain and identify unusual activity that may indicate indicators of compromise (IoCs).

### Automation for Finding Threats

CI/CD pipelines help release software faster, but they can also be attacked.

If someone breaks into the pipeline, they could:

- Add code
- Steal private information
- Stop software from working

Ongoing monitoring should automatically find unusual pipeline activity in:

- Build processes
- Code
- Deployment steps

This automated threat detection helps security teams respond quickly and limit damage.

### Common Indicators of Compromise in CI/CD Pipelines

Understanding CI/CD IoCs helps teams monitor effectively and quickly identify incidents.

#### Unauthorized Code Changes

Examples:

- Code changes from people who should not be making changes
- Code changes made at unusual times or from unexpected locations
- Suspicious code, such as confusing code, very large deletions without reason, or code that does not follow coding rules

#### Suspicious Deployment Patterns

Examples:

- Deployments to unusual or unapproved systems
- Production deployments started directly from developer branches
- Deployments happening at unexpected times or too often
- Deployments started by unusual user accounts or automated accounts that should not be releasing to production

#### Compromised Dependencies

Examples:

- Known vulnerabilities (CVEs) in dependencies found during automated checks
- Unexpected dependencies suddenly added to build settings
- Attempts to download dependencies from unofficial or untrusted sources

#### Unusual Pipeline Execution

Examples:

- Pipeline steps that normally work fine suddenly failing
- Pipelines taking much longer to run without explanation
- Changes in the order or way steps run without approved changes

#### Secrets Exposure Attempts

Examples:

- Logs showing attempts to access secrets from unapproved places in the pipeline
- Private secrets hardcoded in code changes

### Proactive Security Through Monitoring

Ongoing monitoring focused on automated anomaly detection and IoCs makes CI/CD security more proactive.

Benefits include:

- **Responding to incidents quickly**
- **Limiting damage**
- **Improving threat knowledge**

### Using Automation to Find Anomalies and IoCs

#### Comprehensive Logging and Auditing

Detailed logs are the basis of monitoring.

Common logs include:

- **Pipeline execution logs**
- **Code commit logs**
- **Access logs**
- **Deployment logs**

##### Pipeline Execution Logs

Specialized tools can use automated baselining techniques to analyze logs from successful, typical pipeline runs and establish a profile of normal operation.

A baseline may include:

- Standard duration of each pipeline stage
- Expected success and failure rates

Deviations such as unusually long steps, unexpected errors, or altered step order are flagged as possible IoCs.

##### Code Commit Logs

These logs track code changes for each pipeline run.

Examples of IoCs:

- Changes from unauthorized users
- Changes made late at night
- Suspicious content such as very large deletions or confusing code

##### Access Logs

Monitoring tools can learn who usually accesses CI/CD systems.

Examples of IoCs:

- Logins from different countries
- Failed login attempts followed by a successful login
- Login attempts to change important pipeline settings

##### Deployment Logs

These logs show how often deployments happen and what they look like.

Examples of IoCs:

- Deployments at odd times
- Deployments to unexpected places

#### SIEM Integration

Connecting CI/CD logs to a SIEM tool helps automatically find anomalies at scale.

SIEM platforms can:

- Automatically find anomalies using machine learning and analytics
- Use rules to alert on known IoCs

Examples of SIEM rules:

- Detect specific malicious file hashes in build results
- Alert when CI/CD servers connect to known malicious command and control (C2) servers
- Alert when someone tries to download or access private secrets outside approved pipeline steps

#### Real-time Alerting and Notifications

Automated alerts should notify security teams immediately of unusual activity.

Alerts should be set up for:

- Unusual build failures
- Suspicious code changes
- Attempts to expose secrets
- Unusual network traffic from CI/CD servers

#### Performance Monitoring

Performance monitoring can indirectly help find IoCs.

Performance issues, or indicators of attack (IoAs), such as sudden slowdowns or resources being exhausted, may lead to deeper checks that uncover IoCs.

#### Continuous Vulnerability Scanning

Regularly checking CI/CD infrastructure for weaknesses can proactively find vulnerable components.

This includes:

- CVEs in CI/CD tools
- CVEs in plugins
- CVEs in containers

These weaknesses should be patched quickly to prevent compromise.

### Key Takeaways

- Automated monitoring helps identify unusual activity in CI/CD pipelines.
- IoC detection supports fast response and reduces potential damage.
- Logging, SIEM integration, alerting, performance monitoring, and vulnerability scanning are important parts of CI/CD security.

---

## Indicators of Compromise and the Pyramid of Pain

Indicators of compromise (IoCs) are observable evidence that suggests signs of a potential security incident.

An IoC is evidence that points to something that has already happened.

Indicators of attack (IoAs) are the series of observed events that indicate a real-time incident.

- IoCs help identify the **who** and **what** of an attack after it has taken place.
- IoAs focus on the **why** and **how** of an ongoing or unknown attack.

Example:

- A process that makes a network connection is an IoA.
- The filename of the process and the IP address contacted are IoCs.

**Note:** IoCs do not always confirm a security incident. They may also result from human error or system malfunctions.

### Pyramid of Pain

Security researcher David J. Bianco created the **Pyramid of Pain** to help improve how IoCs are used in incident detection.

The Pyramid of Pain shows the relationship between IoCs and the difficulty attackers face when their activity is blocked.

If security teams block higher-level indicators, it becomes harder for attackers to continue.

The levels include:

- Hash values
- IP addresses
- Domain names
- Network artifacts
- Host artifacts
- Tools
- Tactics, techniques, and procedures (TTPs)

#### Hash Values

Hashes correspond to known malicious files and provide unique references to malware samples or files involved in an intrusion.

#### IP Addresses

Example:

- `192.168.1.1`

#### Domain Names

Example:

- `www.google.com`

#### Network Artifacts

Observable evidence created by malicious actors on a network.

Example:

- User-Agent strings in network protocols

#### Host Artifacts

Observable evidence created by malicious actors on a host.

Example:

- A file name created by malware

#### Tools

Software used by a malicious actor to achieve their goal.

Example:

- Password cracking tools like John the Ripper

#### TTPs

Tactics, techniques, and procedures describe attacker behavior.

- **Tactics:** High-level overview of behavior
- **Techniques:** Detailed descriptions of behavior related to a tactic
- **Procedures:** Highly detailed descriptions of a technique

TTPs are the hardest to detect.

### Key Takeaways

- IoCs and IoAs are important for identifying incidents.
- The Pyramid of Pain helps explain which indicators are more valuable for defense.
- Higher-level indicators are harder for attackers to change.

---

## Threat Intelligence and Investigative Tools

Threat intelligence adds context to IoCs and helps analysts build a fuller picture of an incident.

### Adding Context to Investigations

Security analysts need to expand the use of IoCs so they can add context to alerts.

**Threat intelligence** is evidence-based threat information that provides context about existing or emerging threats.

By adding context to an IoC, security teams can build a detailed picture of a security incident and respond more effectively.

### The Power of Crowdsourcing

Crowdsourcing is the practice of gathering information using public input and collaboration.

Threat intelligence platforms use crowdsourcing to collect information from the global cybersecurity community.

Benefits include:

- Organizations can learn from one another
- Attack details can be shared quickly
- Detection methods can improve over time

Examples of information-sharing organizations include:

- Information Sharing and Analysis Centers (ISACs)
- Open-source intelligence (OSINT) sources

**Open-source intelligence (OSINT):** The collection and analysis of information from publicly available sources to generate usable intelligence.

Threat intelligence data can be shared to improve detection products such as:

- Detection tools
- Antivirus software

Example:

- When one organization detects an attack, it can publish details like malicious files, IP addresses, or URLs to tools like VirusTotal so others can defend against the same attack.

### VirusTotal

VirusTotal is a service that allows anyone to analyze suspicious files, domains, URLs, and IP addresses for malicious content.

It is free for non-commercial use and also offers enterprise services.

VirusTotal reports include:

#### Detection

Lists third-party security vendors and their verdicts on an IoC.

#### Details

Provides static analysis details such as:

- Hashes
- File types
- File sizes
- Headers
- Creation time
- First and last submission information

#### Relations

Shows related IoCs such as:

- Contacted URLs
- Domains
- IP addresses
- Dropped files

#### Behavior

Shows observed activity after execution in a controlled or sandboxed environment, including:

- Tactics and techniques detected
- Network communications
- Registry and file system actions
- Processes

#### Community

Contains comments and insights from VirusTotal community members.

#### Vendors’ Ratio and Community Score

The score at the top of the report is the vendors’ ratio, which shows how many vendors flagged the IoC as malicious.

The community score is based on inputs from the VirusTotal community.

**Note:** Data uploaded to VirusTotal is publicly shared with the entire community. Do not upload personal information.

### Other Investigative Tools

#### Jotti Malware Scan

A free service that scans suspicious files with several antivirus programs.

#### Urlscan.io

A free service that scans and analyzes URLs and provides a detailed report.

#### MalwareBazaar

A free repository for malware samples that can be used for threat intelligence and research.

### Key Takeaways

- Threat intelligence helps add context to IoCs.
- Crowdsourcing improves detection capabilities across the security community.
- Tools like VirusTotal help analysts investigate suspicious artifacts.

---

## Documentation

Documentation is any form of recorded content used for a specific purpose. It is essential in security for investigations, task completion, and communication.

### Documentation Benefits

Effective documentation has three benefits:

- Transparency
- Standardization
- Clarity

#### Transparency

Transparency is critical for:

- Demonstrating compliance
- Meeting insurance requirements
- Legal proceedings

**Chain of custody** is an example of documentation that produces transparency and an audit trail.

- **Chain of custody:** The process of documenting evidence possession and control during an incident lifecycle.

#### Standardization

Standardization through repeatable processes and procedures supports:

- Continuous improvement
- Knowledge transfer
- Onboarding of new team members

**Standards** are references that inform how to set policies.

An **incident response plan** is an example of documentation that establishes standardization.

- **Incident response plan:** A document that outlines the procedures to take in each step of incident response.

#### Clarity

Clear documentation helps people quickly access the information they need and understand what action to take.

Security analysts must document the reasoning behind their actions so the team understands why an alert was escalated or closed.

### Best Practices

#### Know Your Audience

Write documentation based on the audience’s needs.

Example:

- A report for a SOC manager should be more technical than a report for a CEO.

#### Be Concise

Long documentation can discourage use. Establish the purpose immediately and keep executive summaries brief.

#### Update Regularly

Documentation must be reviewed and updated to reflect new vulnerabilities and changes in processes.

After an incident is resolved, a review may identify gaps that require updates.

### Key Takeaways

- Documentation supports transparency, standardization, and clarity.
- Good documentation is tailored, concise, and updated regularly.
- Documentation is a critical skill for security analysts.

---

## Triage

Triage is used to assess alerts and assign priority to incidents.

### Triage Process

Triage is the prioritizing of incidents according to their level of importance or urgency.

The triage process consists of three steps:

1. Receive and assess
2. Assign priority
3. Collect and analyze

### Receive and Assess

A security analyst receives an alert from a system such as an IDS.

The analyst reviews the alert to verify its validity and understand the activity that triggered it.

Questions to consider:

- Is the alert a false positive?
- Has this alert happened before?
- Was it triggered by a known vulnerability?
- What is the severity of the alert?

- **False positive:** An alert that incorrectly detects the presence of a threat

### Assign Priority

Once an alert is verified as a genuine issue, it is prioritized.

Factors to consider:

#### Functional Impact

How much does the incident affect the business function of the affected system?

Example:

- Ransomware can severely impact confidentiality, availability, and integrity by encrypting or deleting data.

#### Information Impact

How does the incident affect confidentiality, integrity, and availability of data?

Example:

- In a data exfiltration attack, sensitive data may be stolen and shared publicly.

#### Recoverability

How possible and costly is recovery?

If recovery is not possible, spending time and resources may be wasteful.

**Note:** Alerts often come with an assigned priority or severity level.

### Collect and Analyze

The final step involves gathering evidence from different sources, researching externally, and documenting the investigative process.

The goal is to make an informed decision about how to address the incident.

Depending on severity, escalation to a level two analyst or manager may be required.

### Benefits of Triage

#### Resource Management

Triage helps teams focus resources on urgent threats and reduce response time.

#### Standardized Approach

Triage provides a standardized approach to incident handling. Playbooks help move alerts through an iterative process so only valid alerts are escalated.

### Key Takeaways

- Triage prioritizes incidents by importance and urgency.
- It helps security teams use resources effectively.
- Standardized triage supports timely and accurate response.

---

## Business Continuity Planning

Security teams must minimize the impact that incidents have on normal business operations.

Prolonged disruption can cause:

- Legal damage
- Financial damage
- Reputational damage

A **business continuity plan (BCP)** helps organizations remain operational during major disruptions.

- **Business continuity plan (BCP):** A document that outlines the procedures to sustain business operations during and after a significant disruption.

Entry-level security analysts are not usually responsible for developing and testing BCPs, but it is important to understand how they help organizations respond and recover.

**Note:** BCPs are not the same as disaster recovery plans. Disaster recovery plans focus on restoring information systems after a major disaster such as hardware failure or facility destruction.

### Ransomware and Business Continuity

Ransomware can severely disrupt business operations, especially in critical infrastructure such as healthcare.

Impacts can include:

- Disabled access to medical records
- Reduced delivery of essential healthcare services
- Threats to national security, economic security, and public safety

BCPs help minimize interruptions so essential services can continue.

### Recovery Strategies

When an outage occurs due to a security incident, organizations need a functional recovery plan.

**Site resilience** is one recovery strategy.

- **Resilience:** The ability to prepare for, respond to, and recover from disruptions.

### Site Resilience

Site resilience ensures the availability of networks, data centers, or other infrastructure during disruption.

There are three types of recovery sites:

#### Hot Sites

A fully operational duplicate of the primary environment.

- Can be activated immediately
- Useful when the primary site fails

#### Warm Sites

A facility with a fully updated and configured version of the hot site.

- Not fully operational
- Can be made operational quickly

#### Cold Sites

A backup facility with some necessary infrastructure.

- Not ready for immediate use
- May require additional work before becoming operational

### Key Takeaways

- Business continuity plans help organizations remain operational during disruptions.
- Ransomware and other incidents can seriously disrupt critical services.
- Site resilience and recovery sites support continuity and recovery.

---

## Post-incident Activity

The Post-incident activity phase of the NIST Incident Response Lifecycle is the process of reviewing an incident to identify areas for improvement during incident handling.

### Lessons Learned

After an incident is contained, eradicated, and recovered from, the incident comes to a close. However, the work is not complete.

Incidents give organizations the opportunity to learn and improve future response efforts.

This is typically done through a **lessons learned meeting**, also known as a post-mortem.

- **Lessons learned meeting:** A meeting that includes all involved parties after a major incident.

The meeting may be scheduled no later than two weeks after remediation.

Not all incidents require a dedicated meeting. Major incidents, such as ransomware attacks, should be reviewed.

Questions addressed may include:

- What happened?
- What time did it happen?
- Who discovered it?
- How did it get contained?
- What actions were taken for recovery?
- What could have been done differently?

For large organizations, these meetings help departments share information and recommendations for future prevention.

**Pro tip:** Organizers should prepare an agenda in advance and assign roles such as:

- Moderator
- Scribe

### Recommendations

Lessons learned meetings should produce a list of prioritized actions or actionable recommendations to improve incident handling and overall security posture.

Examples of changes:

- Updating playbook instructions
- Implementing new security tools and technologies

### Final Report

At minimum, incident response documentation should describe the incident by covering the 5 W’s:

- Who
- What
- Where
- Why
- When

A **final report** provides a comprehensive review of an incident.

- **Final report:** Documentation that provides a comprehensive review of an incident.

Final reports are not standardized and can vary across organizations.

Common elements of a final report include:

#### Executive Summary

A high-level summary of the report with key findings and essential facts.

#### Timeline

A chronological timeline of the incident with timestamps.

#### Investigation

A compilation of actions taken during detection and analysis.

#### Recommendations

A list of suggested actions for future prevention.

**Pro tip:** Consider the audience when writing the final report, especially if business executives or non-security professionals will read it.

### Key Takeaways

- Post-incident activity closes the incident response lifecycle.
- Lessons learned meetings help teams improve and prevent repeat incidents.
- Final reports document the full incident and support future improvement.

---

## Terms and Definitions — Course 6, Module 3

| Term | Definition |
|---|---|
| Analysis | The investigation and validation of alerts |
| Broken chain of custody | Inconsistencies in the collection and logging of evidence in the chain of custody |
| Business continuity plan (BCP) | A document that outlines the procedures to sustain business operations during and after a significant disruption |
| Chain of custody | The process of documenting evidence possession and control during an incident lifecycle |
| Containment | The act of limiting and preventing additional damage caused by an incident |
| Crowdsourcing | The practice of gathering information using public input and collaboration |
| Detection | The prompt discovery of security events |
| Documentation | Any form of recorded content that is used for a specific purpose |
| Eradication | The complete removal of the incident elements from all affected systems |
| Final report | Documentation that provides a comprehensive review of an incident |
| Honeypot | A system or resource created as a decoy vulnerable to attacks with the purpose of attracting potential intruders |
| Incident response plan | A document that outlines the procedures to take in each step of incident response |
| Indicators of attack (IoA) | The series of observed events that indicate a real-time incident |
| Indicators of compromise (IoC) | Observable evidence that suggests signs of a potential security incident |
| Intrusion detection system (IDS) | An application that monitors system activity and alerts on possible intrusions |
| Lessons learned meeting | A meeting that includes all involved parties after a major incident |
| Open-source intelligence (OSINT) | The collection and analysis of information from publicly available sources to generate usable intelligence |
| Playbook | A manual that provides details about any operational action |
| Post-incident activity | The process of reviewing an incident to identify areas for improvement during incident handling |
| Recovery | The process of returning affected systems back to normal operations |
| Resilience | The ability to prepare for, respond to, and recover from disruptions |
| Standards | References that inform how to set policies |
| Threat hunting | The proactive search for threats on a network |
| Threat intelligence | Evidence-based threat information that provides context about existing or emerging threats |
| Triage | The prioritizing of incidents according to their level of importance or urgency |
| VirusTotal | A service that allows anyone to analyze suspicious files, domains, URLs, and IP addresses for malicious content |
