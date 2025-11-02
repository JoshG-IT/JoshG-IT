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
[![Purpose](https://img.shields.io/badge/Purpose-Azure_Active_Directory_Lab-lightgrey?style=for-the-badge)]()
[![Status](https://img.shields.io/badge/Status-Learning_Ready-brightgreen?style=for-the-badge)]()

---

# Microsoft Azure Active Directory Lab (Cloud Edition)

---

## Overview
This lab demonstrates how to deploy an **Active Directory environment in Azure** using two virtual machines connected within a **Virtual Network**.  
It is designed for **hands-on training and demonstration**, showing how a Windows Server domain, client join, and Group Policies operate in a **cloud-based environment**.

---

## Key Components
| Component | Role | Description |
|------------|------|-------------|
| **DC01** | Windows Server 2022 | Hosts AD DS, DNS, and optional DHCP |
| **CLIENT01** | Windows 11 Pro | Domain-joined client used for GPO testing |
| **Virtual Network (VNet)** | Cloud Network | Private IP space (192.168.100.0/24) for internal communication |
| **Network Security Group (NSG)** | Firewall | Allows inbound RDP only from your public IP |
| **Resource Group** | Management Container | Contains and organizes all Azure assets |
| **Access** | Connectivity | Direct RDP (no Bastion) to minimize costs |

---

## Learning Objectives
- Deploy and configure **Active Directory Domain Services (AD DS)** in Azure  
- Configure **NSG rules** to restrict RDP access securely  
- Understand differences between **Azure Fabric DHCP** and traditional DHCP  
- Apply **Group Policy Objects (GPOs)** for centralized management  
- Test **domain join and user permissions** between cloud VMs  
- Practice **resource cleanup and cost optimization**

---

## Core Lab Setup
| Component | Purpose | Notes |
|------------|----------|-------|
| **Resource Group** | Logical container for Azure resources | Simplifies cleanup and management |
| **Virtual Network (VNet)** | Internal communication network | 192.168.100.0/24 subnet |
| **Network Security Group (NSG)** | Firewall control | Restricts RDP to your public IP on port 3389 |
| **DC01 (Server)** | Domain Controller | Runs AD DS, DNS, DHCP (optional) |
| **CLIENT01 (Client)** | Domain-joined workstation | Used for GPO validation and login tests |

---

## Key Group Policies Implemented
| GPO | Purpose | Result |
|-----|----------|--------|
| **Disable Control Panel** | Restrict access to system settings | “Restricted by your administrator” displayed |
| **Prevent Wallpaper Change** | Enforce corporate branding | Company wallpaper applied across clients |
| **Disable Task Manager** | Block task termination | Task Manager disabled for standard users |
| **Allow RDP for HR Group** | Grant limited RDP rights | HR users can RDP into CLIENT01 |

---

## Technical Highlights
- **Secure RDP access** through NSG filtering (source IP restriction)  
- **Custom DNS configuration** (192.168.100.10) for name resolution  
- **Azure DHCP** automatically assigns internal IPs (no manual scope setup)  
- **Group Policy enforcement** through Azure-hosted DC  
- **Shared UNC path:** `\\DC01\Company\logo.jpg` used for wallpaper policy  
- **Azure Cost Management** for estimating and monitoring resource usage  

---

## Validation Tasks
☑ AD DS installed and DC01 promoted successfully  
☑ CLIENT01 joined to `lab.local` domain  
☑ GPOs applied (`gpresult /h C:\GPOReport.html`)  
☑ Wallpaper and system restrictions verified  
☑ HR group RDP access validated  
☑ Azure resources deleted after testing  

---

## Screenshots (Optional)
| Image | Description |
|--------|-------------|
| INSERT SCREENSHOT HERE | Resource Group created |
| INSERT SCREENSHOT HERE | Virtual Network `vnet-adlab` created |
| INSERT SCREENSHOT HERE | NSG rule allowing RDP from instructor IP |
| INSERT SCREENSHOT HERE | Windows Server 2022 deployed as DC01 |
| INSERT SCREENSHOT HERE | Windows 11 client joined to domain |
| INSERT SCREENSHOT HERE | Control Panel GPO enforced |
| INSERT SCREENSHOT HERE | Wallpaper GPO applied |
| INSERT SCREENSHOT HERE | RDP allowed for HR User |
| INSERT SCREENSHOT HERE | Azure Cost Analysis after cleanup |

---

## Resource Allocation
| VM | OS | vCPU | RAM | Disk | Role |
|----|----|------|-----|------|------|
| **DC01** | Windows Server 2022 | 2 | 4 GB | 60 GB | Domain Controller |
| **CLIENT01** | Windows 11 Pro | 2 | 4 GB | 60 GB | Client Workstation |

---

## Estimated Cost
| Resource | Type | Approx. Cost/hr |
|-----------|------|-----------------|
| **DC01** | B2s VM | ≈ $0.046 |
| **CLIENT01** | B2s VM | ≈ $0.046 |
| **Total** |  | **≈ $0.09/hr (~$0.27 for 3 hrs)** |

---

## Results
☑ Domain deployed successfully in Azure  
☑ CLIENT01 verified domain membership and GPO application  
☑ NSG confirmed secure RDP restriction  
☑ Cost estimation validated in Azure portal  
☑ All assets cleaned up post-lab to avoid charges  

---

## Summary
A **Microsoft Azure-hosted Active Directory lab** that mirrors on-premises functionality in the cloud.  
Demonstrates **domain services, GPOs, access control, and cost efficiency**—ideal for **IT training and cloud-based system administration practice**.
