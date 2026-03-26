# 🏢 Active Directory Basics
This room introduces **Microsoft Active Directory (AD)** — the backbone of most enterprise Windows environments. Active Directory centralises the management of users, computers, security policies, authentication, and resources within a corporate network.

Throughout this room, we explore how domains function, how objects are structured, how authentication works, and how organisations scale using trees, forests, and trust relationships.

---

## 🎯 Learning Objectives
By completing this room, you will understand:

- What Active Directory is
- What a Windows Domain is
- Core AD components (Users, Groups, Machines, OUs)
- How Group Policy Objects (GPOs) work
- Authentication protocols (Kerberos & NetNTLM)
- Trees, Forests, and Trust Relationships
- Basic domain administration tasks

---

## 🧠 Core Concepts Covered
- Centralised identity management
- Domain Controllers (DC)
- Security Principals
- Organizational Units (OUs)
- Group Policy Objects (GPOs)
- Kerberos authentication
- NetNTLM authentication
- Trust relationships
- Enterprise architecture (Trees & Forests)

---

## 🧭 Task 2: Windows Domains

A **Windows Domain** is a group of users and computers managed centrally using **Active Directory (AD)**.

The server that runs Active Directory services is called a:

> **Domain Controller (DC)**

### ✅ Advantages of a Domain

- Centralised identity management
- Centralised security policies
- Simplified authentication
- Scalability

### 🌍 Real-World Example

In schools/universities:
- Same username/password works on any campus computer
- Policies restrict access to system settings
- Credentials are verified centrally via AD

### 🖥 THM Inc. Scenario

You are the new IT Admin reviewing the domain: `THM.local`


RDP Credentials:

| Username | Administrator |
|-----------|--------------|
| Password | Password321 |

Login format:`THM\Administrator`

### ✅ Answers

**In a Windows domain, credentials are stored in:**  
`Active Directory`

**Server running AD services:**  
`Domain Controller`

---

## 🧭 Task 3: Active Directory Core Components

The core service in a domain is:

> **Active Directory Domain Services (AD DS)**

### 👤 Users

Users are **security principals** that:
- Can authenticate
- Can be assigned permissions
- Represent people or services

### 💻 Machines

Each domain-joined computer has a machine account.

Naming format:`ComputerName$`

Example:`DC01$`

Machine passwords:
- 120 random characters
- Automatically rotated

### 👥 Security Groups

Used to assign permissions to multiple users.

Important default groups:

| Group | Purpose |
|--------|----------|
| Domain Admins | Full domain control |
| Server Operators | Manage DCs |
| Backup Operators | Access all files |
| Account Operators | Modify accounts |
| Domain Users | All users |
| Domain Computers | All machines |
| Domain Controllers | All DCs |

### 🗂 Organizational Units (OUs)

OUs are containers used to:

- Organise users & computers
- Apply policies

A user can belong to:
- Only **one OU**
- Multiple **Security Groups**

### 🔄 Groups vs OUs

| OUs | Security Groups |
|-----|----------------|
| Used for policies | Used for permissions |
| One per user | Multiple allowed |

### ✅ Answers

**Group that administrates entire domain:**  
`Domain Admins`

**Machine account for TOM-PC:**  
`TOM-PC$`

**Container for grouping QA users for policies:**  
`Organizational Units`

---

## 🧭 Task 4: Managing Users in AD

![ad](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M3/3.12.png)

### 🗑 Deleting OUs

By default, OUs are protected against accidental deletion.

Steps:
1. Enable **Advanced Features**
2. Go to Properties
3. Disable protection checkbox
4. Delete OU

![delete](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M3/3.13.png)

![delete1](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M3/3.14.png)

### 🔐 Delegation

Delegation = granting limited administrative control over an OU.

Example:
- Phillip (IT support)
- Delegated password reset rights

![delegate](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M3/3.15.png)

![delegate1](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M3/3.16.png)

![delegate](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M3/3.17.png)

