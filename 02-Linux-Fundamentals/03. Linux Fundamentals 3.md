# 🐧 Linux Fundamentals 3  

This room builds on Linux Fundamentals Part 1 & 2 and dives deeper into **real-world Linux usage**. It focuses on editing files efficiently, managing processes, automating tasks, handling packages, and analysing system logs — all essential skills for cybersecurity and system administration.

---

## 🎯 Learning Objectives

By completing this room, you will be able to:

- Use terminal-based text editors effectively
- Transfer and serve files between systems
- Understand and manage Linux processes
- Automate tasks using cron jobs
- Manage software using package repositories
- Analyse system and application logs

---

## 🧠 Core Concepts Covered

- Terminal text editors (Nano & VIM)
- File transfers (wget, scp)
- Lightweight web servers (Python HTTPServer)
- Process management (ps, top, kill)
- Services and startup processes (systemctl)
- Backgrounding & foregrounding jobs
- Task automation using crontabs
- Package management using apt
- System and application logging

---

### 📝 Task 3: Terminal Text Editors

#### Nano
Nano is a beginner-friendly terminal text editor.

```
nano filename
```

Key features:

- Simple interface
- Easy shortcuts (Ctrl + X to exit)
- Search, copy/paste, line navigation

#### VIM

A powerful and advanced editor with:

- Extensive customisation
- Syntax highlighting
- Availability on almost all systems

**📌 Flag** - `THM{TEXT_EDITORS}`

![flag](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M2/m2.16.png)

---

### 🔧 Task 4: General / Useful Utilities
**Downloading Files (wget)**
```
wget https://example.com/file.txt
```
**Secure File Transfer (scp)**

Local → Remote:
```
scp important.txt ubuntu@192.168.1.30:/home/ubuntu/transferred.txt
```

Remote → Local:
```
scp ubuntu@192.168.1.30:/home/ubuntu/documents.txt notes.txt
```

**Serving Files (Python HTTP Server)**
```
python3 -m http.server
```

Download using:
```
wget http://IP_ADDRESS:8000/filename
```

**📌 Flag** - `THM{WGET_WEBSERVER}`

![flag1](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M2/m2.17.png)

![flag2](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M2/m2.18.png)

---

### ⚙️ Task 5: Processes 101
**Viewing Processes**
```
ps
ps aux
top
```

![ps](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M2/m2.19.png)

**Managing Processes**
```
kill PID
```

Common signals:

- `SIGTERM` – clean termination
- `SIGKILL` – force kill
- `SIGSTOP` – suspend process

**Services (systemctl)**
```
systemctl start service
systemctl stop service
systemctl enable service
systemctl disable service
```

**Background & Foreground**
```
command &
Ctrl + Z
fg
```

**📌 Flags & Answers**

- New PID after 300 → `301`
- Clean kill → `SIGTERM`
- Process flag → `THM{PROCESSES}`
- Stop service → `systemctl stop myservice`
- Start on boot → `systemctl enable myservice`
- Foreground → `fg`

---

### ⏱️ Task 6: Automation with Cron

Cron allows scheduling tasks automatically.

Crontab format:
```
MIN HOUR DOM MON DOW CMD
```

Example:
```
0 */12 * * * cp -R /home/cmnatic/Documents /var/backups/
```

Edit crontab:
```
crontab -e
```

**📌 Answer**

Cron runs at → `@reboot`

![cron](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M2/m2.20.png)

---

### 📦 Task 7: Package Management
**APT & Repositories**

- Ubuntu uses apt for package management
- Supports official and third-party repositories

**Adding a Repository (Example)**
```
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
```
```
apt update
apt install sublime-text
```

Remove:
```
apt remove sublime-text
```

---

### 📊 Task 8: System Logs

Logs are stored in:
```
/var/log
```

Common logs:

- Web server access & error logs
- Authentication logs
- Firewall logs

**📌 Answers**

- IP Address → `10.9.232.111`
- File accessed → `catsanddogs.jpg`

![logs](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M2/m2.21.png)

![logs](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M2/m2.23.png)

---

## 🛠️ Commands & Tools Summary
```
nano, vim
wget, scp
python3 -m http.server
ps, top, kill
systemctl
cron, crontab
apt
Log analysis via /var/log
```

---

## 📝 Key Takeaways

- Terminal text editors are essential for Linux efficiency
- File transfers and hosting are common in pentesting
- Process visibility helps detect malicious activity
- Automation saves time and improves system reliability
- Package management ensures secure software updates
- Logs are critical for incident detection and forensics

---

### 🏁 Final Summary

Linux Fundamentals 3 completes the Linux basics trilogy by exposing you to real operational workflows. These skills directly map to roles such as SOC Analyst, System Administrator, DevOps Engineer, and Penetration Tester.

Linux mastery is non-negotiable 🛡️🐧

![linux3](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M2/Linux3.png)
