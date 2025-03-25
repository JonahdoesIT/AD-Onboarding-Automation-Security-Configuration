
# 🛡️ IT Onboarding Automation & Security Configuration

## 📘 Overview
This tutorial simulates real-world IT onboarding and Windows domain configuration tasks in an enterprise environment. 💻  
Using hands-on techniques from my bootcamp, I joined a computer to a domain, managed user accounts and groups in Active Directory, configured group policies, and automated common administrative tasks using PowerShell. Please follow the link to view full project.
 https://jonahdoesit.github.io/IT-Onboarding-Automation-Security-Configuration/

## 🧱 Steps & Key Tasks

### 🔹 Step 1: Join a Computer to the Domain
- Retrieved server IPv4 address via `ipconfig`
- Configured DNS to point to domain controller
- Joined the machine to `contoso.com` using admin credentials

---

### 🔹 Step 2: Create Domain Users
- Used **Active Directory Users and Computers**
- Created new users: names, passwords, and permissions

---

### 🔹 Step 3: Create Security Group & Add Members
- Created group via Active Directory
- Added users to group and confirmed successful membership

---

### 🔹 Step 4: Create a Shared Folder with Permissions
- Created `test.txt` in department folder
- Configured folder sharing and permissions via Advanced Sharing settings
- Shared with individual users and groups

---

### 🔹 Step 5: Create an Organizational Unit (OU)
- Created an **OU** to manage users, groups, and computers
- Moved entities into the OU for centralized control

---

### 🔹 Step 6: Create and Link a GPO (Group Policy Object)
- Configured startup messages via:
  - `Computer Configuration > Policies > Administrative Templates > System`
- Enabled:
  - **Login Message Title**
  - **Login Message Text**
  - Disabled **Command Prompt** access
  - Disabled **Run** menu
- Created and deployed a `.bat` script to map network drives
- Linked the script via:
  - `User Configuration > Policies > Windows Settings > Scripts`

---

### 🔹 Step 7: Event Log Monitoring
- Opened Event Viewer > Windows Logs > Security
- Monitored event ID `4624` for successful logons

---

### 🔹 Step 8: Use PowerShell to View Installed Programs
```powershell
Get-WmiObject -Class Win32_Product | 
Select-Object Name, InstallDate | 
Sort-Object InstallDate
