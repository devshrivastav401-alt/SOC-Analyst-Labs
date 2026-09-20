# 🛡️ SOC Analyst Labs

Hands-on SOC Analyst L1 investigation portfolio built through controlled cybersecurity labs using Windows Security Logs, authentication events, phishing analysis, and alert triage.

## 🎯 Objective

This repository documents practical SOC Analyst L1 skills through investigation-based labs.

The focus is on:

- Alert triage
- Log analysis
- Authentication investigation
- IOC identification
- Timeline analysis
- Evidence collection
- Incident documentation
- Evidence-based assessment
- Basic incident response

## 🧪 Completed Labs

| # | Lab | Main Skills |
|---|---|---|
| 01 | [Brute Force Investigation](./01-Brute-Force-Investigation/) | Windows Event ID 4625, failed-logon analysis, authentication triage |
| 02 | [Impossible Travel Investigation](./02-Impossible-Travel/) | Authentication logs, IP comparison, timeline analysis |
| 03 | [Phishing Investigation](./03-Phishing-Investigation/) | Email analysis, IOC extraction, phishing indicators |
| 04 | [Windows Event Analysis](./04-Windows-Event-Analysis/) | Event IDs 4625, 4624, 4688, 4104, 4672, 4648 |

## 🔍 Investigation Approach

Each lab follows a basic SOC L1 workflow:

1. Identify the alert or suspicious activity.
2. Collect relevant evidence.
3. Analyze logs, events, or indicators.
4. Build a timeline where applicable.
5. Validate the activity using available context.
6. Document findings.
7. Determine whether the evidence supports escalation.
8. Record recommended next steps.

## 🛠️ Tools & Technologies

- Windows Event Viewer
- Windows Security Logs
- Windows Event XML
- Windows Authentication Events
- Basic IOC Analysis
- Email/Phishing Analysis
- GitHub
- Markdown Documentation

## 📊 Event IDs Practiced

| Event ID | Description |
|---|---|
| 4625 | Failed Logon |
| 4624 | Successful Logon |
| 4688 | Process Creation |
| 4104 | PowerShell Script Block Logging |
| 4672 | Special Privileges Assigned |
| 4648 | Logon Using Explicit Credentials |

## 📁 Repository Structure

Each completed lab uses a consistent documentation pattern:

```text
LAB/
├── README.md
├── Incident-Notes.md
├── Incident-Report.md
└── Screenshots/
    └── evidence screenshots
```

The screenshots provide supporting evidence, while the notes and reports document the investigation and analyst assessment.

## 🔐 Security & Privacy

The repository is public and is designed for portfolio use.

- Lab scenarios are controlled or simulated unless explicitly stated otherwise.
- No real credentials, API keys, private keys, or authentication tokens are intentionally included.
- Simulated indicators are clearly identified in the relevant documentation.
- Sensitive personal or organizational information should not be added to future lab evidence.

## ⚠️ Disclaimer

These labs are created for cybersecurity learning and SOC Analyst L1 portfolio practice. Simulated scenarios and indicators are used where stated. The investigations should not be interpreted as reports of real-world incidents.

## 🚀 Current Learning Focus

After completing these investigation labs, the next focus areas are:

- SIEM fundamentals
- Splunk
- EDR concepts
- Alert investigation
- SOC L1 interview preparation
- Additional hands-on detection and investigation practice

---

**Portfolio:** SOC Analyst L1 Hands-on Investigation Labs  
**Status:** 4 Labs Completed ✅
