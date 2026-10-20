# SOC Analyst L1 Investigation Portfolio

A collection of controlled, simulated investigations documenting foundational SOC Analyst Level 1 workflows, including Windows authentication analysis, phishing triage, suspicious-login review, and incident reporting.

## Portfolio Overview

This repository demonstrates a structured approach to reviewing security telemetry, validating suspicious activity, documenting evidence, and making appropriately cautious assessments. The scenarios are for learning and portfolio practice; they are not claims of real-world incidents.

**Current status:** Five investigation folders are documented. Splunk has **not** been started and is listed as a planned next lab.

## Investigation Labs

| # | Investigation | Focus | Status |
|---|---|---|---|
| 01 | [Brute Force Investigation](./01-Brute-Force-Investigation/) | Windows Event ID 4625, failed-logon analysis, authentication triage | Documented lab |
| 02 | [Impossible Travel Investigation](./02-Impossible-Travel/) | Simulated sign-ins, location/time comparison, validation and escalation criteria | Documented lab |
| 03 | [Phishing Investigation](./03-Phishing-Investigation/) | Email indicators, lookalike domains, suspicious URL analysis, user-impact validation | Documented lab |
| 04 | [Windows Event Analysis](./04-Windows-Event-Analysis/) | Windows Security events, process creation, authentication context and telemetry limitations | Documented lab |
| 05 | [Windows Authentication and Account Discovery Investigation](./05-Active-Directory-Attack-Investigation/) | Local account/group activity, Event IDs 4799/4625/4624/4672/4104, timeline correlation | Documentation completed; standalone Windows host |

> **Lab 05 environment limitation:** The workstation was in a WORKGROUP and was not joined to an Active Directory domain. It must not be presented as a real Active Directory attack or domain compromise.

## Investigation Workflow

The labs use a repeatable workflow where applicable:

1. Define the alert or investigation question.
2. Identify the available log sources and environment.
3. Collect relevant events and indicators.
4. Review timestamps, accounts, source information, and event context.
5. Correlate related activity without assuming that nearby events are connected.
6. Record findings, uncertainty, and evidence limitations.
7. Assess whether the evidence supports escalation.
8. Document recommended next steps.

## Tools and Concepts Practised

- Windows Event Viewer
- Windows Security and PowerShell Operational logs
- PowerShell for local event review and collection
- Windows authentication event analysis
- Basic phishing indicator analysis
- Timeline construction and incident documentation
- Markdown and GitHub

**Not yet practised in this repository:** Splunk, Search Processing Language (SPL), and SIEM-based log ingestion/correlation. These are planned learning goals, not completed experience.

## Windows Event IDs Referenced

| Event ID | Meaning |
|---|---|
| 4624 | Successful logon |
| 4625 | Failed logon |
| 4648 | Logon using explicit credentials |
| 4672 | Special privileges assigned to a new logon |
| 4688 | Process creation |
| 4799 | Security-enabled local group membership enumeration |
| 4104 | PowerShell script block logging |

An event ID alone does not establish malicious activity. Findings must be assessed using event details, host and account context, surrounding telemetry, and the limitations of the available data.

## Lab Documentation

Where present, each lab contains:

```text
LAB/
├── README.md
├── Incident-Notes.md
├── Incident-Report.md
└── Screenshots/
```

- **README.md** — objective, scope, workflow, and findings overview
- **Incident-Notes.md** — detailed observations and analyst reasoning
- **Incident-Report.md** — concise summary, assessment, and recommended actions
- **Screenshots/** — supporting evidence, where captured and uploaded

Check each lab's folder for the evidence actually available; the presence of a documentation link alone does not imply that screenshots are present.

## Planned Next Lab

**Lab 06 — Splunk SIEM Investigation (not started)**

Planned work includes learning basic SPL, ingesting or using suitable Windows event data, running searches, investigating authentication activity, and documenting results with evidence. This lab will be marked in progress only after practical work begins.

## Security and Scope

- Scenarios are simulated or controlled unless explicitly stated otherwise.
- No real-world incident or account compromise is claimed.
- Do not upload passwords, tokens, private keys, or sensitive personal or organizational data.
- Simulated IP addresses, identities, and indicators should be labelled as such.
- Conclusions should not exceed what the available evidence supports.

## Career Focus

The portfolio supports continued preparation for entry-level SOC Analyst roles. Next priorities are hands-on SIEM practice, improving evidence quality, and continuing alert-triage and incident-response exercises.
