# 🪟 Windows Fundamentals 2

## 📘 Room Overview
This room continues the Windows Fundamentals journey by exploring **advanced system utilities**, **administrative tools**, and **power-user components** of the Windows operating system. It focuses on tools commonly used by system administrators, SOC analysts, and blue-teamers for troubleshooting, monitoring, and system analysis.

---

## 🎯 Learning Objectives
By completing this room, you will be able to:
- Understand and use **System Configuration (MSConfig)**
- Modify **User Account Control (UAC)** settings
- Navigate **Computer Management** utilities
- Analyze system details using **System Information**
- Monitor system performance via **Resource Monitor**
- Use essential **Command Prompt** commands
- Understand the purpose and risk of the **Windows Registry**

---

## 🧠 Core Concepts Covered
- Advanced Windows troubleshooting
- Startup and recovery configurations
- Windows administrative utilities
- System monitoring and diagnostics
- Command-line based system inspection
- Registry structure and risks

---

## 🧭 Task 1: Introduction
This room builds on **Windows Fundamentals 1**, extending into deeper administrative utilities like MSConfig, Computer Management, System Information, and more.

📌 The attached **Windows Server VM** is used for hands-on exploration.

---

## 🧭 Task 2: System Configuration & Advanced System Settings

### 🔧 System Configuration (MSConfig)
Used mainly for **startup troubleshooting** and system diagnostics.

**Tabs in MSConfig:**
1. General
2. Boot
3. Services
4. Startup
5. Tools

Key notes:
- Startup apps on **Windows Server** are handled differently
- Use `shell:startup` to view startup items
- The **Tools** tab provides shortcuts to multiple system utilities

### ⚙️ Advanced System Settings
Used to configure:
- Performance options
- Virtual memory (page file)
- Startup & Recovery
- Crash dump generation

### ✅ Answers
- **Service with Systems Internals as manufacturer:** `PsShutdown`
- **Windows license registered to:** `Windows User`
- **Windows Troubleshooting command:**  
  `C:\Windows\System32\control.exe /name Microsoft.Troubleshooting`
- **Control Panel executable:** `control.exe`

---

## 🧭 Task 3: Change UAC Settings

UAC helps prevent unauthorized system-level changes.

**UAC Levels:**
- Always notify
- Notify for apps (default)
- Notify without dimming
- Never notify (not recommended)

### ✅ Answer
- **Command to open UAC settings:** `UserAccountControlSettings.exe`

---

## 🧭 Task 4: Computer Management

Accessible via `compmgmt.msc`, this utility includes:

### 🛠 System Tools
- **Task Scheduler** – automate tasks
- **Event Viewer** – view system & security logs
- **Shared Folders** – manage network shares
- **Local Users & Groups** – user management
- **Performance Monitor** – system metrics
- **Device Manager** – hardware configuration

### 💽 Storage
- **Disk Management**
  - Create, extend, shrink partitions
  - Assign drive letters

### ⚙️ Services & Applications
- Manage background services
- Configure startup types (Automatic, Manual, Disabled)
- WMI Control for system management

### ✅ Answers
- **Command to open Computer Management:** `compmgmt.msc`
- **npcapwatchdog scheduled task runs:** `At system startup`
- **Hidden shared folder name:** `sh4r3dF0Ld3r`

---

## 🧭 Task 5: System Information

The **System Information** tool (`msinfo32`) provides a detailed overview of:
- Hardware Resources
- Components
- Software Environment
- Environment Variables
- Network configuration

### ✅ Answers
- **Command:** `msinfo32.exe`
- **System Name:** `THM-WINFUN2`
- **ComSpec value:** `%SystemRoot%\system32\cmd.exe`

---

## 🧭 Task 6: Resource Monitor

Resource Monitor (`resmon`) provides real-time insights into:
- CPU
- Memory
- Disk
- Network

Used mainly for **advanced performance troubleshooting**.

### ✅ Answer
- **Command:** `resmon.exe`

---

## 🧭 Task 7: Command Prompt

Important CMD commands covered:
- `hostname`
- `whoami`
- `ipconfig`
- `netstat`
- `net`
- `cls`

Help manuals:
- `command /?`
- `net help <subcommand>`

### ✅ Answers
- **Full command for IP configuration:**  
  `C:\Windows\System32\cmd.exe /k %windir%\system32\ipconfig.exe`
- **Detailed IP info command:** `ipconfig /all`

---

## 🧭 Task 8: Registry Editor

The **Windows Registry** is a hierarchical database storing configuration data for:
- Users
- Applications
- Hardware
- System settings

⚠️ **Warning:** Editing the registry can break the OS if done incorrectly.

### ✅ Answer
- **Registry Editor command:** `regedt32.exe`

---

## 🏁 Task 9: Conclusion

This room introduced several **advanced Windows utilities** commonly used by:
- System Administrators
- SOC Analysts
- Blue Team professionals

Most tools explored here can be launched **directly** via:
- Start Menu
- Run dialog
- Command Prompt

No need to rely only on MSConfig 😄

---

## 📝 Key Takeaways
- Windows has powerful built-in admin tools
- Many utilities work behind the scenes
- Knowing commands = speed + confidence
- These tools are critical for real-world troubleshooting and security analysis

---

## 🚀 What’s Next?
Upcoming rooms will dive deeper into:
- Windows Internals
- Event Logs
- Security tools
- PowerShell
- Defensive monitoring

---

📌 *Hands-on Windows knowledge > mugging theory.*  
This room adds serious weight to any **blue team / SOC / sysadmin** learning path.
