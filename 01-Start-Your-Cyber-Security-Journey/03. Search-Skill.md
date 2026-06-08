# 🔍 Search Skills 

We live in a world flooded with information. As cybersecurity learners and professionals, our job is not just to consume information—but to find, evaluate, filter, and validate it. This room teaches the essential search skills required to navigate the modern infoscape effectively.

---

## 🎯 Learning Objectives

By the end of this room, you will learn to:

- Evaluate information sources  
- Use search engines efficiently  
- Explore specialized search engines  
- Read technical documentation  
- Make use of social media  
- Check and follow reliable news outlets  

---

# 🧭 Task-by-Task Walkthrough

## 📝 **Task 2 — Evaluation of Search Results**

Anyone can publish anything online — blogs, social media posts, wiki edits, or opinion pieces.  
Therefore, evaluation skills are crucial.

### **Factors to Consider**
- **Source:** Who wrote it? Are they credible?  
- **Evidence:** Is the claim backed by facts?  
- **Objectivity:** Is the content free from bias or agendas?  
- **Corroboration:** Do multiple reliable sources agree?

### **Questions**
**Q:** What do you call a cryptographic method or product considered bogus or fraudulent?  
**A:** `snake oil`

**Q:** What is the name of the command replacing `netstat` in Linux systems?  
**A:** `ss`

### 🧠 **Deep Dive: `ss` Command**

`ss` (socket statistics) is the modern, faster alternative to `netstat`.

#### Key Features
- **Faster:** Talks directly to kernel netlink sockets.  
- **More detailed:** Shows timers, memory, TCP info.  
- **Advanced filtering:** Filter by state, ports, address.

---

## 📝 **Task 3 — Search Engines**

Modern search engines support advanced operators that help refine searches.

### ⭐ Google Search Operators

| Operator | Meaning | Example |
|---------|---------|---------|
| `"exact phrase"` | Find exact wording | `"passive reconnaissance"` |
| `site:` | Limit results to a specific domain | `site:tryhackme.com success stories` |
| `-` | Exclude terms | `pyramids -tourism` |
| `filetype:` | Search only specific files | `filetype:ppt cyber security` |

🔗 **More operators:** https://github.com/cipher387/Advanced-search-operators-list

### **Questions**
**Q:** Limit results to PDF files containing "cyber warfare report".  
**A:** `filetype:pdf cyber warfare report`

**Q:** What phrase does `ss` stand for?  
**A:** `socket statistics`

---

## 📝 **Task 4 — Specialized Search Engines**

### 🔹 **Shodan**
Search engine for internet-connected devices.  
Example: `apache 2.4.1` to find servers running that version.

### 🔹 **Censys**
Similar to Shodan, but focuses on:
- Hosts  
- Websites  
- Certificates  
- Internet assets  

### 🔹 **VirusTotal**
Multi-antivirus scanner for:
- Files  
- URLs  
- Hashes  

Shows detection labels and community insights.

### 🔹 **Have I Been Pwned (HIBP)**
Checks whether an email appears in breached datasets.

### **Questions**
**Q:** What is the top country with *lighttpd* servers?  
**A:** `United States`

![shodan](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/m1.10.png)

**Q:** What does BitDefenderFalx detect the file with hash  
`2de70ca737c1f4602517c555ddd54165432cf231ffc0e21fb2e23b9dd14e7fb4` as?  
**A:** `Android.Riskware.Agent.LHH`

![virustotal](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/m1.11.png)

---

## 📝 **Task 5 — Vulnerabilities & Exploits**

### 🔹 **CVE (Common Vulnerabilities and Exposures)**  
A standardized identifier for vulnerabilities (e.g., `CVE-2024-29988`).  
Maintained by MITRE.

Useful links:  
- CVE Program  
- National Vulnerability Database (NVD)

### 🔹 **Exploit Database**  
Contains public exploit PoCs and verified exploit code.

GitHub is also a major source for:
- Exploit scripts  
- PoC  
- Security tools  

### **Questions**
**Q:** What utility does CVE-2024-3094 refer to?  
**A:** `xz`

Details: Malicious code was injected into xz versions 5.6.0 & 5.6.1 tarballs, affecting systemd interactions.

---

## 📝 **Task 6 — Technical Documentation**

### 🔹 **Linux Manual Pages (`man`)**
Before the web, man pages were the primary documentation source.

Example:
```
man ip
```

### 🔹**Microsoft Technical Documentation**
Official docs for Windows commands, APIs, features.

Example search: ipconfig documentation

### 🔹**Product Docs**
Every major tool has official documentation:

- Snort
- Apache HTTP Server
- PHP
- Node.js

Always check official docs first — they’re most accurate and updated.

### **Questions**
**Q:** What does the Linux command cat stand for?  
**A:** `concatenate`
(Also used to display files)

**Q:** What is the netstat parameter in Windows to show executables?  
**A:** `-b`

---

## 📝 **Task 7 — Social Media**
Social media is a powerful OSINT and cybersecurity tool.

### **Why Use Social Media?**

- Learn about employees
- Check for oversharing
- Identify security weaknesses
- Follow cybersecurity updates & news

### **OSINT Tip:**
Use temporary email when exploring new platforms.

### **Questions**
**Q:** What platform helps you evaluate technical background of employees?  
**A:** `Linkedin`

**Q:** Which platform might reveal answers to secret questions like childhood school?  
**A:** `Facebook`

---

### 🛠 **Commands Summary**
```
ss          # socket statistics
man <cmd>   # view manual pages
cat         # display/concatenate files
```

---

### 📝 **Key Takeaways**

- Not all information is reliable—verify sources.
- Search engines are powerful when using filters and operators.
- Specialized tools like Shodan, Censys, and VirusTotal reveal deep insights.
- CVE databases help track vulnerabilities across the industry.
- Official documentation is the best source of truth.
- Social media can be both a security risk and an intelligence goldmine.

---

### 🏁 **Summary**

This room teaches you how to search, filter, evaluate, research, and validate information — crucial skills for cybersecurity analysts, penetration testers, OSINT investigators, and defenders. Strong search skills make you faster, more accurate, and more effective in any cybersecurity role.

![Search-Skill](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/Search-Skill.png)
