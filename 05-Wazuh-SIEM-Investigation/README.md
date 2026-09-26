# 🛡️ Lab 05 — Wazuh SIEM Investigation

## 🎯 Objective

Perform a SOC Analyst L1 investigation using Wazuh SIEM to collect, triage, analyze, and document security events from a Windows endpoint.

## 🔎 Investigation Focus

- SIEM alert triage
- Windows endpoint log analysis
- Authentication/security event investigation
- Alert severity and rule analysis
- IOC identification
- Timeline correlation
- Evidence-based incident assessment

## 🧪 Scenario

A Windows endpoint generates suspicious security activity. The analyst uses Wazuh to review alerts and endpoint telemetry, identify relevant events, correlate evidence, and document the investigation.

> **Lab status:** In Progress

## 🛠️ Tools

- Wazuh
- Wazuh Dashboard
- Windows Event Logs
- Windows endpoint
- GitHub

## 📋 Investigation Workflow

1. Generate or identify controlled security activity.
2. Confirm the Windows endpoint is reporting to Wazuh.
3. Review Wazuh alerts.
4. Filter alerts by time, rule, level, and endpoint.
5. Inspect the underlying event details.
6. Identify relevant indicators and event IDs.
7. Build an investigation timeline.
8. Determine whether the activity appears benign, suspicious, or requires escalation based on available evidence.
9. Document findings and limitations.
10. Capture screenshots as evidence.

## 📸 Evidence

Screenshots will document:
- Wazuh dashboard/agent status
- Relevant security alert
- Alert details and rule information
- Underlying event/log data
- Investigation timeline or filtered results
- Final assessment

## 📁 Documentation

- [Incident Notes](./Incident-Notes.md)
- [Incident Report](./Incident-Report.md)
- [Screenshots](./Screenshots/)

## 🔐 Security & Privacy

All activity should be performed in a controlled lab environment. Do not include real credentials, tokens, private IP information that should remain private, or sensitive organizational data.

---
**Portfolio:** SOC Analyst L1 Hands-on Investigation Labs  
**Status:** In Progress 🚧
