# 🚨 Incident Report — Brute Force Investigation

## 1. Incident Summary
A controlled Windows authentication investigation was performed to identify and analyze repeated failed logon activity.

The investigation focused on Windows Security Event ID **4625** and the associated authentication fields.

## 2. Detection
- **Alert Type:** Failed Authentication / Brute Force Investigation
- **Event ID:** 4625
- **Logon Type:** 2 — Interactive
- **Environment:** Windows Security Event Logs
- **Lab Classification:** Controlled / Simulated

## 3. Evidence

Four Event ID 4625 records were observed:

| Time | Event ID | Logon Type | Source Address |
|---|---:|---:|---|
| 7:44:57 PM | 4625 | 2 | 127.0.0.1 |
| 7:44:57 PM | 4625 | 2 | 127.0.0.1 |
| 7:59:32 PM | 4625 | 2 | 127.0.0.1 |
| 7:59:32 PM | 4625 | 2 | 127.0.0.1 |

The investigated event showed:
- Status: `0xC000006D`
- Sub Status: `0xC0000380`
- Logon Process: `User32`
- Authentication Package: `Negotiate`
- Process: `C:\Windows\System32\svchost.exe`

## 4. Analysis
The Event ID 4625 records confirm failed authentication attempts.

The two pairs of events were approximately 15 minutes apart, and the source address was `127.0.0.1`. Because the activity was intentionally generated during a controlled lab exercise, the events should not be interpreted as evidence of a real attack.

A production brute-force investigation would require correlation with account information, event frequency, source IPs, successful logons, and other surrounding telemetry.

## 5. Analyst Assessment
The investigation demonstrates detection of repeated failed authentication activity.

The available evidence does **not** establish:
- A confirmed remote brute-force attack
- A confirmed attacker login
- Account compromise
- Unauthorized activity

## 6. Recommended Monitoring
Continue monitoring for:
- Increasing failed-logon frequency
- Short bursts of repeated failures
- Remote source IP addresses
- Successful logons following repeated failures
- Multiple affected accounts
- Other suspicious authentication activity

## 7. Final Conclusion
**Assessment: Controlled lab activity — repeated failed logons detected.**

The investigation demonstrates how a SOC L1 analyst can identify Event ID 4625, review authentication fields, examine event frequency, and avoid classifying suspicious activity as malicious without sufficient supporting evidence.

## 8. Evidence
Supporting screenshots:
- `screenshots/01-event-4625-failed-logon.png`
- `screenshots/02-multiple-4625-events.png`

> **Lab Classification:** Controlled / Simulated training exercise. No real brute-force attack or account compromise is claimed.
