# Ticket 402 — MFA Troubleshooting 📱

## User

**Name:** Rachel Thompson
**Department:** Finance
**Job Title:** Financial Analyst


---

## Scenario

Rachel recently replaced her mobile device and was unable to complete MFA using her previously registered Microsoft Authenticator method.

The ticket was received by the IAM team for investigation.

---

## Investigation

I reviewed Rachel's registered authentication methods and found that her previous Microsoft Authenticator registration was associated with an iPad device.

The previous Microsoft Authenticator registration was removed to simulate the loss/replacement of the device.

---

## Root Cause

Rachel no longer had access to the device associated with her previous Microsoft Authenticator registration.

As a result, she could not use the existing authentication method to complete MFA.

---

## Remediation

I created a Temporary Access Pass (TAP) for Rachel to provide a temporary recovery method.

Rachel used the TAP to access the Microsoft security information registration process and registered a replacement Microsoft Authenticator method.

The TAP was configured as a one-time-use credential with a limited activation period.

---

## Verification

Rachel successfully registered the replacement Microsoft Authenticator method.

The MFA registration was verified after completing the authentication setup.

---

## Audit Verification

I reviewed the Microsoft Entra audit logs and confirmed the administrative activity associated with Rachel's authentication-method changes.

---

## Evidence

- Original Microsoft Authenticator registration
- Previous authentication method removed
- Temporary Access Pass created
- Replacement Microsoft Authenticator registered
- Successful MFA verification
- Audit log evidence