### 🖥 PowerShell Password Reset

```powershell
Set-ADAccountPassword sophie -Reset -NewPassword (Read-Host -AsSecureString -Prompt 'New Password')
```

Force password change:
```
Set-ADUser -ChangePasswordAtLogon $true -Identity sophie
```

### ✅ Answers

**Flag from Sophie's desktop:**  
`THM{thanks_for_contacting_support}`

![ans](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M3/3.18.png)

![ans1](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M3/3.19.png)

![ans2](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M3/3.20.png)

![ans3](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M3/3.21.png)

![ans4](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M3/3.22.png)

![ans4](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M3/3.23.png)

**Granting privileges over OU is called:**  
`delegation`

---

## 🧭 Task 5: Managing Computers in AD

Default container:`Computers`

![ans](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M3/3.24.png)

Separate OUs for:
- Workstations
- Servers
- Domain Controllers

### 🏗 Device Categories
1. Workstations – user PCs
2. Servers – service providers
3. Domain Controllers – most sensitive

### ✅ Answers

**Computers in Workstations OU:**  
`7`

![ans1](https://github.com/Deeptig9138/CyberSecurity101---THM/blob/main/screenshots/M3/3.25.png)

**Separate OUs recommended?**  
`yay`

---

## 🧭 Task 6: Group Policies (GPO)

GPO = Collection of settings applied to OUs.

Managed via:`Group Policy Management`

GPO Structure:
- Computer Configuration
- User Configuration

### 📂 GPO Distribution

Network share:`SYSVOL`

Path:`C:\Windows\SYSVOL\sysvol\`

Force update:`gpupdate /force`

### 🎯 Implemented GPOs

1️⃣ Restrict Control Panel Access

2️⃣ Auto Lock Screen (5 min inactivity)

### ✅ Answers

**Network share distributing GPOs:**  
`SYSVOL`

**Can GPO apply to users & computers?**  
`yay`

---

## 🧭 Task 7: Authentication Methods

Two authentication protocols:
- Kerberos (default)
- NetNTLM (legacy)

### 🔐 Kerberos

*Uses tickets:*
- TGT (Ticket Granting Ticket)
- TGS (Ticket Granting Service)

*Flow:*
- User → KDC → TGT
- User → KDC → TGS
- User → Service → Access

### 🔄 NetNTLM

Challenge-response mechanism.

Password:
- Never transmitted over network

### ✅ Answers

**Will a current version of Windows use NetNTLM as the preferred authentication protocol by default? (yay/nay)**  
`nay`

**Ticket allowing request for TGS:**  
`Ticket Granting Ticket`

**Password transmitted in NetNTLM?**  
`nay`

---

## 🧭 Task 8: Trees, Forests & Trusts

### 🌳 Tree

Multiple domains sharing same namespace.

Example:
```
thm.local
uk.thm.local
us.thm.local
```

Enterprise-level group:
```
Enterprise Admins
```

### 🌲 Forest

Multiple trees with different namespaces.

Example:
```
thm.local
mht.local
```

### 🤝 Trust Relationships

Required for cross-domain access.

Types:
- One-way trust
- Two-way trust

Trust does NOT automatically grant access — permissions must still be configured.

### ✅ Answers

**Domains sharing namespace:**  
`Tree`

**Required for cross-domain access:**  
`A Trust Relationship`

---

## 🏁 Task 9: Conclusion

This room introduced the fundamentals of:
- Windows Domains
- AD structure
- User & computer management
- GPO deployment
- Authentication methods
- Enterprise domain architecture

Active Directory is powerful — and misconfigurations can be dangerous.

---

## 🚀 Next Steps

To go deeper:
- Active Directory Hardening
- Compromising Active Directory
- Kerberos attacks (Golden Ticket, Silver Ticket)
- AD privilege escalation techniques

---
*📌 Active Directory knowledge is essential for both blue team and red team professionals.
Mastering AD fundamentals is the gateway to enterprise security expertise.*
