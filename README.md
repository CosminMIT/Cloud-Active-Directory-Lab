# Cloud & Active Directory Home Lab

## Overview
A hands on IT infrastructure lab built to simulate daily 1st Line Service Desk operations, identity administration, and cloud virtual machine deployment. 

**Core Technologies Used:**
* **Cloud Infrastructure:** Microsoft Azure (Resource Groups, Virtual Machines, Network Security Groups)
* **Identity & Access Management:** Microsoft Entra ID (formerly Azure AD), Microsoft 365 Admin Center
* **On-Premises Directory Services:** Windows Server 2022, Active Directory Domain Services (AD DS), ADUC
* **Command-Line Administration:** Windows PowerShell, Command Prompt (`dsquery`, `dsmove`, `dsmod`)

---

## Lab Architecture & Completed Exercises

### 1. Azure Cloud Virtual Machine & Firewall Configuration
* Created a dedicated Azure **Group** to logically isolate lab infrastructure and manage cloud resource lifecycles.
* Deployed a **Windows Server 2022** Virtual Machine in Azure and configured **Network Security Group (NSG)** inbound firewall rules (allowing RDP Port 3389 and SSH Port 22) to enable secure remote connectivity.

### 2. On Premises Active Directory Domain Services (Windows Server 2022)
* Promoted a Windows Server 2022 instance to an **Active Directory Domain Controller** (`itlab.local`).
* Structured departmental **Organizational Units (OUs)** via **Active Directory Users and Computers (ADUC)**.
* Executed routine 1st Line Help Desk tasks including user provisioning, password resets, account unlocks, and Security Group assignments.

### 3. Command-Line & PowerShell Automation
*User creation, and account queries using PowerShell (`New-ADUser`, `Get-ADUser`, `Add-ADGroupMember`) and legacy CMD directory tools (`dsquery`, `dsmove`, `dsmod`).

Get-ADUser -Filter * 
Add-ADGroupMember -Identity 
```

### 4. Microsoft 365 & Entra ID Cloud Administration
* Configured a live **Microsoft Entra ID** tenant alongside the **Microsoft 365 Admin Center**.
* Executed cloud user onboarding, password resets, Security Group assignments, and Multi-Factor Authentication (MFA) re-registrations.


---

## Troubleshooting Case Study: Shared Mailbox Member Visibility

* **Issue:** A newly onboarded user needed access to a department Shared Mailbox, but their name did not appear in the member search list inside the Microsoft 365 Admin Center.
* **Root Cause:** The user account had been provisioned without an active product license, meaning Exchange Online had not yet generated a mailbox object for the account.
* **Resolution:** Navigated to **Users > Active users**, assigned an available **Microsoft 365 Business Standard** license to provision the Exchange mailbox, allowed propagation, and successfully added the user to the Shared Mailbox.

---
