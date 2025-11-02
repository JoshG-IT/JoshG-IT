
# Microsoft Azure Active Directory Lab
---
## Overview
This project demonstrates how to deploy a **Active Directory environment in Azure** using two virtual machines.
It’s designed for training and demonstration - showing how a Windows Server domain, client join, and Group Policies work together.
---
**Key Components**
- **DC01:** Windows Server 2022 (AD DS, DNS, DHCP)
- **CLIENT01:** Windows 11 Pro (domain joined)
- **Network:** Azure Virtual Network + Network Security Group (NSG)
- **Access:** Direct RDP (no Bastion, low cost)
---
## Learning Objectives
- Understand how **Active Directory** manages users and computers
- See how **Azure Fabric DHCP** differs from on-prem DHCP
- Apply **Group Policy Objects (GPOs)** for control and security
- Demonstrate **RDP and centralized management**
- Learn how a single server can manage multiple users and machines
---
## Core Lab Setup
| Component | Purpose | Notes |
|------------|----------|-------|
| **Resource Group** | Container for all Azure assets | Deleted to clean up everything at once |
| **Virtual Network (VNet)** | Private IP network (192.168.100.0/24) | Simulates an internal LAN |
| **Network Security Group (NSG)** | Firewall to limit inbound RDP | Allows only instructor’s IP on port 3389 |
| **DC01 (Server)** | Domain Controller | Runs AD DS, DNS, optional DHCP |
| **CLIENT01 (Client)** | Domain-joined client | Used for user login and GPO testing |
---
## Key Group Policies Demonstrated
| GPO | Purpose | Result |
|-----|----------|--------|
| **Disable Control Panel** | Restrict system access | Users see “Restricted by your administrator” |
| **Prevent Wallpaper Change** | Enforce shared wallpaper | Company logo appears on all desktops |
| **Remove Task Manager** | Prevent task termination | Ctrl + Alt + Del -> Task Manager greyed out |
| **Allow RDP for HR** | Enable remote login | HR users can RDP into CLIENT01 |
---
## Fun Step – “Desktop Image added”
Before applying GPOs, users can log in and put a image on a desktop. If you don't do this step, remove it from the description.
After the policies have been applied, the user can still see the file but **can’t set it as wallpaper**, showing how Group Policy overrides local control.
---
## Screenshots
| Image | Description |
|--------|-------------|
| PUT SCREENSHOT HERE| Resource Group created in Azure to contain all lab components |
| PUT SCREENSHOT HERE| Virtual Network `vnet-adlab` created with custom subnet |
| PUT SCREENSHOT HERE| NSG rule allowing RDP only from student’s public IP |
| PUT SCREENSHOT HERE| Windows Server 2022 VM created (DC01) |
| PUT SCREENSHOT HERE| Windows 11 Pro client VM created, background changed and domain joined |
| PUT SCREENSHOT HERE| AD DS role installed and DC01 promoted to domain controller |
| PUT SCREENSHOT HERE| GPO preventing users (HR) from opening Control Panel |
| PUT SCREENSHOT HERE| GPO disabling Task Manager for users part of HR |
| PUT SCREENSHOT HERE| GPO pushing company logo to users in HR |
| PUT SCREENSHOT HERE| Group Policy Management Console showing all enforced policies |
| PUT SCREENSHOT HERE| Cleaning up all resources in Azure Resource Group to avoid charges |
| PUT SCREENSHOT HERE| Cost Analysis of resources for this lab |
---
## Technical Highlights
- Secure RDP access limited to a single external IP
- Custom DNS (192.168.100.10) for internal name resolution
- Demonstrates Azure **Fabric DHCP** vs. traditional server DHCP using an IP address/subnet vs DHCP role
- Enforces domain policies with OU-scoped GPOs
- Uses shared UNC path (`\\DC01\Company\logo.jpg`) for company wallpaper
---
## Estimated Cost
| Resource | Type | Cost/hr |
|-----------|------|---------|
| DC01 | B2s VM | ≈ $0.046 |
| CLIENT01 | B2s VM | ≈ $0.046 |
| **Total** | | **≈ $0.09/hr (~$0.27 for 3 hrs)** |
---
## Results
|Tasks completed|
|--------|
|✅ Domain environment successfully deployed|
|✅ CLIENT01 joined to domain `lab.local`|
|✅ GPOs applied and verified (`gpresult /h C:\GPOReport.html`)|
|✅ Wallpaper, Control Panel, and Task Manager restrictions enforced|
|✅ RDP access functioning for domain users|
|✅ All resources deleted post-lab to avoid costs|
|✅ Summary of Operation Expenditure|
---
