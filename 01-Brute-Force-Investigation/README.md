# 01 - Brute Force Investigation

## Objective

Investigate failed Windows logon activity, validate failed-logon auditing, and determine whether the observed activity provides evidence of a brute-force attack.

## Environment

- Windows Security Event Logs
- Windows Event Viewer
- Local Security Policy
- Audit Logon Events: Success + Failure
- Controlled lab activity

## Investigation Workflow

1. Review Windows Security logs.
2. Enable auditing for logon events.
3. Apply the policy with `gpupdate /force`.
4. Generate a controlled failed logon.
5. Identify Event ID 4625.
6. Analyze authentication and network fields.
7. Generate additional controlled failures and compare events.
8. Document findings and response considerations.

## Completed Steps

### 1. Audit Configuration

**Audit Logon Events** was configured for:

- Success
- Failure

The policy was successfully applied using:

`gpupdate /force`

### 2. Controlled Failed Logons

Controlled incorrect-password attempts were generated on the Windows host to validate failed-logon auditing and practice investigating repeated authentication failures.

### 3. Event ID 4625 Identified

Windows Security Event ID **4625** was observed.

Key fields from the investigated events:

| Field | Observed Value |
|---|---|
| Event ID | 4625 |
| Task Category | Logon |
| Keywords | Audit Failure |
| Logon Type | 2 (Interactive) |
| Status | `0xC000006D` |
| Sub Status | `0xC0000380` |
| Source Network Address | `127.0.0.1` |
| Logon Process | User32 |
| Authentication Package | Negotiate |
| Process | `C:\Windows\System32\svchost.exe` |

## Investigation Findings

Four Event ID 4625 records were observed during the controlled test.

| Time | Event ID | Logon Type | Source Address |
|---|---:|---:|---|
| 7:44:57 PM | 4625 | 2 | 127.0.0.1 |
| 7:44:57 PM | 4625 | 2 | 127.0.0.1 |
| 7:59:32 PM | 4625 | 2 | 127.0.0.1 |
| 7:59:32 PM | 4625 | 2 | 127.0.0.1 |

The events occurred in two pairs approximately 15 minutes apart. The source address was `127.0.0.1`, indicating that the authentication activity originated from the local host rather than an external network source.

The investigated event showed:

- **Logon Type 2:** interactive/local logon
- **Status `0xC000006D`:** failed logon
- **Authentication Package:** Negotiate
- **Process:** `svchost.exe`

## Analysis

The repeated 4625 events demonstrate how a SOC analyst can identify and investigate failed authentication activity.

However, these events were intentionally generated as part of a controlled lab exercise. Therefore, they **do not represent a confirmed brute-force attack**.

A real brute-force investigation would require additional context such as:

- Higher-frequency repeated failures
- Target account information
- Source IP reputation and ownership
- Successful logon following repeated failures
- Multiple affected accounts
- Authentication patterns over time
- Confirmation that the activity was unauthorized

This lab demonstrates the distinction between **detecting repeated authentication failures** and **confirming malicious activity**.

## Evidence

- `Screenshots/01-event-4625-failed-logon.png`
- `Screenshots/02-multiple-4625-events.png`

## Final Conclusion

**Finding:** Repeated failed logon events were detected and successfully investigated.

**Classification:** Controlled lab activity — not a confirmed brute-force attack.

**Key SOC lesson:** An authentication alert should be validated with context before being classified as a security incident.

## Skills Practiced

- Windows Event Viewer
- Security log analysis
- Event ID 4625 investigation
- Authentication event analysis
- Frequency and timeline analysis
- Basic alert triage
- Evidence collection
- Incident documentation
