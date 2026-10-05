# 🛡️ Lab 05 — Active Directory Attack Investigation

## 🎯 Objective

Perform a SOC Analyst L1 investigation of authentication, account discovery, group enumeration, privileged logon activity, and PowerShell telemetry using Windows endpoint logs.

> **Lab status:** ✅ Completed

> **Environment note:** The test workstation was confirmed to be **WORKGROUP / not domain-joined**. Therefore, this lab is documented as an **AD-style Windows authentication and discovery investigation**, not as a confirmed Active Directory attack or compromise.

## 🔎 Investigation Focus

- Windows authentication analysis
- Local account and group activity
- Failed authentication detection
- Successful-logon correlation
- Privileged logon analysis
- PowerShell Script Block Logging
- IOC identification
- Timeline correlation
- MITRE ATT&CK mapping
- Evidence-based incident assessment

## 🛠️ Tools

- Windows Event Viewer
- Windows Security Event Log
- PowerShell
- GitHub
- Markdown Documentation

## 📋 Investigation Workflow

1. Check the endpoint and domain state.
2. Identify local users and groups.
3. Review recent Windows Security telemetry.
4. Investigate Event ID 4799 for group enumeration.
5. Generate controlled failed authentication attempts.
6. Analyze Event ID 4625.
7. Check Event ID 4624 for successful-logon correlation.
8. Review Event ID 4672 for privileged activity.
9. Review PowerShell Event ID 4104 Script Block Logging.
10. Correlate events into a timeline.
11. Map relevant behavior to MITRE ATT&CK.
12. Produce an evidence-based final assessment.

## 🧪 Investigation Results

| Event ID | Finding | Assessment |
|---|---|---|
| **4799** | Local group membership enumeration | 🟢 Benign in lab context |
| **4625** | 3 controlled failed Administrator authentications | 🟡 Simulated detection activity |
| **4624** | No correlated successful Administrator logon | 🟢 No evidence of successful compromise |
| **4672** | SYSTEM privileged logon activity | 🟢 Normal SYSTEM activity |
| **4104** | PowerShell Script Block Logging reviewed | 🟢 No clear malicious activity identified |

### Authentication Test

Three intentionally invalid password attempts were made against the local `Administrator` account using:

`runas /user:DEV\\Administrator cmd`

The resulting Event ID 4625 records showed:

- **Status:** `0xC000006D`
- **SubStatus:** `0xC000006A`
- **Logon Type:** 2
- **Source:** `::1`
- **Target:** `Administrator`

This demonstrates how a SOC analyst can validate Windows authentication-failure telemetry in a controlled environment.

## 🧠 Analyst Takeaways

- Do not treat every 4625 as an attack; establish context and look for patterns.
- Do not correlate unrelated 4624 events simply because they occur near a 4625.
- Event 4672 does not automatically mean privilege escalation.
- Event 4104 does not automatically mean malicious PowerShell.
- Domain status must be verified before claiming an Active Directory compromise.
- Evidence-based correlation is more important than isolated event IDs.

## 📸 Evidence

The investigation includes screenshots documenting:

- Environment/domain verification
- Local group enumeration
- Failed authentication events
- Successful authentication correlation check
- Privileged logon analysis
- PowerShell Operational logging

See the `Screenshots/` directory for evidence.

## 📁 Documentation

- [Incident Notes](./Incident-Notes.md)
- [Incident Report](./Incident-Report.md)
- [Screenshots](./Screenshots/)

## 🔐 Security & Privacy

Only controlled lab activity and non-sensitive endpoint telemetry should be documented. Never upload passwords, access tokens, API keys, personal account identifiers, or sensitive organizational information.

---

**Portfolio:** SOC Analyst L1 Hands-on Investigation Labs  
**Status:** Completed ✅
