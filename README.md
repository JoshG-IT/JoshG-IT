<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&height=190&color=0:2B5D8C,50:8C3A3A,100:4A7350&text=Cybersecurity%20Portfolio&fontSize=40&fontAlign=50&fontAlignY=36&fontColor=ffffff&animation=fadeIn" alt="Cybersecurity Portfolio"/>
</p>

---

<p align="center">
Each repository below holds documented investigations, implementations, detections, and assessments, backed by real commands, queries, logs, and validated remediation.
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
  PIM · Conditional Access · RBAC
  <br/><br/>
  <b>4 investigations · 2 implementations</b>
  <br/><br/>
</td>
<td width="33%" align="center" valign="top">
  <br/>
  <a href="https://github.com/JoshG-IT/security-operations">
    <img src="https://img.shields.io/badge/SECURITY_OPERATIONS-8C3A3A?style=for-the-badge" height="36" alt="Security Operations"/>
  </a>
  <br/><br/>
  Sentinel · Defender · Sysmon<br/>
  KQL · Threat Hunting · IR
  <br/><br/>
  <b>3 investigations · 6 detections</b>
  <br/><br/>
</td>
<td width="33%" align="center" valign="top">
  <br/>
  <a href="https://github.com/JoshG-IT/vulnerability-management">
    <img src="https://img.shields.io/badge/VULNERABILITY_MGMT-4A7350?style=for-the-badge" height="36" alt="Vulnerability Management"/>
  </a>
  <br/><br/>
  Nessus · Defender VM<br/>
  CIS · DISA STIG · NIST
  <br/><br/>
  <b>2 implementations · 2 assessments</b>
  <br/><br/>
</td>
</tr>
</table>

---

<h2 align="center">Projects</h2>

<table align="center" width="100%">
<tr>
<td align="left">

<h3><a href="PROJECT_LINK_1">Operation Dead Deploy</a> — Privileged Access Investigation</h3>

Traced an orphaned deployment service principal holding standing Owner rights across a subscription.

<ul>
<li>Reconstructed the assignment path via RBAC review and Activity Log correlation</li>
<li>Identified a 14-month credential rotation gap on a privileged identity</li>
<li>Delivered scoped custom-role remediation, mapped to NIST 800-53 AC-6</li>
</ul>

<img src="https://img.shields.io/badge/IDENTITY_SECURITY-2B5D8C?style=flat-square" alt="Identity Security"/>
<img src="https://img.shields.io/badge/AZURE-2B5D8C?style=flat-square" alt="Azure"/>
<img src="https://img.shields.io/badge/AZURE_CLI-2B5D8C?style=flat-square" alt="Azure CLI"/>
<img src="https://img.shields.io/badge/KQL-2B5D8C?style=flat-square" alt="KQL"/>
<img src="https://img.shields.io/badge/NIST_800--53-2B5D8C?style=flat-square" alt="NIST 800-53"/>

</td>
</tr>

<tr>
<td align="left">

<h3><a href="PROJECT_LINK_2">Silent Spread</a> — Lateral Movement Threat Hunt</h3>

Hypothesis-driven hunt for lateral movement across a Windows estate using process and authentication telemetry.

<ul>
<li>Built the hypothesis from observed service account behavior, then queried to confirm or reject it</li>
<li>Correlated remote service creation with anomalous logon patterns across 40+ hosts</li>
<li>Converted the hunt query into a scheduled analytics rule with a measured false-positive rate</li>
</ul>

<img src="https://img.shields.io/badge/SECURITY_OPERATIONS-8C3A3A?style=flat-square" alt="Security Operations"/>
<img src="https://img.shields.io/badge/ON--PREMISES-8C3A3A?style=flat-square" alt="On-Premises"/>
<img src="https://img.shields.io/badge/SYSMON-8C3A3A?style=flat-square" alt="Sysmon"/>
<img src="https://img.shields.io/badge/SENTINEL-8C3A3A?style=flat-square" alt="Sentinel"/>
<img src="https://img.shields.io/badge/MITRE_ATT%26CK-8C3A3A?style=flat-square" alt="MITRE ATT&CK"/>

</td>
</tr>

<tr>
<td align="left">

<h3><a href="PROJECT_LINK_3">Enterprise Vulnerability Management</a> — Implementation</h3>

Deployed authenticated scanning across a Windows environment with a risk-based remediation workflow.

<ul>
<li>Onboarded 40+ hosts with credentialed scanning and validated coverage gaps</li>
<li>Built severity-based remediation SLAs tied to asset criticality</li>
<li>Proved patch effectiveness through automated rescan evidence</li>
</ul>

<img src="https://img.shields.io/badge/VULNERABILITY_MGMT-4A7350?style=flat-square" alt="Vulnerability Management"/>
<img src="https://img.shields.io/badge/ON--PREMISES-4A7350?style=flat-square" alt="On-Premises"/>
<img src="https://img.shields.io/badge/NESSUS-4A7350?style=flat-square" alt="Nessus"/>
<img src="https://img.shields.io/badge/POWERSHELL-4A7350?style=flat-square" alt="PowerShell"/>
<img src="https://img.shields.io/badge/CIS_BENCHMARKS-4A7350?style=flat-square" alt="CIS Benchmarks"/>

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
<tr><td>AWS</td><td><b>Solutions Architect – Associate (SAA-C03)</b></td><td>Cloud Architecture</td></tr>
</table>

---

<h2 align="center">Skills &amp; Tools</h2>

```ini
[Identity_Security]
Platforms    = Entra ID, Active Directory, Azure RBAC
Capabilities = Conditional Access, PIM, Access Reviews, Group Policy
Focus        = Privileged access, consent governance, tiered administration

[Security_Operations]
SIEM_EDR     = Microsoft Sentinel, Defender for Endpoint, Sysmon
Query        = KQL, PowerShell, Wireshark
Practice     = Threat hunting, log analysis, incident response
Frameworks   = MITRE ATT&CK

[Vulnerability_Management]
Scanning     = Tenable Nessus, Defender Vulnerability Management
Practice     = Authenticated scanning, risk-based remediation, patch validation
Standards    = CIS Benchmarks, DISA STIG, NIST 800-53

[Infrastructure_Foundation]
Systems      = Windows Server, Linux (RHEL, Ubuntu), Hyper-V, VMware ESXi
Networking   = VLANs, routing, ACLs, IPsec VPN, pfSense
Automation   = PowerShell, Python, Bash, Azure CLI
```
