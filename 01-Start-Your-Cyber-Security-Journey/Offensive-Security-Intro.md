# Offensive Security Intro  
*A beginner-friendly introduction to offensive security, hacking mindset, and your first practical web enumeration task using Gobuster.*

---

## 🎯 Learning Objectives
- Understand what offensive security means  
- Learn the purpose of virtual machines in ethical hacking  
- Perform your first directory brute-force attack using Gobuster  
- Identify hidden web pages on a target site  
- Understand real-world offensive security career paths  

---

## 🧠 Core Concepts

### **Offensive Security**
Offensive means attacking. Offensive security involves thinking like a hacker to break into systems, exploit vulnerabilities, and gain unauthorized access — but all in a **legal and ethical environment**. This falls under the **Red Team** domain.

### **Virtual Machines**
TryHackMe provides a safe VM (virtual machine), a virtual replica of a real system.  
VMs (VirtualBox, VMware, etc.) allow you to:

- Practice hacking safely  
- Reset systems if you break them  
- Experiment without damaging your real machine  

### **Gobuster**
Gobuster is a **fast command-line tool** used to discover:

- Hidden folders  
- Hidden files  
- Admin panels  
- Subdomains  
- Virtual hosts  

It works by **brute forcing** URLs using a wordlist.

### **Directory Enumeration**
This is the process of finding hidden areas on a website such as:

- `/admin`
- `/backup`
- `/bank-transfer`
- `/images`

---

## 🧭 Walkthrough (Step-by-Step)

### **Task 1 — Offensive vs Defensive Security**

**Question:** Which option describes simulating a hacker to find vulnerabilities?

**Answer:** `Offensive Security`

---

### **Task 2 — Your First Hack Using Gobuster**

You will use Gobuster to find hidden directories on the FakeBank website.

**Command:**
```
gobuster -u http://fakebank.thm -w wordlist.txt dir
```

**Breakdown of the Command:**
| Part                | Description                     |
| :------------------ | :-----------------------------: |
| gobuster            | Runs the Gobuster tool          |
| -u	                | Specifies the target URL        |
| http://fakebank.thm	| Target website                  |
| -w wordlist.txt	    | Wordlist to test possible paths |
| dir	                | Directory enumeration mode      |

**Expected Output:**
```
/images (Status: 301)
/bank-transfer (Status: 200)
```

- 200 → OK (page exists)
- 301 → Redirect (directory exists)

**This reveals a hidden page:**
```👉 /bank-transfer```

---

### **Task 3 — Exploiting the Hidden Bank Page**

Visit the hidden page by entering:
```
http://fakebank.thm/bank-transfer
```

You'll find a vulnerable transfer form.

- **Mission:** Transfer $2000 from account 2276 → 8881
- Refresh your account page to confirm the change.

**Question:** What message appears above your account balance?

**Answer:** BANK-HACKED

---

### **🛠 Commands Used**
```
gobuster -u http://fakebank.thm -w wordlist.txt dir
```

---

### **📝 Notes & Takeaways**

- Offensive security = acting like a hacker to find weaknesses
- VMs are safe, disposable hacking environments
- Gobuster is essential for discovering hidden website content
- Directory enumeration is a fundamental pentesting skill
- Understanding status codes (200, 301, 403) is crucial

---

### **🔗 Useful References**

- Gobuster GitHub: https://github.com/OJ/gobuster
- SecLists (common wordlists): https://github.com/danielmiessler/SecLists

---

### **🏁 Summary**

This room introduced the basics of offensive security and guided you through your first hands-on hack. You learned how to use Gobuster to discover hidden directories, access a vulnerable bank transfer page, and understand how attackers map websites. These foundational skills prepare you for deeper penetration testing and red team operations.

---

![Offensive-Sec](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/Offensive_Sec.png)
