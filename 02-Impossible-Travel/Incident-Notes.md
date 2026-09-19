# Incident Notes — Impossible Travel Investigation

## Alert Details
- **Alert Type:** Impossible Travel
- **User:** dev.user
- **Date:** 19-09-2026
- **Risk:** High
- **Lab Type:** Controlled / Simulated

## Timeline

| Time | Location | IP Address | Status |
|---|---|---|---|
| 10:00 AM | New Delhi, India | 103.21.45.10 | Successful Login |
| 10:20 AM | Mumbai, India | 49.36.120.25 | Successful Login |

## Investigation Observations
1. The same account successfully authenticated from two different locations.
2. The source IP addresses were different.
3. The locations were geographically distant.
4. The time difference between the two logins was 20 minutes.
5. The activity is suspicious and consistent with an Impossible Travel alert.
6. Different IP addresses alone do not confirm malicious activity.

## Validation
- User confirmation was not available in this lab.
- VPN/proxy evidence was not available.
- IP geolocation was not independently verified.
- No additional suspicious activity was provided in the simulated dataset.

## Final Assessment
**Inconclusive — Further Investigation Required**

The alert remains suspicious, but there is insufficient evidence to confirm account compromise.

## SOC L1 Recommended Actions
- Validate the activity with the user.
- Check VPN or proxy usage.
- Verify IP geolocation.
- Review additional authentication events.
- Check for other suspicious activity associated with the account.
- Escalate if additional evidence indicates compromise.

> All login data and IP addresses in this lab are simulated for training purposes.