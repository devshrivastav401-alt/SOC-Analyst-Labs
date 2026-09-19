# Incident Report — Phishing Investigation

## 1. Incident Summary
A simulated phishing alert was investigated for the account **dev.user**. The email used a suspicious lookalike sender domain, urgent language, and a login URL that could potentially be used for credential harvesting.

## 2. Detection
- **Alert:** Phishing
- **User:** dev.user
- **Date:** 19-09-2026
- **Time:** 09:15 AM
- **Risk:** High
- **Detection Basis:** Suspicious sender domain, urgent account-suspension message, and suspicious login URL.

## 3. Evidence
- Sender: `security-alert@micr0soft-support.com`
- Suspicious domain: `micr0soft-account-verify.com`
- Suspicious URL: `http://micr0soft-account-verify.com/login`
- No attachment was present.
- Multiple social-engineering indicators were identified.

## 4. Analysis
The sender domain uses a lookalike spelling designed to resemble a trusted Microsoft-related domain. The message creates urgency and fear by warning that the account will be suspended. The included login URL uses a suspicious domain and could potentially be used to capture credentials.

These indicators support treating the email as a likely phishing attempt.

## 5. Validation
The simulated lab does not provide evidence showing whether the user clicked the link or submitted credentials. Additional authentication and endpoint activity would be required to determine whether account compromise occurred.

## 6. Final Finding
**Likely Phishing Attempt — Investigation Required**

The available simulated evidence strongly supports the phishing assessment, but user interaction and possible compromise are not confirmed.

## 7. Recommended Response
1. Do not open the suspicious link.
2. Quarantine or remove the email.
3. Check whether the user clicked the link.
4. Check whether credentials were submitted.
5. Review related authentication activity.
6. Block confirmed malicious indicators.
7. Escalate if additional evidence indicates account compromise.

## 8. SOC L1 Lesson
SOC L1 should identify phishing indicators, extract relevant IOCs, validate user interaction, document evidence, and avoid assuming account compromise without supporting evidence.

> **Lab Classification:** Controlled / Simulated training exercise. No real phishing campaign or account compromise is claimed.