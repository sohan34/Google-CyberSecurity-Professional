# Course 6 — Module 1

## Table of Contents

- [Incident Response Teams](#incident-response-teams)
- [Detection Tools](#detection-tools)
- [SIEM Tools and the SIEM Process](#siem-tools-and-the-siem-process)
- [Terms and Definitions](#terms-and-definitions-course-6-module-1)

---

## Incident Response Teams

The National Institute of Standards and Technology (NIST) Incident Response Lifecycle has four phases:

- Preparation
- Detection and Analysis
- Containment, Eradication, and Recovery
- Post-incident activity

As a security professional, you will work with others to monitor, detect, and respond to incidents. Understanding the structure of incident response teams helps you collaborate effectively and respond efficiently.

### Command, Control, and Communication

A computer security incident response team (CSIRT) is a specialized group of security professionals trained in incident management and response.

For incident response to be effective, there must be clear:

- Command: leadership and direction
- Control: management of technical aspects, resources, and tasks
- Communication: keeping stakeholders informed

Clear roles and structure help make response efforts more effective.

### Roles in CSIRTs

CSIRTs vary by organization. They may exist as:

- A dedicated team
- A task force that meets when needed

CSIRTs include both security and nonsecurity professionals. Nonsecurity professionals may come from:

- Human resources
- Public relations
- Management
- IT
- Legal

Common security roles in a CSIRT include:

- Security analyst
- Technical lead
- Incident coordinator

#### Security Analyst

The security analyst continuously monitors the environment for threats. Duties include:

- Analyzing and triaging alerts
- Performing root-cause investigations
- Escalating or resolving alerts

If a critical threat is identified, the analyst escalates it to the proper lead.

#### Technical Lead

The technical lead manages technical aspects of the incident response process, such as applying patches or updates. Responsibilities include:

- Determining root cause
- Creating containment, eradication, and recovery strategies
- Coordinating with other teams to align incident response with business goals

#### Incident Coordinator

The incident coordinator works with relevant departments during an incident to maintain clear communication and awareness of incident status.

This role may also appear in other teams, including the SOC.

#### Other Roles

Other CSIRT roles may include:

- Communications lead
- Legal lead
- Planning lead

**Note:** Job titles can differ by organization. Incident coordinator may also be called incident commander or incident manager.

### Security Operations Center

A security operations center (SOC) is an organizational unit dedicated to monitoring networks, systems, and devices for security threats or attacks.

A SOC may exist:

- As its own unit
- Within a CSIRT

A SOC is part of the **blue team**, which defends against security threats and attacks.

### SOC Organization

A SOC typically includes:

- SOC analysts
- SOC leads
- SOC managers

SOC analysts are grouped into three tiers.

#### Tier 1 SOC Analyst

Tier 1 analysts are the least experienced. They are responsible for:

- Monitoring, reviewing, and prioritizing alerts
- Creating and closing alerts using ticketing systems
- Escalating tickets to Tier 2 or Tier 3

#### Tier 2 SOC Analyst

Tier 2 analysts are more experienced and are responsible for:

- Receiving escalated tickets from Tier 1 and conducting deeper investigations
- Configuring and refining security tools
- Reporting to the SOC lead

#### Tier 3 SOC Lead

Tier 3 analysts are highly experienced and are responsible for:

- Managing team operations
- Performing advanced detection techniques such as malware and forensics analysis
- Reporting to the SOC manager

#### SOC Manager

The SOC manager is responsible for:

- Hiring, training, and evaluating team members
- Creating performance metrics
- Developing reports related to incidents, compliance, and auditing
- Communicating findings to stakeholders such as executive management

#### Other SOC Roles

Specialized SOC roles may include:

- **Forensic investigators:** Collect, preserve, and analyze digital evidence related to incidents
- **Threat hunters:** Detect, analyze, and defend against advanced threats using threat intelligence

**Note:** SOC structures also vary by organization.

### Key Takeaways

- CSIRTs and SOCs help organizations monitor, detect, and respond to incidents.
- Security and nonsecurity professionals often work together during incident response.
- Knowing roles and responsibilities helps security analysts collaborate effectively.

---

## Detection Tools

Detection tools help organizations become aware of suspicious activity on networks and systems.

They work like home security systems:

- Home security systems monitor homes for intrusion
- Cybersecurity detection tools monitor systems and networks for unauthorized activity

Once suspicious activity is detected, the tool triggers an alert so a security professional can investigate.

### Detection Tools Overview

| Capability | IDS | IPS | EDR |
|---|---:|---:|---:|
| Detects malicious activity | ✓ | ✓ | ✓ |
| Prevents intrusions | N/A | ✓ | ✓ |
| Logs activity | ✓ | ✓ | ✓ |
| Generates alerts | ✓ | ✓ | ✓ |
| Performs behavioral analysis | N/A | N/A | ✓ |

### IDS Tools

An intrusion detection system (IDS) monitors system activity and alerts on possible intrusions.

An IDS:

- Continuously monitors network events
- Detects potential malicious activity
- Generates alerts

An IDS does **not** stop the activity. Security professionals investigate and respond if necessary.

Example:

- An IDS may alert on a suspicious login from an unknown IP address at an unusual time.
- It will not block the login itself.

Examples of IDS tools:

- Zeek
- Suricata
- Snort
- Sagan

### Detection Categories

Four detection categories are important when reviewing IDS alerts:

- **True positive:** Correctly detects an attack
- **True negative:** No malicious activity exists and no alert is triggered
- **False positive:** Incorrectly identifies harmless activity as malicious
- **False negative:** Fails to detect malicious activity

False positives waste time. False negatives are dangerous because real attacks go unnoticed.

### IPS Tools

An intrusion prevention system (IPS) monitors system activity and takes action to stop intrusive activity.

An IPS:

- Detects and alerts on intrusions
- Prevents activity
- Minimizes the effect of the activity

Example:

- An IPS may alert and modify an access control list on a router to block traffic.

**Note:** Some IDS tools can also operate as IPS tools. Suricata, Snort, and Sagan may have both capabilities.

### EDR Tools

Endpoint detection and response (EDR) monitors an endpoint for malicious activity.

An endpoint is any device connected to a network, such as:

- Computers
- Phones
- Tablets

EDR tools:

- Monitor endpoint activity
- Record activity
- Analyze activity
- Identify suspicious behavior
- Alert and respond to suspicious activity

Unlike IDS or IPS tools, EDR performs behavioral analysis using machine learning and artificial intelligence to detect malicious or unusual activity.

EDR tools also use automation to stop attacks without manual intervention.

Example:

- If an EDR detects an unusual process on a workstation, it can automatically block the process.

Examples of EDR tools:

- Open EDR
- Bitdefender Endpoint Detection and Response
- FortiEDR

**Note:** SIEM tools also have detection capabilities.

### Key Takeaways

- Detection tools help organizations understand what is happening in their environments.
- IDS, IPS, and EDR are different types of detection tools.
- Their value is in detecting, logging, alerting, and stopping malicious activity.

---

## SIEM Tools and the SIEM Process

A security information and event management (SIEM) tool collects and analyzes log data to monitor critical activities in an organization.

SIEM tools help analysts perform **log analysis**, which is the process of examining logs to identify events of interest.

### SIEM Advantages

SIEM tools collect and manage security-relevant data used during investigations.

Advantages include:

- **Access to event data:** Provides access to real-time and historical event data
- **Monitoring, detecting, and alerting:** Monitors systems and applies detection rules to generate alerts
- **Log storage:** Stores historical data for retention based on organizational requirements

### The SIEM Process

The SIEM process has three steps:

1. Collect and aggregate data
2. Normalize data
3. Analyze data

### Collect and Aggregate Data

SIEM tools collect event data from sources such as:

- Firewalls
- Servers
- Routers
- Other systems

This data, also known as logs, contains details such as timestamps and IP addresses.

**Log:** A record of events that occur within an organization’s systems.

After collection, logs are aggregated into one central location.

**Aggregation:** The process of consolidating log data into a centralized place.

Parsing may happen during collection.

**Parsing:** Mapping data according to fields and corresponding values.

Example log:

```text
April 3 11:01:21 server sshd[1088]: Failed password for user nuhara from 218.124.14.105 port 5023
```
Parsed fields may include:

host = server
process = sshd
source_user = nuhara
source_ip = 218.124.14.105
source_port = 5023
Normalize Data

Collected event data must be transformed into a single format so it can be easily processed by the SIEM.

Normalization: Converts data into a standard, structured format that is easily searchable.

Analyze Data

After logs are collected, aggregated, and normalized, the SIEM analyzes them using detection logic such as rules and conditions.

If activity matches a rule, alerts are sent to cybersecurity teams.

Correlation: Comparing multiple log events to identify common patterns that indicate potential security threats.

SIEM Tools

Common SIEM tools include:

AlienVault OSSIM
Chronicle
Elastic
Exabeam
IBM QRadar Security Intelligence Platform
LogRhythm
Splunk
Key Takeaways
SIEM tools collect and organize data into useful insights.
The SIEM process includes collection, normalization, and analysis.
SIEM tools help teams identify threats and respond to incidents more effectively.

| Term                                             | Definition                                                                                                                              |
| ------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------- |
| Aggregation                                      | The process of consolidating log data into a centralized place                                                                          |
| Alert                                            | A notification that something suspicious or unusual has been detected                                                                   |
| Analysis                                         | The process of examining logs or data to identify events of interest                                                                    |
| Behavioral analysis                              | The process of using machine learning and artificial intelligence to analyze system behavior and identify malicious or unusual activity |
| Blue team                                        | Security professionals responsible for defending against security threats and attacks                                                   |
| Computer security incident response team (CSIRT) | A specialized group of security professionals trained in incident management and response                                               |
| Correlation                                      | The comparison of multiple log events to identify common patterns that indicate potential security threats                              |
| Detection                                        | The act of identifying suspicious or malicious activity                                                                                 |
| Endpoint                                         | Any device connected to a network                                                                                                       |
| Endpoint detection and response (EDR)            | An application that monitors an endpoint for malicious activity                                                                         |
| Incident coordinator                             | The person who coordinates with relevant departments during a security incident                                                         |
| Incident response                                | The process of detecting, analyzing, containing, eradicating, and recovering from security incidents                                    |
| Intrusion detection system (IDS)                 | An application that monitors system activity and alerts on possible intrusions                                                          |
| Intrusion prevention system (IPS)                | An application that monitors system activity for intrusive activity and takes action to stop the activity                               |
| Log                                              | A record of events that occur within an organization’s systems                                                                          |
| Log analysis                                     | The process of examining logs to identify events of interest                                                                            |
| Normalization                                    | The process of converting data into a standard, structured format that is easily searchable                                             |
| Security information and event management (SIEM) | An application that collects and analyzes log data to monitor critical activities in an organization                                    |
| Security analyst                                 | The person who continuously monitors an environment for security threats                                                                |
| Security operations center (SOC)                 | An organizational unit dedicated to monitoring networks, systems, and devices for security threats or attacks                           |
| Technical lead                                   | The person who manages technical aspects of the incident response process                                                               |
| Threat hunter                                    | A security professional who detects, analyzes, and defends against new and advanced cybersecurity threats using threat intelligence     |
| Ticketing system                                 | A system used to create, track, and manage alerts or requests                                                                           |
| Tier 1 SOC analyst                               | The least experienced SOC analyst who monitors, reviews, and prioritizes alerts                                                         |
| Tier 2 SOC analyst                               | The more experienced SOC analyst who conducts deeper investigations and refines tools                                                   |
| Tier 3 SOC lead                                  | The highly experienced SOC professional who manages team operations and advanced detection                                              |
| True negative                                    | A state where no malicious activity exists and no alert is triggered                                                                    |
| True positive                                    | An alert that correctly detects the presence of an attack                                                                               |
| False negative                                   | A state where a threat is present but not detected                                                                                      |
| False positive                                   | An alert that incorrectly detects the presence of a threat                                                                              |
| Triaging                                         | The process of reviewing and prioritizing alerts based on severity or criticality                                                       |
