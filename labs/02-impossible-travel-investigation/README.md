# Lab 02 — Impossible Travel Investigation

## Objective
Investigate a simulated Impossible Travel alert as a SOC Analyst L1.

## Scenario
A successful login for the same user account was observed from two geographically distant locations within a very short time period.

## Simulated Login Events

| User | Date | Time | IP Address | Location | Status |
|---|---|---|---|---|---|
| dev.user | 19-09-2026 | 10:00 AM | 103.21.45.10 | New Delhi, India | Successful |
| dev.user | 19-09-2026 | 10:20 AM | 49.36.120.25 | Mumbai, India | Successful |

## Initial Investigation

- Same account used for both logins.
- Source IP addresses are different.
- Locations are geographically distant.
- Time difference between successful logins is 20 minutes.
- The activity therefore triggers a suspicious Impossible Travel assessment.

## IP Investigation

The two source IP addresses are different. Different source IPs support the Impossible Travel alert, but IP difference alone does not confirm malicious activity.

**Important:** The IP addresses and login activity in this lab are simulated for training purposes.

## Current Status

**Under Investigation**

The alert is not treated as confirmed account compromise. Further validation is required, including checking whether VPN/proxy use, inaccurate IP geolocation, shared-account activity, or legitimate user activity could explain the alert.

## SOC L1 Skills Practiced

- Alert triage
- Authentication log analysis
- Timeline analysis
- IP comparison
- Impossible Travel investigation
- Evidence collection
- Avoiding premature incident confirmation

## Evidence

- 02-login-events.png
- 03-investigation-finding.png

> This lab is a controlled/simulated investigation created for SOC Analyst L1 portfolio practice.
