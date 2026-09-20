# 02 - Impossible Travel Investigation

## Objective

Investigate a simulated Impossible Travel alert as a SOC Analyst L1 and document the investigation using evidence.

## Scenario

A successful login for the same user account was observed from two geographically distant locations within a short time period.

## Investigation Workflow

**Objective → Evidence → Timeline → Validation → Assessment → Next Steps**

## Evidence Reviewed

| User | Date | Time | IP Address | Location | Status |
|---|---|---|---|---|---|
| dev.user | 19-09-2026 | 10:00 AM | 103.21.45.10 | New Delhi, India | Successful |
| dev.user | 19-09-2026 | 10:20 AM | 49.36.120.25 | Mumbai, India | Successful |

## Investigation Findings

- The same account was used for both successful logins.
- Source IP addresses are different.
- The listed locations are geographically distant.
- The time difference between the logins is 20 minutes.
- The activity matches the pattern that can trigger an Impossible Travel alert.
- Different IP addresses and locations alone do not confirm malicious activity.

## Analyst Assessment

**Status: Under Investigation**

The available simulated evidence is sufficient to document the alert, but it does not confirm account compromise.

Potential explanations that should be validated include:

- VPN or proxy use
- Inaccurate IP geolocation
- Shared-account activity
- Legitimate user travel or activity

## Recommended Next Steps

1. Validate the user's actual activity.
2. Check VPN/proxy and identity-provider context.
3. Review related successful and failed authentication events.
4. Check for additional suspicious account activity.
5. Escalate if supporting evidence indicates compromise.

## Evidence Files

- `Screenshots/02-impossible-travel-finding.png`
- `Screenshots/03-investigation-finding.png`
- `Screenshots/04-final-assessment.png`

## Skills Practiced

- Alert triage
- Authentication log analysis
- Timeline analysis
- IP comparison
- Impossible Travel investigation
- Evidence collection
- Avoiding premature incident confirmation
- Incident documentation

> This is a controlled/simulated lab created for SOC Analyst L1 portfolio practice. The IP addresses and login activity are simulated for training.