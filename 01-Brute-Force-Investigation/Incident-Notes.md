# 📝 Incident Notes — Brute Force Investigation

## Alert Details
- **Alert Type:** Failed Authentication / Brute Force Investigation
- **Event ID:** 4625
- **Logon Type:** 2 — Interactive
- **Lab Type:** Controlled / Simulated

## Audit Configuration
Audit Logon Events was configured for:
- Success
- Failure

The policy was applied using:

`gpupdate /force`

## Investigation Observations

Four Event ID 4625 records were observed during the controlled test.

| Time | Event ID | Logon Type | Source Address |
|---|---:|---:|---|
| 7:44:57 PM | 4625 | 2 | 127.0.0.1 |
| 7:44:57 PM | 4625 | 2 | 127.0.0.1 |
| 7:59:32 PM | 4625 | 2 | 127.0.0.1 |
| 7:59:32 PM | 4625 | 2 | 127.0.0.1 |

The events appeared in two pairs approximately 15 minutes apart.

### Key Event Fields

| Field | Observed Value |
|---|---|
| Event ID | 4625 |
| Task Category | Logon |
| Keywords | Audit Failure |
| Logon Type | 2 — Interactive |
| Status | `0xC000006D` |
| Sub Status | `0xC0000380` |
| Source Network Address | `127.0.0.1` |
| Logon Process | User32 |
| Authentication Package | Negotiate |
| Process | `C:\Windows\System32\svchost.exe` |

## Analysis
The events demonstrate repeated failed authentication activity. The source address was `127.0.0.1`, indicating activity from the local host in this controlled exercise.

The observed activity does **not** establish a confirmed brute-force attack because:
- The activity was intentionally generated for the lab.
- The failures were not observed as a sustained high-frequency burst.
- The source was local rather than a remote address.
- No successful attacker login was established.

## Validation
A real SOC investigation would require additional context such as:
- Target account information
- Authentication frequency over a longer period
- Remote source IP information
- Successful logons following failures
- Multiple affected accounts
- User confirmation or other evidence of unauthorized activity

## Final Assessment
**Controlled Lab Activity — Repeated Failed Logons Detected**

The evidence is sufficient to demonstrate Event ID 4625 investigation, but not to classify the activity as a confirmed brute-force attack.

## SOC L1 Recommended Actions
- Continue monitoring failed authentication events.
- Correlate repeated failures with successful logons.
- Investigate remote source addresses when present.
- Review affected accounts and authentication patterns.
- Escalate when supporting evidence indicates unauthorized activity.

> All activity in this lab was intentionally generated for cybersecurity training.
