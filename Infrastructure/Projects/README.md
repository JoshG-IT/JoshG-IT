<!-- ============================================================
ACTIVE DIRECTORY ON-PREMISES LAB (VIRTUALBOX EDITION)
Student GitHub Template - Created by Joshua Gonzalez
For Educational and Learning Showcase Use
============================================================ -->

# Active Directory On-Premises Lab (VirtualBox Edition)

> **Instructions for Students**
>
> This repository is a **GitHub template** provided by **Joshua Gonzalez** for students who complete the *Active Directory On-Premises Lab* training.
> 
> After finishing your lab:
> 1. **Copy this Markdown (README.md)** into your own GitHub repository.  
> 2. Replace the sample text and screenshots with **your own work**.  
> 3. Use this as your **IT portfolio showcase** to demonstrate your hands-on experience.  
>
> The sections below help you structure your documentation — including:
> - Lab overview and learning objectives  
> - Configuration details (VMs, roles, IPs, etc.)  
> - Screenshots of your own environment  
> - Validation steps and summary of what you learned  
>
> **Goal:** Build confidence in technical writing, professional documentation, and hands-on IT skills.

---

[![Platform](https://img.shields.io/badge/Platform-VirtualBox-orange?style=for-the-badge&logo=virtualbox)](https://www.virtualbox.org/)
[![Windows](https://img.shields.io/badge/Windows-Server%202022-blue?style=for-the-badge&logo=windows)](https://www.microsoft.com/)
[![Purpose](https://img.shields.io/badge/Purpose-Student_Lab_Showcase-lightgrey?style=for-the-badge)]()
[![Status](https://img.shields.io/badge/Status-Template_Ready-brightgreen?style=for-the-badge)]()

---

> **⚠️ Educational Use Only**
>
> This lab and its documentation template are provided for **educational and portfolio-building purposes** only.  
> Students are free to copy, modify, and personalize this Markdown file for their own learning showcase.  
>
> Do not reuse this material for **commercial or production systems**.  
>
> © 2025 Joshua Gonzalez — Educational Template for Student Learning & Portfolio Development.


---


## Overview
This project demonstrates the deployment of a **complete on-premises Active Directory environment** using **Windows Server 2022** and **Windows 11 Pro** virtual machines inside **VirtualBox**.  
It’s designed for IT training simulation—covering **AD DS**, **DNS**, **DHCP**, **GPOs**, **File Sharing**, **Printer Deployment**, and **Redundancy with a Second Domain Controller**.

---

## Key Components
| Component | Role | Description |
|------------|------|-------------|
| **WS22-DC01** | Primary Domain Controller | Hosts AD DS, DNS, DHCP, Group Policy, and shared company resources |
| **WS22-DC02 (Server Core)** | Secondary Domain Controller | Provides redundancy, replication, and failover testing |
| **W11P-Client** | Windows 11 Pro Workstation | Domain-joined client used to verify user logons, GPOs, and file/print access |
| **Internal Network (VirtualBox)** | Simulated LAN | Isolated 192.168.100.0/24 network with no external internet connectivity |

---

## Learning Objectives
- Deploy and configure **Active Directory Domain Services (AD DS)**  
- Configure **Forward and Reverse DNS zones**  
- Implement **DHCP** with scope assignment and options  
- Apply **Group Policy Objects (GPOs)** for user restrictions and automation  
- Create and test **organizational units, users, and security groups**  
- Set up **shared folders and printers** through GPOs  
- Add a **secondary domain controller (DC02)** for replication testing  
- Simulate **break/fix incidents** and perform troubleshooting  
- Document and create **operational procedures**

---

## Core Lab Setup
| Component | Purpose | Notes |
|------------|----------|-------|
| **VirtualBox Internal Network** | Isolated LAN | Simulates a subnet with private IP addressing |
| **DC01 (192.168.100.10)** | Primary Domain Controller | Runs AD DS, DNS, DHCP, File Sharing, Printer Server |
| **DC02 (192.168.100.11)** | Backup Domain Controller | Replicates directory and SYSVOL data |
| **W11P** | Domain-Joined Client | Used for user logins and GPO verification |
| **DHCP Scope** | 192.168.100.50–100 | Assigns client IPs automatically |
| **Reverse Lookup Zone** | 100.168.192.in-addr.arpa | Enables PTR record resolution |
| **OUs** | Departments -> HR, Marketing, Sales, and IT | For GPO targeting |
| **IT Security Group** | RSAT Control | Only members can use admin tools |
| **Company Share (\\DC01\\Company)** | Shared Folder | Auto-mapped via GPO |
| **Department-Printer (\\DC01\\Department-Printer)** | Shared Printer | Auto-deployed via GPO |

---

## Key Group Policies Implemented
| GPO | Purpose | Result |
|-----|----------|--------|
| **Company Wallpaper** | Enforce branding | Shared logo displayed across all desktops |
| **Disable Control Panel** | Restrict user access | “Restricted by your administrator” shown |
| **Disable Task Manager** | Prevent task manager access | Ctrl+Alt+Del and Task Manager restricted |
| **Login Banner** | Display compliance message | Legal IT banner before login |
| **Mapped Drive Policy** | Connect to \\DC01\\Company | Auto-mounts at user login |
| **RSAT Restriction** | Limit management tools | Only IT Security Group can use RSAT |
| **Web Filtering via Defender** | Restrict access | Blocks sites like YouTube, Netflix, TikTok |
| **Printer Deployment** | Deploy departmental printer automatically | Shared printer (\\DC01\\Department-Printer) appears automatically for all users |

---

## Technical Highlights
- Two-tier **domain controller topology** (GUI + Server Core)  
- **DHCP + DNS** integrated for dynamic name registration  
- **Forward and Reverse DNS zones** configured  
- **Organizational Units** and **Security Groups** for role-based control  
- **Printer and file shares** deployed with GPOs  
- **Replication** verified with `repadmin /replsummary`  
- **Break-Fix Automation** introduces random issues for troubleshooting  
- **Snapshots** created for rollback and controlled failure testing  

---

## Validation Tasks
☑ AD DS roles installed and DC01 promoted  
☑ Reverse DNS zone resolves correctly via `nslookup`  
☑ DHCP distributes correct IPs and DNS settings  
☑ W11P successfully joined to `lab.local` domain  
☑ All GPOs applied (`gpresult /h C:\GPOReport.html`)  
☑ Shared drive and printer available to users  
☑ Replication verified between DC01 and DC02  
☑ Break-Fix challenges completed and restored  
☑ Final documentation prepared  

---

## Screenshots (Optional)
| Image | Description |
|--------|-------------|
| INSERT SCREENSHOT HERE | AD DS role installed and DC01 promoted |
| INSERT SCREENSHOT HERE | Forward and Reverse DNS zones configured |
| INSERT SCREENSHOT HERE | DHCP scope 192.168.100.50–100 active |
| INSERT SCREENSHOT HERE | Wallpaper GPO applied |
| INSERT SCREENSHOT HERE | Control Panel GPO applied |
| INSERT SCREENSHOT HERE | Task Manager GPO applied |
| INSERT SCREENSHOT HERE | Mapped share drive GPO applied |
| INSERT SCREENSHOT HERE | Logon Banner GPO applied |
| INSERT SCREENSHOT HERE | RSAT Restriction GPO applied |
| INSERT SCREENSHOT HERE | Web Filtering GPO applied |
| INSERT SCREENSHOT HERE | Printer GPO applied |
| INSERT SCREENSHOT HERE | Replication status showing DC01 ↔ DC02 |
| INSERT SCREENSHOT HERE | W11P client joined to lab.local and policy applied |

---

## Resource Allocation
| VM | OS | vCPU | RAM | Disk | Role |
|----|----|------|-----|------|------|
| **DC01** | Windows Server 2022 GUI | 2 | 4 GB | 60 GB | Primary Domain Controller |
| **DC02** | Windows Server 2022 Core | 1 | 2 GB | 40 GB | Secondary Domain Controller |
| **W11P** | Windows 11 Pro | 2 | 4 GB | 60 GB | Client Workstation |

---

## Break-Fix Simulation
This lab includes a **randomized PowerShell break-fix script** that introduces one of several issues:
- DNS record deleted  
- User account disabled from OU  
- Wallpaper GPO unlinked  
- Shared printer disabled  

Each trigger displays a message:  
> “Something broke. Identify and fix the issue using AD, DNS, and GPO management tools.”

Students must investigate using tools such as **Event Viewer**, **DNS Manager**, and **Group Policy Management**.

---

## Results
AD environment deployed on a single host machine  
Verified redundancy with DC02 (Server Core)  
GPOs, DHCP, DNS, and shares functioning correctly  
Simulated troubleshooting enhances operational skills  
Fully documented lab for IT training and demonstrations  

---

## Summary
A **Active Directory on-premises lab** built from using **VirtualBox**, designed to replicate a AD environment.  
Demonstrates **infrastructure design, configuration, redundancy, policy enforcement, and troubleshooting**—all inside a local, cost-free simulation.

---

## Tags & Skills
`Active Directory`  `DNS`  `DHCP`  `Group Policy`  `Windows Server 2022`  `Server Core`  `VirtualBox`  `IT Operations`  `Troubleshooting`  `SysAdmin Lab`  `Networking Basics`  `Infrastructure Design`
