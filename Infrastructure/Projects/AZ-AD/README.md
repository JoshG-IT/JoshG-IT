<!-- ============================================================
⚠️ EDUCATIONAL USE ONLY DISCLAIMER
Author: Joshua Gonzalez
Applies To: All repositories, labs, and educational templates under this account
============================================================ -->

> ## ⚠️ Educational Use Only — Read Before Proceeding  
>
> **Purpose:**  
> All content within any repository published by **Joshua Gonzalez** (including PDFs, Markdown files, scripts, templates, and lab instructions) is provided **strictly for educational, training, and demonstration purposes**.  
>
> **Usage Conditions:**  
> - These materials are **not intended for production or commercial use**.  
> - You are fully responsible for **any configurations, deployments, or cloud costs** incurred while following these labs.  
> - The author, **Joshua Gonzalez**, assumes **no liability** for data loss, misconfiguration, or financial impact caused by misuse or misunderstanding.  
> - Do **not** include real credentials, company data, or personal information.  
> - These labs exist for **learning, experimentation, and personal portfolio growth** only.  
>
> **Legal Notice:**  
> By accessing or using these materials, you acknowledge that you understand and accept these terms in full.  
>
> Joshua Gonzalez — Educational Training Content.  
> Redistribution or commercial resale of these materials (including anything produced or posted by Joshua Gonzalez) is **strictly prohibited without written consent**.

---

[![Platform](https://img.shields.io/badge/Platform-Microsoft%20Azure-0078D4?style=for-the-badge&logo=microsoftazure)](https://portal.azure.com)
[![Windows Server](https://img.shields.io/badge/Windows-Server%202022-blue?style=for-the-badge&logo=windows)](https://www.microsoft.com/windows-server)
[![Windows 11](https://img.shields.io/badge/Windows-11%20Pro-blueviolet?style=for-the-badge&logo=windows11)](https://www.microsoft.com/software-download/windows11)
[![Purpose](https://img.shields.io/badge/Purpose-Cloud_Active_Directory_Lab-lightgrey?style=for-the-badge)]()
[![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge)]()

---

# Microsoft Azure Active Directory Lab (Cloud Edition)

---

## Overview
This lab demonstrates how to deploy an **Active Directory environment in Azure** using two virtual machines connected within a Virtual Network.  
It is designed for **hands-on training and demonstration**, showing how a Windows Server domain, client join, and Group Policies operate in a cloud-based environment.

---

## Key Components
| Component | Role | Description |
|------------|------|-------------|
| **DC01** | Windows Server 2022 | Hosts AD DS, DNS, and optional DHCP |
| **CLIENT01** | Windows 11 Pro | Domain-joined client used for GPO testing |
| **Virtual Network (VNet)** | Cloud Network | Private IP space (192.168.100.0/24) for internal communication |
| **Network Security Group (NSG)** | Firewall | Allows inbound RDP only from instructor’s IP |
| **Resource Group** | Management Container | Contains and organizes all Azure assets |
| **Access** | Connectivity | Direct RDP (no Bastion) to minimize costs |

---

## Learning Objectives
- Understand how **Active Directory (AD DS)** manages users and devices  
- Compare **Azure Fabric DHCP** vs. traditional on-prem DHCP  
- Apply **Group Policy Objects (GPOs)** for control and security  
- Demonstrate **centralized user management** with RDP testing  
- Practice **resource cleanup and cost awareness**

---

## Core Lab Setup
| Component | Purpose | Notes |
|------------|----------|-------|
| **Resource Group** | Logical container for Azure assets | Easy cleanup |
| **Virtual Network (VNet)** | Simulated internal LAN | 192.168.100.0/24 subnet |
| **Network Security Group (NSG)** | Restrict access | Only instructor IP on port 3389 |
| **DC01 (Server)** | Domain Controller | AD DS, DNS, DHCP roles |
| **CLIENT01 (Client)** | Domain-joined workstation | Verifies user/group access |

---

## Key Group Policies Demonstrated
| GPO | Purpose | Result |
|-----|----------|--------|
| **Disable Control Panel** | Restrict access to system settings | “Restricted by your administrator” displayed |
| **Prevent Wallpaper Change** | Enforce branding | Company logo set for all users |
| **Remove Task Manager** | Prevent task termination | Task Manager disabled for standard users |
| **Allow RDP for HR** | Grant remote login access | HR users allowed to RDP into CLIENT01 |

---

## Fun Step – “Desktop Image Added”
Before applying GPOs, users can set a custom desktop image.  
After GPO enforcement, users can still see the file but **cannot set it as wallpaper**, illustrating **Group Policy precedence** over local settings.

---

## Screenshots
| Image | Description |
|--------|-------------|
| PUT SCREENSHOT HERE | Resource Group created |
| PUT SCREENSHOT HERE | Virtual Network `vnet-adlab` created |
| PUT SCREENSHOT HERE | NSG rule allowing RDP from instructor IP |
| PUT SCREENSHOT HERE | Windows Server 2022 VM deployed (DC01) |
| PUT SCREENSHOT HERE | Windows 11 Pro client joined to domain |
| PUT SCREENSHOT HERE | AD DS role installed and DC01 promoted |
| PUT SCREENSHOT HERE | Control Panel and Task Manager restricted via GPO |
| PUT SCREENSHOT HERE | Wallpaper GPO applied successfully |
| PUT SCREENSHOT HERE | Azure Cost Analysis after cleanup |

---

## Technical Highlights
- **Secure RDP access** restricted to a single IP via NSG  
- **Custom DNS** (192.168.100.10) for internal resolution  
- **Azure DHCP** differs from on-prem DHCP (VNet-assigned IPs)  
- **GPOs** enforce consistent desktop and access policies  
- **Shared UNC path:** `\\DC01\Company\logo.jpg`  
- **Resource cleanup** ensures cost efficiency  

---

## Estimated Cost
| Resource | Type | Cost/hr |
|-----------|------|---------|
| DC01 | B2s VM | ≈ $0.046 |
| CLIENT01 | B2s VM | ≈ $0.046 |
| **Total** |  | **≈ $0.09/hr (~$0.27 for 3 hrs)** |

---

## Results
☑ Domain environment successfully deployed  
☑ CLIENT01 joined to `lab.local`  
☑ GPOs applied and verified (`gpresult /h C:\GPOReport.html`)  
☑ Wallpaper, Control Panel, and Task Manager restrictions enforced  
☑ RDP tested and functioning  
☑ Resources deleted to prevent cost overrun  
