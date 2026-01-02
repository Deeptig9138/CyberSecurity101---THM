# 🐧 Linux Fundamentals 1  
*A beginner-friendly introduction to Linux, its history, and essential command-line skills.*

---

## 🎯 Learning Objectives
By completing this room, you will be able to:

- Understand what Linux is and where it is used  
- Learn basic Linux history and distributions  
- Use the Linux terminal with confidence  
- Run essential commands to navigate the filesystem  
- Search for files efficiently using `find` and `grep`  
- Understand and use basic shell operators  

---

## 🧠 Core Concepts: What Is Linux?

Linux is an **open-source operating system** widely used across the world.  
While Windows and macOS focus heavily on graphical interfaces, Linux emphasizes **performance, flexibility, and command-line power**.

### 🏭 Where Is Linux Used?
You’ve likely used Linux today without realizing it:

- Websites and web servers  
- Android smartphones  
- Car infotainment systems  
- Point of Sale (PoS) machines  
- Traffic systems & industrial sensors  

### 🧩 Linux Distributions (Flavours)
Linux is not a single OS — it’s a family of **UNIX-based distributions**.

Common examples:
- **Ubuntu**
- **Debian**
- Fedora
- Arch

For this room and series, **Ubuntu** is used.

📌 *Fun fact:* Ubuntu Server can run on systems with **512 MB RAM**.

---

## 📝 Task 2 — A Bit of Background on Linux

**Question:**  
What year was the first release of a Linux operating system?

**Answer:** `1991`

---

## 📝 Task 4 — Running Your First Few Commands

Most Linux servers **do not have a GUI**.  
Interaction happens via the **Terminal**.

### 🖥️ First Commands

| Command | Description |
|------|------------|
| `echo` | Outputs text |
| `whoami` | Displays current logged-in user |

### Examples
```bash
echo Hello
echo "Hello Friend!"
whoami
```

**Question:**  
1) Output the text TryHackMe

**Answer:** `echo TryHackMe`

2) What is the logged-in username?

**Answer:** `tryhackme`

---

## 📝 Task 5 — Interacting with the Filesystem

To navigate Linux efficiently, these commands are essential:

| Command	| Full Form |
|---------|-----------|
| ls	    | list      |
| cd	    | change directory |
| cat	    | concatenate | 
| pwd	    | print working directory | 

**📂 Listing Files (ls)**
```
ls
ls folder1
```

**📁 Changing Directories (cd)**
```
cd Pictures
ls
```

**📄 Viewing File Contents (cat)**
```
cat note.txt
cat /home/tryhackme/folder4/note.txt
```

📌 Useful for finding:

- Flags
- Passwords
- Configuration values

**📍 Finding Your Location (pwd)**
```
pwd
```

Example paths:

- `/home/tryhackme`
- `/home/tryhackme/folder4`

**Question:**  
1) How many folders are there?

**Answer:** `4`

2) Which directory contains a file?

**Answer:** `folder4`

3) What is the file content?

**Answer:** `Hello World!`

4) Current directory after navigation?

**Answer:** `/home/tryhackme/folder4`

![start](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M2/m2.1.png)

![second](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M2/m2.2.png)

![third](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M2/m2.3.png)

---

## 📝 Task 6 — Searching for Files

Linux allows fast system-wide searching without manual navigation.

**🔍 Using find**

Find a specific file:
```
find -name passwords.txt
```

Find all .txt files:
```
find -name *.txt
```

**📌 Output (example):** `folder4/note.txt`

**🔎 Using grep**

grep searches inside files.

Example: Search for an IP in a log file
```
grep "81.143.211.90" access.log
```

**Question:**  
Find the flag in /home/tryhackme/access.log with prefix THM.

**Answer:** `THM{ACCESS}`

![flag](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M2/m2.5.png)

![flag1](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M2/m2.6.png)

![flag2](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M2/m2.7.png)

---

## 📝 Task 7 — Introduction to Shell Operators

Shell operators increase efficiency and automation.

| Operator	| Purpose |
|-----------|---------|
| &	        | Run command in background |
| &&	      | Run commands sequentially |
| >	        | Redirect output (overwrite) |
| >>	      | Redirect output (append) |

**⚙️ Operator Examples**

`&` — Background execution
```
cp bigfile.txt backup.txt &
```

`&&` — Conditional execution
```
mkdir test && cd test
```

`>` — Overwrite file
```
echo hey > welcome
```

`>>` — Append to file
```
echo hello >> welcome
```

**Question:**  
1) Background operator?

**Answer:** `&`

2) Replace file contents with password123?

**Answer:** `echo password123 > passwords`

3) Append tryhackme without removing content?

**Answer:** `echo tryhackme >> passwords`

![eg](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M2/m2.8.png)

---

## 🛠 Commands Used (Quick Reference)
```
echo
whoami
ls
cd
cat
pwd
find
grep
```

---

## 📝 Key Takeaways

- Linux is powerful, lightweight, and everywhere
- Terminal skills are essential for servers & security
- File navigation is faster without GUI
- find and grep are critical for forensics & SOC work
- Shell operators enable automation

---

## 🏁 Summary

This room builds your Linux foundation by introducing the terminal, filesystem navigation, file searching, and shell operators. These skills are essential for SOC analysts, penetration testers, DFIR professionals, and system administrators. Mastering Linux early gives you a massive advantage in cybersecurity.

![linux1](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M2/Linux1.png)
