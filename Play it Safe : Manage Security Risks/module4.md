# Course 2 - Module 4: Playbooks & Incident Response

## Playbook Overview
A **playbook** is a documented guide that provides predefined steps for responding to security incidents.

### Purpose
- Standardizes incident response
- Ensures consistency across analysts
- Defines responsibilities and workflow
- Helps meet legal and compliance requirements
- Minimizes errors during incidents

### Playbook Components
- **Strategy:** Defines roles, responsibilities, and expectations
- **Plan:** Specifies the exact steps to complete the task

### Living Documents
Playbooks are continuously updated when:
- Failures or gaps are identified
- Laws or compliance standards change
- New threats and attack techniques emerge

---

# Types of Playbooks

Organizations create playbooks for different situations, including:

- Ransomware attacks
- Phishing and Vishing
- Business Email Compromise (BEC)
- Malware incidents
- Vulnerability response
- Incident response

The exact content varies by:
- Organization
- Country regulations
- Industry requirements
- Compliance obligations

---

# Incident & Vulnerability Response Playbooks

These are the most commonly used playbooks by security analysts.

They are based on the organization's **Business Continuity Plan (BCP)**, ensuring business operations continue after security incidents.

### Benefits
- Provides predefined response procedures
- Ensures legal and organizational compliance
- Reduces human error
- Improves response speed
- Preserves forensic evidence

> **Risk = Likelihood × Impact**

Because incidents can quickly damage organizational assets, following the playbook immediately is essential.

---

# Common Incident Response Steps

1. Preparation
2. Detection
3. Analysis
4. Containment
5. Eradication
6. Recovery
7. Post-Incident Review (Lessons Learned)
8. Coordination & Communication

---

# Business Continuity Plan (BCP)

A **Business Continuity Plan (BCP)** defines how an organization continues operating after disruptions such as cyberattacks or system failures.

Playbooks help execute the BCP efficiently.

---

# Playbooks with SIEM

SIEM tools detect suspicious activity by analyzing logs.

When a SIEM generates an alert:
1. SIEM detects suspicious behavior.
2. Analyst follows the relevant playbook.
3. Investigation and response begin using standardized procedures.

### Example
- SIEM detects unusual login attempts.
- Analyst follows the Unauthorized Login playbook.
- Actions may include verifying the user, reviewing logs, isolating affected systems, and documenting findings.

---

# Playbooks with SOAR

**SOAR (Security Orchestration, Automation, and Response)** automates repetitive security tasks.

### SIEM vs SOAR

| SIEM | SOAR |
|------|------|
| Detects and analyzes threats | Automates responses |
| Generates alerts | Executes automated actions |
| Requires analyst investigation | Reduces manual work |

### Example
A user enters the wrong password multiple times.

SOAR automatically:
- Locks the account
- Creates an alert
- Notifies analysts

The analyst then follows the appropriate playbook to investigate and resolve the incident.

---

# Runbooks vs Playbooks

- **Playbook:** Overall incident response guide with decision-making and procedures.
- **Runbook:** Detailed instructions for performing a specific technical task.

Many organizations use both terms interchangeably.

---

# Key Takeaways

- Playbooks provide standardized incident response procedures.
- They define **who does what, when, and how**.
- They improve consistency, compliance, and forensic integrity.
- Playbooks are regularly updated as threats and regulations evolve.
- SIEM detects incidents; playbooks guide analysts' response.
- SOAR automates repetitive actions, allowing analysts to focus on complex investigations.

---

# Important Terms

| Term | Definition |
|------|------------|
| **Playbook** | Documented incident response procedures |
| **Business Continuity Plan (BCP)** | Plan to keep business operational after disruptions |
| **SIEM** | Collects and analyzes security logs to detect threats |
| **SOAR** | Automates security response workflows |
| **Runbook** | Detailed instructions for a specific operational task |
| **Incident Response** | Identifying, containing, eradicating, and recovering from security incidents |
| **Containment** | Limiting the spread of an attack |
| **Eradication** | Removing the root cause of an incident |
| **Recovery** | Restoring systems to normal operation |
| **Post-Incident Review** | Lessons learned and process improvement after an incident |

---

# Quick Revision

- **Playbook = Step-by-step response guide**
- **BCP = Business recovery plan**
- **SIEM = Detects & alerts**
- **SOAR = Automates response**
- **Runbook = Task-specific instructions**
- **Incident Response Flow:** Preparation → Detection → Analysis → Containment → Eradication → Recovery → Lessons Learned
