# Incident Report — Impossible Travel Investigation

## 1. Incident Summary
A simulated Impossible Travel alert was investigated for the account **dev.user**. Two successful logins were observed from New Delhi and Mumbai within a 20-minute period.

## 2. Detection
- **Alert:** Impossible Travel
- **User:** dev.user
- **Date:** 19-09-2026
- **Risk:** High
- **Detection Basis:** Geographically distant successful logins within a very short time interval.

## 3. Evidence
- Login 1: 10:00 AM — New Delhi — 103.21.45.10
- Login 2: 10:20 AM — Mumbai — 49.36.120.25
- Both authentication attempts were successful.
- Two different source IP addresses were observed.

## 4. Analysis
The 20-minute gap between the two geographically distant logins makes the activity suspicious for Impossible Travel.

However, the alert does not by itself prove account compromise. Possible legitimate or detection-related explanations include VPN/proxy use, inaccurate IP geolocation, shared-account usage, or legitimate activity.

## 5. Finding
**Initial Finding: Suspicious — Under Investigation**

The evidence supports the Impossible Travel alert, but there is insufficient evidence in this simulated dataset to confirm malicious activity or account compromise.

## 6. Recommended Response
1. Validate the activity with the user.
2. Check VPN/proxy and IP geolocation information.
3. Review additional authentication events around the alert.
4. Check for other suspicious activity associated with the account.
5. Escalate to the appropriate analyst/team if additional evidence indicates compromise.

## 7. SOC L1 Lesson
An Impossible Travel alert should be treated as an investigation lead, not automatically as a confirmed incident. SOC L1 should validate the timeline, source information, user context, and supporting evidence before escalating.

> **Lab Classification:** Controlled / Simulated training exercise. No real account compromise is claimed.
