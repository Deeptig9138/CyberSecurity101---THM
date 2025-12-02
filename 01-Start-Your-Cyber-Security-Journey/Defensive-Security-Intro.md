# Defensive Security Intro  
*Understanding how defenders protect systems, detect intrusions, and respond to cyber threats.*

---

## 🎯 Learning Objectives
- Understand the core purpose of defensive security  
- Learn what the Blue Team does  
- Explore SOC operations, threat intelligence, DFIR, and malware analysis  
- Understand the data protection lifecycle  
- Complete a SIEM simulation and retrieve the flag  

---

## 🛡️ What Is Defensive Security?

Defensive Security focuses on **detecting, preventing, and responding** to cyberattacks.

Key responsibilities include:

- **User Cyber Security Awareness**  
  Training users to identify phishing, scams, malicious links, and unsafe behavior.

- **Documenting & Managing Assets**  
  You can’t protect what you don’t know exists — proper inventory is crucial.

- **Patching & Updates**  
  Ensuring all systems are updated to prevent exploitation of known vulnerabilities.

- **Preventative Security Devices**  
  - **Firewalls:** Control inbound/outbound traffic.  
  - **IPS (Intrusion Prevention System):** Blocks malicious patterns using signatures and rules.

- **Logging & Monitoring**  
  Collecting logs and setting up monitoring tools to identify:  
  - Unauthorized devices  
  - Suspicious activities  
  - Failed logins  
  - Network anomalies

**Q: Which team focuses on defensive security?**  

**A: Blue Team**

---

# 🏢 Security Operations Center (SOC)

A SOC is a team of cybersecurity professionals who monitor, detect, and investigate malicious security events.

### SOC Analysts Handle:

#### **1. Vulnerabilities**
Updating systems, applying patches, and mitigating exploit risks.

#### **2. Policy Violations**
Example: Uploading sensitive company data to public storage.

#### **3. Unauthorized Activity**
Detecting stolen credentials, unusual access locations, abnormal login times, etc.

#### **4. Network Intrusions**
Even with strong security, intrusions can occur:
- Phishing emails  
- Public server exploits  
- Malware infections  

A SOC must detect and contain these quickly to minimize damage.

---

# 🔎 Threat Intelligence

**Threat Intelligence** = Information collected about attackers, their motives, and their techniques.

It answers:
- Who are the adversaries?  
- What techniques do they use?  
- What are they trying to achieve?  

Attackers may be:
- Nation-state groups  
- Ransomware gangs  
- Hacktivists  
- Insiders  

### Threat Intelligence Pipeline:

1. **Data Collection**  
   From logs, sensors, OSINT, malware databases, etc.

2. **Processing**  
   Converting raw data into usable formats.

3. **Analysis**  
   Identifying adversaries, predicting behavior, and producing actionable recommendations.

This leads to **Threat-Informed Defence**, allowing defenders to prepare for known tactics (MITRE ATT&CK, TTPs).

---

# 🔐 Data Protection Lifecycle

Understanding data flow helps protect user privacy and prevent data breaches.

### **1. Data Collection**
- Gather only necessary data  
- Always with user consent  

### **2. Data Storage**
- Databases, cloud storage  
- Use **encryption**, **ACLs**, **firewalls**

### **3. Data Transmission**
- Secure channels like **HTTPS, SSL/TLS**

### **4. Data Processing**
- Role-based access  
- Process only what is required  

### **5. Data Sharing**
- Must follow laws (GDPR, HIPAA, etc.)  
- Done only with trusted parties  

### **6. Data Retention & Deletion**
- Keep data only as long as required  
- Secure deletion (wiping, overwriting)

---

# 🔬 Digital Forensics & Incident Response (DFIR)

DFIR = Investigating cyber incidents + responding to minimize damage.

### **Digital Forensics Areas:**

- **File System Analysis**  
  Deleted files, installed software, user activity.

- **Memory Forensics**  
  Extract malware or attacker tools running in RAM.

- **System Logs**  
  Authentication logs, event logs, audit logs.

- **Network Logs**  
  Packet captures, IDS alerts, traffic patterns.

## 🧯 Incident Response Lifecycle

1. **Preparation**  
   Policies, playbooks, tools, training.

2. **Detection & Analysis**  
   Identify and verify security events.

3. **Containment, Eradication, Recovery**  
   Stop attack → remove threat → restore systems.

4. **Post-Incident Activity**  
   Document findings, improve defenses, share lessons.

![DFIR](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/dfir.png)

**Q: What does DFIR stand for?**  

**A: Digital Forensics and Incident Response**

---

# 👾 Malware Analysis

Malware = Malicious software. Types include:

### **1. Virus**
- Attaches to programs  
- Spreads by modifying or deleting files

### **2. Trojan Horse**
- Appears legitimate  
- Contains hidden malicious functionality  

### **3. Ransomware**
- Encrypts user files  
- Victim must pay ransom to regain access  

### Malware Analysis Methods:

#### **Static Analysis**
Inspecting malware *without running* it  
Requires assembly, reverse engineering skills

#### **Dynamic Analysis**
Running malware in a controlled sandbox  
Observe behavior, registry changes, traffic, processes

**Q: Which malware requires payment to restore access?**

**A: Ransomware**

---

# 🏦 SOC Scenario: Your First SIEM Analysis

You're a SOC analyst protecting a bank.  
Your SIEM collects logs and displays suspicious security events on a dashboard.

Examples of alerts:
- Multiple failed logins  
- Unknown IP addresses connecting  
- Unusual login location  
- Suspicious admin actions  

Not every alert is harmful — you must analyze and verify.

---

# 🖥️ SIEM Simulation Task

Follow the steps in the TryHackMe interactive simulation:

1. Open the "View Site" simulation  
2. Inspect logs and events  
3. Identify unauthorized access

![Logs](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/m1.4.png)

4. Note the suspicious IP
   
![Logs1](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/m1.5.png)
![Logs2](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/m1.6.png)

5. Report it to the SOC Lead

![Logs3](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/m1.7.png)

6. Block the IP

![Logs4](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/m1.8.png)

7. Retrieve the flag

![Logs5](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/m1.9.png)

**Final Question: What flag did you obtain?**

**A: THM{THREAT-BLOCKED}**

---

# 📝 Summary

- Defensive Security = Preventing, detecting & responding to attacks  
- Blue Team ≠ Red Team  
- SOC analysts monitor systems for threats  
- Threat intelligence helps predict attacker behavior  
- DFIR investigates incidents and restores systems  
- Malware analysis reveals how malicious programs work  
- SIEM tools centralize logs and alerts for quick analysis  

This room establishes foundational defensive security concepts that you'll build upon in SOC, SIEM, DFIR, and malware labs ahead.
