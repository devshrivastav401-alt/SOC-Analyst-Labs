# Incident Notes — Phishing Investigation

## Alert Details
- **Alert Type:** Phishing
- **User:** dev.user
- **Date:** 19-09-2026
- **Time:** 09:15 AM
- **Risk:** High
- **Lab Type:** Controlled / Simulated

## Investigation Observations
1. The sender domain uses a lookalike spelling: `micr0soft-support.com`.
2. The email creates urgency by threatening account suspension.
3. The email contains a suspicious login URL.
4. The URL uses a suspicious domain designed to resemble a trusted service.
5. The email uses multiple social-engineering techniques.
6. The link could potentially be used for credential harvesting.

## Extracted Indicators

| Type | Indicator | Reason |
|---|---|---|
| Email Address | security-alert@micr0soft-support.com | Suspicious lookalike sender |
| Domain | micr0soft-account-verify.com | Suspicious impersonation domain |
| URL | http://micr0soft-account-verify.com/login | Potential credential-harvesting URL |

## Final Assessment
**Likely Phishing Attempt — Investigation Required**

The available simulated evidence strongly supports treating the email as a potential phishing attempt. Further validation is required to determine whether the user interacted with the email or submitted credentials.

## Recommended SOC L1 Actions
- Do not open the suspicious link.
- Quarantine or remove the email.
- Check whether the user clicked the link.
- Check whether credentials were submitted.
- Review related authentication activity.
- Block confirmed malicious indicators.
- Escalate if additional evidence indicates account compromise.

> All email data, domains, and URLs in this lab are simulated for training purposes.