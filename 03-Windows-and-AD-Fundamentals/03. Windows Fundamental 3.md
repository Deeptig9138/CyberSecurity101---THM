# 🪟 Windows Fundamentals 3
This room continues the Windows Fundamentals journey by focusing on **built-in Windows security features**. We explore how Microsoft protects devices using updates, antivirus, firewall profiles, disk encryption, hardware-based security, and backup mechanisms.

This module builds on:

- **Windows Fundamentals 1** – Desktop, File System, UAC, Control Panel, Task Manager  
- **Windows Fundamentals 2** – System utilities like MSConfig, Computer Management, Resource Monitor, and more  

The attached VM used in this room runs **Windows Server 2019**.

---

## 🎯 Learning Objectives
By completing this room, you will be able to:

- Understand how **Windows Update** works
- Navigate **Windows Security**
- Configure **Virus & Threat Protection**
- Understand **Firewall profiles**
- Learn about **Microsoft Defender SmartScreen**
- Identify hardware-based security features like **TPM**
- Understand **BitLocker Drive Encryption**
- Explain the purpose of **Volume Shadow Copy Service (VSS)**

---

## 🧠 Core Concepts Covered
- Patch management (Patch Tuesday)
- Built-in antivirus protection
- Firewall profiles (Domain, Private, Public)
- Browser & exploit protection
- TPM & hardware-backed security
- Disk encryption
- System restore & shadow copies
- Living Off The Land (LOLBins concept)

---

## 🧭 Task 2: Windows Update

**Windows Update** is a service provided by Microsoft to deliver:

- Security patches  
- Feature updates  
- Bug fixes  
- Definition updates (e.g., Microsoft Defender)  

Updates are typically released on the **second Tuesday of each month**, known as **Patch Tuesday**.

Updates can be accessed via:

- **Settings → Update & Security**
- Run dialog: `control /name Microsoft.WindowsUpdate`


### Important Notes (VM Context)

- Updates are *managed* (typical in enterprise environments)
- The VM has no internet access
- No new updates are available

Modern Windows versions (especially Windows 10+) do not allow users to permanently ignore updates — only postpone them.

### ✅ Answer
- **There were two definition updates installed in the attached VM. On what date were these updates installed?:** `5/3/2021`

---

## 🧭 Task 3: Windows Security

According to Microsoft:

> “Windows Security is your home to manage the tools that protect your device and your data.”

Accessible via:
- **Settings → Update & Security → Windows Security**

### 🔒 Protection Areas

- **Virus & threat protection**
- **Firewall & network protection**
- **App & browser control**
- **Device security**

### Status Indicators

- 🟢 Green → Protected
- 🟡 Yellow → Recommendation available
- 🔴 Red → Immediate action required

### ✅ Answer
- **Area needing immediate attention:** `Virus & threat protection`

![virus&threat](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M3/3.10.png)

---

## 🧭 Task 4: Virus & Threat Protection

This section is divided into:

### 1️⃣ Current Threats

Scan Options:
- Quick scan
- Full scan
- Custom scan

Threat History:
- Last scan
- Quarantined threats
- Allowed threats

⚠️ Only allow threats if you are 100% certain.

### 2️⃣ Virus & Threat Protection Settings

Key features:

- **Real-time protection**
- Cloud-delivered protection
- Automatic sample submission
- Controlled folder access (Ransomware protection)
- Exclusions
- Notifications

In the attached VM:
- Real-time protection is intentionally disabled (safe in this lab environment)

### ✅ Answer
- **Turned off feature:** `Real-time protection`

---

## 🧭 Task 5: Firewall & Network Protection

A firewall controls traffic entering and leaving a system via ports.

Microsoft defines three firewall profiles:

### 🔹 Domain
Used when connected to a domain controller.

### 🔹 Private
Used for trusted networks (home/work).

### 🔹 Public
Used for untrusted networks (coffee shops, airports).

Command to open firewall settings: `WF.msc`

![firewall](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M3/3.11.png)

⚠️ It is strongly recommended to keep the firewall enabled.

### ✅ Answer
- **Airport Wi-Fi profile:** `Public network`

---

## 🧭 Task 6: App & Browser Control

This section manages **Microsoft Defender SmartScreen**.

SmartScreen protects against:

- Phishing websites
- Malicious downloads
- Unrecognized applications

Settings options:
- Warn
- Block
- Off (not recommended)

### Exploit Protection
Built-in Windows feature that helps mitigate exploit-based attacks.

⚠️ Leave default settings unless fully confident.

---

## 🧭 Task 7: Device Security

This section includes hardware-based protections.

### 🔐 Core Isolation
- **Memory Integrity**
  - Prevents malicious code injection into high-security processes.

### 🔐 Security Processor (TPM)

**TPM (Trusted Platform Module)** is a hardware chip that:

- Performs cryptographic operations
- Protects sensitive data
- Ensures system integrity
- Prevents tampering

### ✅ Answer
- **TPM stands for:** `Trusted Platform Module`

---

## 🧭 Task 8: BitLocker

**BitLocker Drive Encryption** protects data from:

- Lost devices
- Stolen systems
- Offline attacks

Best used with TPM version 1.2 or later.

If TPM is not available, BitLocker can use a **removable USB drive**.

### ✅ Answer
- **Removable drive contains:** `Startup key`

---

## 🧭 Task 9: Volume Shadow Copy Service (VSS)

**Volume Shadow Copy Service (VSS)** creates consistent snapshots of data for backup purposes.

Shadow copies are stored in: `System Volume Information`


If System Protection is enabled, you can:

- Create restore points
- Perform system restore
- Configure restore settings
- Delete restore points

⚠️ Malware often deletes shadow copies to prevent ransomware recovery.

### ✅ Answer
- **VSS stands for:** `Volume Shadow Copy Service`

---

## 🏁 Task 10: Conclusion

This room covered key Windows security components:

- Windows Update
- Microsoft Defender
- Firewall profiles
- SmartScreen
- TPM
- BitLocker
- VSS

These tools are built into Windows to provide layered defense.

However, attackers often abuse legitimate Windows tools to avoid detection — a technique known as **Living Off The Land (LOLBins)**.

Security professionals must understand both:
- How these tools protect systems  
- How attackers misuse them  

---

## 📝 Key Takeaways

- Windows uses layered security
- Updates are critical (Patch Tuesday)
- Real-time protection should always be enabled in production systems
- Firewall profile selection matters
- TPM enhances encryption security
- BitLocker protects against physical theft
- VSS assists with recovery but can be targeted by malware

---

## 🚀 Further Reading

To deepen your knowledge:

- Antimalware Scan Interface (AMSI)
- Credential Guard
- Windows Hello
- Windows 10 Security Features
- LOLBAS Project (Living Off The Land Binaries)

---

📌 *Understanding Windows security is essential for SOC analysts, blue teamers, and system administrators.*  
Mastering these fundamentals builds a strong defensive foundation.

![windows3](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M3/Windows3.png)
