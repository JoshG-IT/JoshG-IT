# ChatGPT Autofill Prompt (use this to generate similar reports on future findings)

```text
You are a cybersecurity analyst preparing a short, professional Markdown summary for a STIG or vulnerability finding.

Rules:
- Output valid Markdown only.
- Use clear, concise language suitable for documentation or GitHub.
- Keep the report brief — 1 page or less.
- Follow the structure below exactly.
- Include PowerShell or Bash commands if applicable.
- No emojis, icons, or decorative symbols.

Prepare a complete Markdown report using the template above based on the following finding details:

Finding details:
[Paste your notes: system(s), OS/version, component, tool plugins, exact settings, commands used, remediation steps (manual + automation), verification commands, severity, IDs, references, dates, and repository paths.]
```
---

## Overview
Windows 10 systems were found to allow unrestricted use of USB storage devices.  
This configuration introduces data exfiltration and malware infection risks and violates DISA STIG control V-220815, which mandates removable storage restriction for non-administrative users.

---

## Affected Systems
| System | OS | Component |
|--------|----|-----------|
| LAPTOP-01 | Windows 10 Pro 22H2 | Removable Storage |
| HR-PC-02 | Windows 10 Enterprise 21H2 | USB Ports |

---

## Detection
**Tool / Method:** Local Group Policy Review, PowerShell Verification  
**Evidence:**
```powershell
# Check if USB storage drivers are disabled
Get-ItemProperty -Path "HKLM:\SYSTEM\CurrentControlSet\Services\USBSTOR" | Select Start
```

**Result:**  
`Start : 3` → USB storage enabled (non-compliant)

---

## Remediation
**Steps:**
1. Open the Registry Editor or use PowerShell to modify the USBSTOR service.  
2. Set the `Start` value to `4` (Disabled).  
3. Reboot to apply changes.

**Command Example:**
```powershell
Set-ItemProperty -Path "HKLM:\SYSTEM\CurrentControlSet\Services\USBSTOR" -Name "Start" -Value 4
```

---

## Verification
Recheck the value:
```powershell
Get-ItemProperty -Path "HKLM:\SYSTEM\CurrentControlSet\Services\USBSTOR" | Select Start
```
**Expected Output:**  
`Start : 4` → USB storage disabled (compliant)

---

## Impact
| Confidentiality | Integrity | Availability |
|-----------------|------------|---------------|
| High | Medium | Low |

---

## References
- DISA STIG ID: V-220815  
- NIST 800-53 Control: AC-19 – Access Control for Portable Devices  
- Microsoft Docs: [Block USB Drives Using Group Policy or Registry](https://learn.microsoft.com/en-us/windows/client-management/usb-block-policy)
