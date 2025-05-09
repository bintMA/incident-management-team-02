
# Incident Management Lab (Incident Response & Threat Intelligence)

## 1. Project Overview

### **Objective**
This project aims to build a prototype **Security Operations Center (SOC) platform** for **Catnip Games International** to secure its multiplayer gaming infrastructure. The focus is on **incident management, threat intelligence sharing, and automated response workflows**.

### **Context**
Catnip Games International is preparing for its first major multiplayer game launch. The company's **300 Linux servers across two data centers** handle **sensitive player data, matchmaking services, and game hosting**. Security issues identified during beta testing include:
- **Undetected bot attacks** exploiting game mechanics.
- **Delayed response to account compromises**.
- **Lack of standardized incident response procedures**.
- **Inefficient threat intelligence sharing between teams**.

### **Goals**

This project addresses these gaps by implementing an **incident management platform** using TheHive, MISP, and Cortex.

---
## 2. Technology Stack

| Tool         | Purpose                               |
|-------------|--------------------------------------|
| **TheHive**  | Case management & alert triage     |
| **MISP**     | Threat intelligence sharing        |
| **Cortex**   | Automated analysis                 |
| **Elasticsearch** | Log storage & querying       |
| **Python**   | Custom integrations & automation  |
| **Git**      | Version control & collaboration   |

--- 

## 3. Functional & Non-Functional Requirements

### **Functional Requirements**
1. **Prototype SOC Implementation**
   - Deploy integrated incident management platform.
   - Configure **threat intelligence sharing** via MISP.
   - Implement **automated response workflows** using Cortex.
   - Establish **incident tracking system** with TheHive.
   - Develop response playbooks for handling security incidents.
   - Set up **reporting mechanisms** for security operations.

### **Non-Functional Requirements**
#### **Performance**
- 15-minute maximum alert triage time.
- <5-minute threat intelligence sharing latency.
- Support for 100 concurrent incidents.
- Handle 1000 alerts per day.

#### **Reliability**
- 24/7 operational availability.
- No single point of failure.
- Automated backup system.
- Data retention compliance.

#### **Operations Management**
- Clear escalation procedures.
- Documented response workflows.
- KPI tracking capabilities.
- Team collaboration tools.


---

## 4. Architecture Overview

### **High-Level Architecture**

---

---

## 5. VM Setup Instructions

### **TheHive**
[Please find TheHive Installation here](https://github.com/bintMA/incident-management-team-02/blob/main/Procedures/2025-02-28-installing-thehive-on-centos-7.md)

### **MISP**
[Please find MISP Installation here](https://github.com/bintMA/incident-management-team-02/blob/main/Procedures/2025-02-21-install-misp-on-ubuntu22.4.md)

### **Cortex**
[Please find Cortex Installation here](https://github.com/bintMA/incident-management-team-02/blob/main/Procedures/2025-02-15-installing-cortex-on-ubuntu22.4.md)

---

## 6. Integration Instructions
[Please find Integration Instruction here](https://github.com/bintMA/incident-management-team-02/blob/main/Procedures/2025-02-15-integrating-cortex-misp-thehive.md)

---

## 7. Sample Playbook

### **Scenario: Account Takeover via Credential Stuffing**
A sudden increase in failed login attempts was detected on Catnip Games International’s multiplayer platform. TheHive flagged repeated failed logins originating from multiple IPs in a short period, indicating a credential-stuffing attack. 

### PREPARATION

- Ensure AntiVirus and TheHive systems are active and centrally monitored.
- Confirm team access to TheHive, MISP, Cortex, and sandboxing tools.
- Maintain secure, tested backup procedures.
- Integrate MISP feeds and regularly update IOCs.

### DETECTION AND ANALYSIS

#### Indicators:

- Alert from The Hive indicating mass encryption or ransomware activity.
- Suspicious user reports (e.g., file not opening, system slowness).
- VirusTotal detection from hash submissions.

#### Initial Triage:

- SOC Analyst creates a case in TheHive using structured templates.
- Classify the incident severity and identify scope (number of endpoints/users affected).

#### IoC Analysis:

- Use Cortex analysers (e.g., Abuseipdb, VirusTotal) to analyze suspicious files or URLs.
- Threat indicators submitted to MISP to correlate with known malware campaigns.

#### Artifact Collection:

- Endpoint logs, binaries, process lists, network traffic (PCAPs), and registry data gathered and attached to the case in TheHive.

### CONTAINMENT, ERADICATION, AND RECOVERY

#### Containment:

- IT isolates affected systems (e.g., via EDR network quarantine).
- User credentials are disabled if compromise is suspected.

#### Eradication:

- Malicious files removed using AntiVirus/EDR.
- Cortex responders used to automatically contain or disable persistence mechanisms.
- All artifacts analysed to understand infection vectors and identify backdoors.

#### Recovery:

- Systems are restored from clean backups or rebuilt.
- Systems patched and monitored for reinfection signs.
- Affected credentials reset.

### BACKUP EVIDENCE

- Store evidence (logs, files, memory dumps) in secure, time-stamped directories.
- Ensure metadata and access logs are intact.
- All response actions documented in TheHive, including timeline, artifacts, tags, and analyst notes.

### POST-INCIDENT ACTIVITY

#### Lessons Learned:

- The malware family or variant that was found.
- Infection vector and user behaviour involved.
- The success of automated responders (Cortex).
- Recommendations to prevent future recurrence.

#### Evaluate:

- If earlier detection was possible.
- Identify gaps in containment or communication.
- Consult legal counsel regarding disclosure and reporting.
- Final incident report detailing detection, response, recovery, and improvements.
- Update IOC enrichment processes and detection rules in MISP and TheHive.
- Update playbook.

---

## 8. Challenges & Resolutions

| Challenge | Resolution |
|-----------|------------|
|  The Hive 5 license key  | Downgraded to TheHive version 4 |
| Elasticsearch Startup Failures – TheHive relies on Elasticsearch, but the service failed to start due to permission errors and incorrect configurations.  | Adjusted file permissions, modified the Elasticsearch configuration file, and ensured the service was set to start on boot. |
| Dependency Issues with Cortex Analyzers – Some Cortex analyzers failed to function due to missing Python dependencies.  | Installed required dependencies using both pip2 and pip3, ensuring compatibility.  |

---

## 9. Documentation & Updates
All setup guides, configuration steps, and troubleshooting logs will be documented in this repository. Future updates and lessons learned will be added as the project progresses.

> **Note:** This project is an internal prototype and is currently **not open for external collaboration**.


---
# incident-management-team-02
