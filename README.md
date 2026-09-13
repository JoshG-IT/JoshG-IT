<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&height=190&color=0:2B5D8C,50:8C3A3A,100:4A7350&text=Cybersecurity%20Portfolio&fontSize=40&fontAlign=50&fontAlignY=36&fontColor=ffffff&animation=fadeIn" alt="Cybersecurity Portfolio"/>
</p>

---

<p align="center">
Documented security casework across identity, detection, and exposure management.<br/>
Each case carries evidence: commands, queries, logs, findings, and remediation.
</p>

---

<table align="center">
<tr>
<td width="33%" align="center" valign="top">
  <br/>
  <a href="https://github.com/JoshG-IT/identity-security">
    <img src="https://img.shields.io/badge/IDENTITY_SECURITY-2B5D8C?style=for-the-badge" height="36" alt="Identity Security"/>
  </a>
  <br/><br/>
  Entra ID · Active Directory<br/>
  RBAC · Azure Policy · Privileged Access
  <br/><br/>
</td>
<td width="33%" align="center" valign="top">
  <br/>
  <a href="https://github.com/JoshG-IT/security-operations">
    <img src="https://img.shields.io/badge/SECURITY_OPERATIONS-8C3A3A?style=for-the-badge" height="36" alt="Security Operations"/>
  </a>
  <br/><br/>
  Sentinel · Defender · Sysmon<br/>
  KQL · Threat Hunting · Incident Response
  <br/><br/>
</td>
<td width="33%" align="center" valign="top">
  <br/>
  <a href="https://github.com/JoshG-IT/vulnerability-management">
    <img src="https://img.shields.io/badge/VULNERABILITY_MGMT-4A7350?style=for-the-badge" height="36" alt="Vulnerability Management"/>
  </a>
  <br/><br/>
  Nessus · Defender for Cloud<br/>
  CIS · DISA STIG · NIST 800-53
  <br/><br/>
</td>
</tr>
</table>

---

<h2 align="center">Featured Cases</h2>

<table align="center" width="100%">
<tr>
<td align="left">

<h3><a href="https://github.com/JoshG-IT/identity-security/tree/main/cases/IAM-AZ-001-operation-dead-deploy">Operation Dead Deploy</a> | Azure Governance Investigation</h3>

Reconstructed an ARM deployment trail in a live multi-user Azure tenant to determine why an active naming policy detected a violation without preventing resource creation.

<ul>
<li>Traced provisioning from resource discovery through deployment history using Azure CLI</li>
<li>Correlated Azure Policy state, definition, and assignment as three separate objects</li>
<li>Root cause: the control was configured in Audit mode, making it detective rather than preventive</li>
<li>Documented an RBAC authorization boundary encountered mid-investigation and worked around it</li>
</ul>

<img src="https://img.shields.io/badge/IDENTITY_SECURITY-2B5D8C?style=flat-square" alt="Identity Security"/>
<img src="https://img.shields.io/badge/AZURE-2B5D8C?style=flat-square" alt="Azure"/>
<img src="https://img.shields.io/badge/AZURE_CLI-2B5D8C?style=flat-square" alt="Azure CLI"/>
<img src="https://img.shields.io/badge/AZURE_POLICY-2B5D8C?style=flat-square" alt="Azure Policy"/>
<img src="https://img.shields.io/badge/READ--ONLY-6E7681?style=flat-square" alt="Read-only"/>

</td>
</tr>
</table>

---

<h2 align="center">Certifications</h2>

<p align="center">
  <a href="CREDLY_PUBLIC_URL_1"><img src="CREDLY_IMAGE_URL_1" height="90" alt="CompTIA Security+"/></a>
  <a href="CREDLY_PUBLIC_URL_2"><img src="CREDLY_IMAGE_URL_2" height="90" alt="Microsoft Azure Fundamentals"/></a>
  <a href="CREDLY_PUBLIC_URL_3"><img src="CREDLY_IMAGE_URL_3" height="90" alt="AWS Cloud Practitioner"/></a>
  <a href="CREDLY_PUBLIC_URL_4"><img src="CREDLY_IMAGE_URL_4" height="90" alt="AWS Solutions Architect"/></a>
</p>

<table align="center">
<tr><th>Vendor</th><th>Certification</th><th>Domain</th></tr>
<tr><td>CompTIA</td><td><b>Security+ (SY0-701)</b></td><td>Security Fundamentals</td></tr>
<tr><td>Microsoft</td><td><b>Azure Fundamentals (AZ-900)</b></td><td>Cloud Fundamentals</td></tr>
<tr><td>AWS</td><td><b>Cloud Practitioner (CLF-C02)</b></td><td>Cloud Fundamentals</td></tr>
<tr><td>AWS</td><td><b>Solutions Architect - Associate (SAA-C03)</b></td><td>Cloud Architecture</td></tr>
</table>

---

<h2 align="center">Skills &amp; Tools</h2>

```ini
[Identity_Security]
Platforms    = Entra ID, Active Directory, Azure RBAC
Capabilities = Azure Policy, Conditional Access, Access Reviews, Group Policy
Focus        = Privileged access, governance controls, consent governance

[Security_Operations]
SIEM_EDR     = Microsoft Sentinel, Defender for Endpoint, Sysmon
Query        = KQL, PowerShell, Windows Event Logs
Practice     = Threat hunting, log analysis, incident response
Frameworks   = MITRE ATT&CK

[Vulnerability_Management]
Scanning     = Tenable Nessus, Defender for Cloud
Practice     = Authenticated scanning, risk prioritization, patch validation
Standards    = CIS Benchmarks, DISA STIG, NIST 800-53

[Infrastructure_Foundation]
Systems      = Windows Server, Linux (RHEL, Ubuntu), Hyper-V, VMware ESXi
Networking   = VLANs, routing, ACLs, IPsec VPN, pfSense
Automation   = PowerShell, Python, Bash, Azure CLI, Azure Resource Graph
```

---

<p align="center">
Cases are performed in controlled lab and training environments.
</p>
