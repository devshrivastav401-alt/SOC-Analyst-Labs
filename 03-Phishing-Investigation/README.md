# 03 - Phishing Investigation

## Objective

Investigate a simulated phishing email as a SOC Analyst L1 and document the investigation using evidence.

## Scenario

A suspicious email was reported for the user **dev.user**. The message claimed the user's Microsoft account would be suspended and included a suspicious login link.

## Investigation Workflow

**Objective → Evidence → IOC Extraction → Validation → Assessment → Response**

## Evidence Reviewed

| Field | Value |
|---|---|
| User | dev.user |
| Date | 19-09-2026 |
| Time | 09:15 AM |
| Alert Type | Phishing |
| Risk | High |
| Sender | security-alert@micr0soft-support.com |
| Subject | Urgent: Your Microsoft Account Will Be Suspended |
| Attachment | None |

## Investigation Findings

- The sender uses a lookalike domain with **"0" replacing "o"** in "micr0soft".
- The email uses urgency and fear to pressure the user.
- A suspicious login URL is included.
- The URL uses a suspicious impersonation-style domain.
- The indicators are consistent with credential harvesting.
- Multiple social-engineering techniques were identified.

## Extracted IOCs

| Type | Indicator |
|---|---|
| Email Address | security-alert@micr0soft-support.com |
| Domain | micr0soft-account-verify.com |
| URL | http://micr0soft-account-verify.com/login |

## Analyst Assessment

**Likely phishing attempt — investigation required**

The available simulated evidence supports treating the email as a potential phishing attempt. User interaction and account compromise are **not confirmed** in this lab.

## Recommended SOC L1 Actions

1. Do not open the suspicious link.
2. Quarantine or remove the email.
3. Check whether the user clicked the link.
4. Check whether credentials were submitted.
5. Review related authentication activity.
6. Block confirmed malicious indicators according to organizational process.
7. Escalate if additional evidence indicates compromise.

## Evidence Files

- `Screenshots/01-phishing-indicators.png`
- `Screenshots/02-ioc-extraction.png`
- `Screenshots/03-email-analysis.png`
- `Screenshots/04-final-assessment.png`

## Skills Practiced

- Phishing alert triage
- Email analysis
- Social-engineering identification
- IOC extraction
- Suspicious URL analysis
- Evidence collection
- Incident documentation
- Basic incident response

> This is a controlled/simulated lab created for SOC Analyst L1 portfolio practice. The email, domains, URL, and activity are simulated for training purposes.