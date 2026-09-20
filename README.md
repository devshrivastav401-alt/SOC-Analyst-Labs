# 🛡️ SOC Analyst Labs

Hands-on SOC Analyst L1 investigation portfolio focused on practical alert triage, Windows event analysis, authentication investigations, phishing analysis, IOC identification, and incident documentation.

## 👋 Portfolio Overview

This repository demonstrates how I approach common SOC Analyst L1 investigation tasks using controlled lab scenarios and evidence-based analysis.

**4 investigation labs completed:** brute-force investigation, impossible-travel investigation, phishing investigation, and Windows event analysis.

### 🔎 What This Portfolio Demonstrates

- Alert triage and initial validation
- Windows Security Event analysis
- Authentication and failed-logon investigation
- IOC identification and phishing analysis
- Timeline and evidence correlation
- Analyst notes and incident reporting
- Evidence-based assessment and escalation decisions
- Basic incident-response workflow

## 🧪 Completed Labs

| # | Lab | Key Skills | Evidence |
|---|---|---|---|
| 01 | [Brute Force Investigation](./01-Brute-Force-Investigation/) | Event ID 4625, failed-logon analysis, authentication triage | Screenshots + notes + report |
| 02 | [Impossible Travel Investigation](./02-Impossible-Travel/) | Authentication logs, IP comparison, timeline analysis | Screenshots + notes + report |
| 03 | [Phishing Investigation](./03-Phishing-Investigation/) | Email analysis, IOC extraction, phishing indicators | Screenshots + notes + report |
| 04 | [Windows Event Analysis](./04-Windows-Event-Analysis/) | Event IDs 4625, 4624, 4688, 4104, 4672, 4648 | Screenshots + notes + report |

**Recommended starting point:** [Lab 01 — Brute Force Investigation](./01-Brute-Force-Investigation/)

## 🔍 Investigation Workflow

Each lab follows a repeatable SOC L1 workflow:

1. Identify the alert or suspicious activity.
2. Collect relevant evidence.
3. Analyze logs, events, or indicators.
4. Build a timeline where applicable.
5. Validate the activity using available context.
6. Document observations and findings.
7. Assess whether the available evidence supports escalation.
8. Record recommended next steps and limitations.

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

## 📁 Lab Documentation Structure

Each completed lab uses a consistent structure:

```text
LAB/
├── README.md
├── Incident-Notes.md
├── Incident-Report.md
└── Screenshots/
    └── evidence screenshots
```

- **README.md** — lab objective, workflow, and evidence overview
- **Incident-Notes.md** — investigation observations and analyst reasoning
- **Incident-Report.md** — concise incident summary, findings, assessment, and next steps
- **Screenshots/** — supporting visual evidence

## 🔐 Security & Privacy

The repository is public and designed for portfolio use.

- Lab scenarios are controlled or simulated unless explicitly stated otherwise.
- No real credentials, API keys, private keys, or authentication tokens are intentionally included.
- Simulated indicators are clearly identified in the relevant documentation.
- Sensitive personal or organizational information should not be added to future lab evidence.

## ⚠️ Disclaimer

These labs are created for cybersecurity learning and SOC Analyst L1 portfolio practice. Simulated scenarios and indicators are used where stated. The investigations should not be interpreted as reports of real-world incidents.

## 🚀 Current Learning Focus

Next areas of practice:

- SIEM fundamentals
- Splunk
- EDR concepts
- Alert investigation
- SOC L1 interview preparation
- Additional hands-on detection and investigation practice

---

**Portfolio:** SOC Analyst L1 Hands-on Investigation Labs  
**Status:** 4 Labs Completed ✅
