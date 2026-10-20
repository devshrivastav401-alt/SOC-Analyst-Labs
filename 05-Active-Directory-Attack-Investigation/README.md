# Lab 05 — Windows Authentication and Account Discovery Investigation

## Objective

Review Windows endpoint telemetry related to local group enumeration, authentication failures, privileged logons, and PowerShell script block logging. Practise evidence collection, event correlation, and cautious SOC L1 assessment.

## Status and Scope

**Documentation status:** Completed  
**Environment:** Windows 10 Pro, standalone workstation  
**Domain state:** WORKGROUP; not joined to an Active Directory domain

This was a Windows endpoint investigation using AD-related concepts. It was **not** a test of an actual Active Directory domain, domain controller, or confirmed Active Directory attack.

## Investigation Focus

- Local account and group activity
- Failed authentication detection
- Successful-logon correlation
- Privileged logon context
- PowerShell Script Block Logging
- Timeline construction
- MITRE ATT&CK technique-aware analysis
- Evidence-based incident assessment

## Tools

- Windows Event Viewer
- Windows Security event log
- PowerShell
- GitHub and Markdown documentation

Splunk and SPL were not used in this lab.

## Workflow

1. Verify the endpoint and domain-join state.
2. Review local account and group context.
3. Examine Windows Security telemetry, including Event ID 4799.
4. Generate three controlled invalid-password attempts against the local Administrator account.
5. Review Event ID 4625 and its authentication status fields.
6. Check for a related successful Administrator logon using Event ID 4624.
7. Review Event ID 4672 in account context.
8. Review available PowerShell Event ID 4104 records.
9. Correlate timestamps and document the limitations of the evidence.
10. Write an incident assessment and recommended next steps.

## Findings

| Event ID | Observation | Assessment |
|---|---|---|
| 4799 | Local group membership enumeration was observed. | Consistent with discovery-related activity; benign in this lab context. |
| 4625 | Three controlled failed authentication attempts against the local Administrator account. | Expected results of the invalid-password test. |
| 4624 | No successful Administrator logon correlated with the controlled failures was identified. | No evidence from this review of a successful Administrator logon caused by the test. |
| 4672 | Reviewed privileged-logon activity was associated with SYSTEM. | Not evidence by itself of privilege escalation by the test user. |
| 4104 | PowerShell Script Block Logging was reviewed. | No clear malicious script activity was identified in the reviewed records. |

### Controlled Authentication Test

Three invalid-password attempts were made against the local `Administrator` account. The resulting Event ID 4625 records showed:

- **Status:** `0xC000006D`
- **Substatus:** `0xC000006A`
- **Logon type:** `2`
- **Source:** `::1` (IPv6 loopback)
- **Target account:** `Administrator`

These events demonstrate how controlled authentication failures can be located and assessed in Windows logs. They do not demonstrate a remote brute-force attack.

## Timeline

| Time | Event | Interpretation |
|---|---|---|
| 15:27:32 | 4799 | Local group membership enumeration |
| 15:27:38 | 4624 / 4672 | SYSTEM service/privileged activity; not correlated to the test failures |
| 15:32:32 | 4625 | First controlled failed Administrator authentication |
| 15:32:38 | 4625 | Second controlled failed Administrator authentication |
| 15:32:43 | 4625 | Third controlled failed Administrator authentication |
| 15:32:44 | 4672 | SYSTEM privileged activity |
| 15:41:22 | 4104 | Script Block Logging record reviewed |

Times are reproduced from the lab notes. They should be interpreted in the context of the local test environment.

## MITRE ATT&CK Context

- **T1087 — Account Discovery:** Local account/group enumeration is relevant to account discovery. In this exercise, the activity was generated during benign lab work and is not evidence of attacker activity.
- **T1059.001 — PowerShell:** PowerShell was used for event collection and analysis. PowerShell usage alone is not malicious; the reviewed activity did not reveal clear malicious execution.

Technique mapping describes behavioural relevance; it does not independently prove an attack.

## Final Assessment

**Assessment: Benign controlled lab activity; no confirmed compromise identified in the reviewed telemetry.**

The exercise demonstrated collection and review of Windows authentication, group-enumeration, privileged-logon, and PowerShell telemetry. Correlation helped distinguish the deliberately generated failed logons from unrelated SYSTEM activity.

This conclusion is limited to the records reviewed. It is not a claim that all possible endpoint activity was examined.

## Recommended Next Steps

1. Repeat the investigation in an isolated, genuine Active Directory lab when domain infrastructure is available.
2. Practise reviewing domain-controller and Kerberos events.
3. Learn SIEM fundamentals and later repeat relevant searches in Splunk after the tool has been studied.
4. Preserve screenshots or exported event details that support each key finding.
5. Continue documenting the difference between observed evidence, interpretation, and unverified hypotheses.

## Evidence and Related Files

- [Incident Notes](./Incident-Notes.md)
- [Incident Report](./Incident-Report.md)
- [Screenshots folder](./Screenshots/)

Only claim evidence that is actually uploaded and viewable in the repository.
