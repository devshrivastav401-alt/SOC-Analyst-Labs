# 02 - Impossible Travel Investigation

## Objective

Investigate a simulated Impossible Travel alert as a SOC Analyst L1 and document the investigation using evidence.

## Scenario

A successful login for the same user account was observed from two geographically distant locations within a very short time period.

## Simulated Login Events

| User | Date | Time | IP Address | Location | Status |
|---|---|---|---|---|---|
| dev.user | 19-09-2026 | 10:00 AM | 103.21.45.10 | New Delhi, India | Successful |
| dev.user | 19-09-2026 | 10:20 AM | 49.36.120.25 | Mumbai, India | Successful |

## Investigation

- Same account used for both logins.
- Source IP addresses are different.
- Locations are geographically distant.
- Time difference between successful logins is 20 minutes.
- The activity is suspicious for an Impossible Travel alert.
- Different IP addresses support the alert, but IP difference alone does not confirm malicious activity.

## Current Status

**Under Investigation**

The alert is not treated as confirmed account compromise. Further validation is required, including checking for VPN/proxy use, inaccurate IP geolocation, shared-account activity, or legitimate user activity.

## Evidence

- `Screenshots/02-impossible-travel-finding.png`
- `Screenshots/03-investigation-finding.png`
- `Screenshots/04-final-assessment.png`

## SOC L1 Skills Practiced

- Alert triage
- Authentication log analysis
- Timeline analysis
- IP comparison
- Impossible Travel investigation
- Evidence collection
- Avoiding premature incident confirmation

> This is a controlled/simulated lab created for SOC Analyst L1 portfolio practice. The IP addresses and login activity are simulated for training.
