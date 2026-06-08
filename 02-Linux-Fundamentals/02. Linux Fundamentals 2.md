# 🐧 Linux Fundamentals 2  
*Building on Linux basics: remote access, filesystem power, permissions, and system structure.*

---

## 🎯 Learning Objectives
By completing this room, you will be able to:

- Connect to a remote Linux machine using SSH  
- Understand how SSH works and why it is secure  
- Use flags and switches to extend command functionality  
- Create, copy, move, and delete files and directories  
- Identify file types and permissions  
- Switch between users safely  
- Understand common Linux root directories and their purpose  

---

## 🧠 Core Concepts: Advancing Linux Fundamentals

Linux Fundamentals 2 builds directly on **Linux Fundamentals 1**.  
Here, we move closer to **real-world Linux usage** by:

- Logging into remote systems (like servers)
- Working efficiently with files
- Understanding permissions and users
- Learning where critical system data lives

These skills are **essential** for:
- SOC analysts  
- Penetration testers  
- System administrators  
- DFIR professionals  

---

## 📝 Task 2 — Accessing Your Linux Machine Using SSH

### 🔐 What Is SSH?

**SSH (Secure Shell)** is an encrypted protocol that allows you to:
- Execute commands on a remote machine
- Transfer data securely over a network

✔ Commands are encrypted  
✔ Passwords are never sent in plaintext  

### 🚀 Deploying the Machines

You will deploy:
- Your **Linux target machine**
- The **TryHackMe AttackBox** (Ubuntu-based)

### 🖥️ Using SSH to Log In

SSH syntax:
```
ssh username@IP_ADDRESS
```

For this room:

- **Username:** tryhackme
- **Password:** tryhackme

Example:
```
ssh tryhackme@MACHINE_IP
```

> 📌 Passwords do not show when typing — this is normal.

Once connected, all commands execute on the remote machine.

![ssh](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M2/m2.9.png)

---

## 📝 Task 3 — Introduction to Flags & Switches

Commands can be extended using flags (also called switches).

Example:
```
ls
ls -a
```

- ls → lists visible files
- ls -a → lists all files, including hidden ones (.)

**🆘 Using** `--help`

Most commands support:
```
command --help
```

Example:
```
ls --help
```

This output is derived from the manual (man) pages.

**📖 Using Man Pages**
```
man ls
```

Man pages contain:

- Description
- Syntax
- Available flags
- Examples

![help](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M2/m2.10.png)

![help1](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M2/m2.11.png)

**Questions**

- Which arrow key scrolls down the man page? - `down`
- What flag enables human-readable output? - `-h`

---

## 📝 Task 4 — Filesystem Interaction Continued

More filesystem commands you’ll use daily:

| Command	| Purpose |
|---------|---------|
| touch	  | Create file |
| mkdir	  | Create directory | 
| cp	    | Copy file/folder | 
| mv	    | Move or rename | 
| rm	    | Delete |
| file	  | Identify file type |

**📄 Creating Files & Folders**
```
touch note
mkdir mydirectory
```

**❌ Removing Files & Folders**
```
rm note
rm -R mydirectory
```

> ⚠️ rm -R is dangerous — no recycle bin!

**📦 Copying & Moving**
```
cp note note2
mv note2 note3
mv myfile myfolder
```

**🔍 Identifying File Types**
```
file note
```

Example output:
```
note: ASCII text
```

**Questions**

- Create a file named newnote - `touch newnote`
- File type of unknown1 - `ASCII text`
- Move myfile to myfolder - `mv myfile myfolder`
- File contents - `THM{FILESYSTEM}`

![files](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M2/m2.12.png)

---

## 📝 Task 5 — Permissions 101

Linux permissions define who can do what.

Using:
```
ls -lh
```

Key permission types:

- Read (r)
- Write (w)
- Execute (x)

Permissions apply to:

- Owner
- Group
- Others

### 👥 Users vs Groups

Linux allows:

- Granular access control
- Shared permissions without ownership changes

This is critical for multi-user systems like servers.

**🔄 Switching Users (su)**
```
su user2
```

Login shell (recommended):
```
su -l user2
```

**Questions**

- Owner of important - `user2`
- Command to switch to user2 - `su user2`
- Flag inside important - `THM{SU_USER2}`

![flag](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M2/m2.13.png)

---

## 📝 Task 6 — Common Linux Directories

Understanding the Linux filesystem is crucial.

**📁 `/etc`**

- Configuration files
- User credentials
- System-wide settings

Examples:

- passwd
- shadow
- sudoers

![etc](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M2/m2.14.png)

**📁 `/var`**

- Variable data
- Logs
- Databases

Logs location:
```
/var/log
```

![var](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M2/m2.15.png)

**📁 /root**

- Home directory of root user
- Not `/home/root`

**📁 `/tmp`**

- Temporary storage
- Cleared on reboot
- Writable by all users

Used heavily during:

- Enumeration
- Exploitation
- Script storage

**Questions**

- Log directory path - `/var/log`
- RAM-like directory - `/tmp`
- Root user home - `/root`

---

## 🛠 Commands Used (Quick Reference)
```
ssh
ls
man
touch
mkdir
cp
mv
rm
file
su
```

---

## 📝 Key Takeaways

- SSH is the standard way to access Linux servers
- Flags massively extend command capabilities
- Filesystem control is core to Linux mastery
- Permissions protect multi-user systems
- Understanding /etc, /var, /tmp is vital for security

---

## 🏁 Summary

Linux Fundamentals 2 bridges the gap between basic Linux usage and real-world system interaction. You now know how to remotely access machines, manage files confidently, understand permissions, switch users, and identify where critical system data is stored — all foundational skills for cybersecurity and system administration roles.

![linux2](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M2/Linux2.png)
