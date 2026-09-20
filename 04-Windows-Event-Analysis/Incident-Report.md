# 🚨 Incident Report — Windows Event Analysis

## 1. Executive Summary
A Windows Security Log investigation was performed to identify potentially suspicious authentication and process activity.

The investigation focused on Windows Security Event IDs 4625, 4624, 4688, 4104, 4672, and 4648.

Multiple failed interactive logon attempts were identified. However, the available evidence did not establish a remote brute-force attack or successful compromise.

## 2. Investigation Scope
**Host:** Dev  
**Log Source:** Windows Security  
**Primary Tool:** Windows Event Viewer

## 3. Timeline and Findings

### Event 4625 — Failed Logon
Nine failed logon events were observed. The attempts were distributed across different times rather than appearing as one short burst.

The investigated event showed:
- Logon Type: 2 — Interactive
- SubStatus: `0xc000006a` — incorrect password
- No source IP recorded

### Event 4624 — Successful Logon
A successful SYSTEM service logon was observed:
- Logon Type: 5
- Process: `services.exe`

This was assessed as service activity rather than a successful interactive user login.

### Event 4688 — Process Creation
An `lsass.exe` process creation event was observed with:
- Parent process: `C:\Windows\System32\wininit.exe`
- Command Line: blank

The event was not considered suspicious based on this event alone.

### Event 4104 — PowerShell
No matching events were found.

### Event 4672 — Special Privileges
No matching events were found.

### Event 4648 — Explicit Credentials
Explicit credential usage was observed in a local context:
- Target server: `localhost`
- Process: `lsass.exe`
- No remote IP recorded

The event alone does not establish credential theft or malicious activity.

## 4. Analyst Assessment
The observed failed logons represent repeated incorrect-password attempts.

The available evidence does not demonstrate:
- A confirmed remote brute-force attack
- A confirmed successful attacker login
- Confirmed credential theft
- Confirmed malicious process execution

## 5. Recommended Monitoring
Continue monitoring for:
- Increasing failed-logon frequency
- Short bursts of repeated authentication failures
- Remote source IP addresses
- Successful logons following repeated failures
- Unusual PowerShell activity
- Suspicious process creation
- Privileged-account activity

## 6. Final Conclusion
**Assessment: No confirmed compromise based on the reviewed evidence.**

The investigation demonstrates Windows Security Event analysis, event correlation, documentation of missing telemetry, and evidence-based SOC L1 assessment.

## 7. Evidence
Supporting screenshots are stored in the `Screenshots/` directory.
