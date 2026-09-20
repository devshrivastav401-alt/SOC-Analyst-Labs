# 04 - Windows Event Analysis

## Objective

Analyze Windows Security Event Logs as a SOC L1 Analyst and investigate authentication, process, PowerShell, privilege, and credential-related events.

## Tools Used

- Windows Event Viewer
- Windows Security Logs
- Windows Event XML View

## Investigation Workflow

**Objective → Evidence → Event Analysis → Correlation → Assessment → Next Steps**

## Events Investigated

| Event ID | Purpose | Finding |
|---|---|---|
| 4625 | Failed Logon | 9 failed interactive logon events observed |
| 4624 | Successful Logon | SYSTEM service logon observed |
| 4688 | Process Creation | `lsass.exe` process creation observed |
| 4104 | PowerShell Script Block | No events found |
| 4672 | Special Privileges | No events found |
| 4648 | Explicit Credentials | Local explicit credential usage observed |

## Key Findings

- 9 Event ID 4625 records were identified.
- The investigated 4625 event showed Logon Type 2 (Interactive).
- The investigated 4625 event showed an incorrect-password status.
- No remote IP address was recorded in the investigated 4625 event.
- The 9 failed logons were distributed across different times rather than appearing as one short burst.
- Event ID 4624 showed a SYSTEM service logon (Logon Type 5).
- Event ID 4688 showed `lsass.exe` being created by `wininit.exe`.
- No Event ID 4104 or 4672 records were available in the investigated log.
- Event ID 4648 showed explicit credential usage in a local context.

## Analyst Assessment

The available evidence shows repeated failed interactive logon attempts, but the reviewed events do not establish a remote brute-force attack or successful compromise.

The Event ID 4688 observation was assessed from the event context available in this lab; an individual process-creation event should be correlated with additional endpoint and security telemetry before drawing a broader conclusion.

## Recommended Next Steps

- Continue monitoring failed authentication activity for frequency and clustering.
- Investigate any remote source IPs if they appear.
- Correlate suspicious successful logons with preceding failures.
- Review related process and PowerShell activity when available.
- Escalate when additional evidence indicates compromise.

## Evidence Files

- `Screenshots/01-event-4625-xml-analysis.png`
- `Screenshots/02-event-4624-successful-logon.png`
- `Screenshots/03-event-4688-process-creation.png`
- `Screenshots/04-initial-event-review.png`
- `Screenshots/05-event-4672-no-events.png`
- `Screenshots/06-event-4648-explicit-credentials.png`

## Skills Demonstrated

- Windows Event Viewer
- Windows Security Event Analysis
- Event ID Investigation
- XML Event Analysis
- Log Correlation
- SOC L1 Investigation
- Evidence Documentation
- Incident Assessment

> This is a controlled lab created for SOC Analyst L1 portfolio practice.