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

### 2. Controlled Failed Logon
A controlled incorrect-password attempt was generated on the Windows host to validate that failed-logon auditing was working.

### 3. Event ID 4625 Identified
Windows Security Event ID **4625** was observed.

Key fields from the controlled event:

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

## Initial Analysis

Event ID 4625 indicates that a logon request failed.

The observed event was generated intentionally as part of a controlled lab test. The source address was `127.0.0.1`, indicating localhost rather than an external source.

Therefore, **this single event does not establish that a brute-force attack occurred**. It confirms that Windows failed-logon auditing is functioning and provides an event that can be investigated using authentication, source, timestamp, and process information.

## Evidence

Screenshot evidence will be added to the `screenshots/` folder.

Recommended evidence filename:

`01-event-4625-failed-logon.png`

## Next Investigation Step

Generate a small number of additional controlled failed logons and compare the resulting 4625 events for:

- Timestamp
- Target account
- Logon type
- Source address
- Failure reason
- Frequency/pattern

The goal is to practice distinguishing isolated authentication failures from repeated suspicious activity.

## Skills Practiced
- Windows Event Viewer
- Security log analysis
- Event ID 4625 investigation
- Authentication event analysis
- Basic alert triage
- Evidence collection
- Incident documentation
