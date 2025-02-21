
# Incident Management Lab (Incident Response & Threat Intelligence)

## 1. Project Overview

### **Objective**
This project aims to build a prototype **Security Operations Center (SOC) platform** for **Catni Games International** to secure its multiplayer gaming infrastructure. The focus is on **incident management, threat intelligence sharing, and automated response workflows**.

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


### **MISP**

### **Cortex**

---

## 6. Integration Instructions
### Step 1: TheHive ↔ MISP

---

## 7. Incident Simulation & Response Workflow

### **Scenario: Failed Login Attempt Detection**
To test the SOC platform, we will simulate a **brute-force attack** scenario.

#### **Step 1: Simulate Brute Force Attack**




---

## 8. Challenges & Resolutions

| Challenge | Resolution |
|-----------|------------|
| **Issue #1:** Delay in TheHive-MISP API authentication. | Adjusted API key validation method. |
| **Issue #2:** Threat intelligence feed latency >5 minutes. | Exploring alternative MISP feeds. |
| **Issue #3:** Cortex analyzer execution time variability. | Optimizing integration and reducing redundant queries. |

---

## 9. Documentation & Updates
All setup guides, configuration steps, and troubleshooting logs will be documented in this repository. Future updates and lessons learned will be added as the project progresses.

> **Note:** This project is an internal prototype and is currently **not open for external collaboration**.


---
# incident-management-team-02
