# Phase 4 — IAM Operations Tickets 🎫

This document contains the operational IAM tickets used during Phase 4 of the Cedar Valley Health Identity Modernization project.

For this phase, I focused on three common IAM issues involving authentication, MFA recovery, and application authorization.

The tickets were handled using a simple troubleshooting process:

**Investigate → Identify → Remediate → Verify → Document**

---

# CVH-IAM-401 — Sign-In Troubleshooting

**User:** Danielle Carter

**Department:** Finance

**Job Title:** Financial Analyst

**Issue Type:** Authentication

## Ticket

Danielle reported that she was unable to sign in to Cedar Valley Health resources.

The ticket was received by the IAM team for investigation.

## Investigation

I reviewed Danielle's Microsoft Entra sign-in logs to determine why authentication was failing.

The failed sign-in event showed:

**Error Code:** `50126`

**Failure Reason:** Error validating credentials due to invalid username or password.

**Additional Details:** The user did not enter the correct credentials.

## Finding

The sign-in failure was caused by invalid credentials.

## Remediation

I performed a password reset for Danielle's account.

## Verification

I attempted authentication again after the password reset and confirmed that the sign-in was successful.

The successful sign-in event was captured as evidence.

## Audit Verification

I reviewed the Microsoft Entra audit logs to verify the administrative activity associated with the password reset.

## Result

Danielle was able to successfully authenticate after the password reset.

### Evidence

- Failed sign-in showing error `50126`
- Successful sign-in after password reset
- Audit log showing the administrative activity

---

# CVH-IAM-402 — MFA Troubleshooting

**User:** Rachel Thompson

**Issue Type:** MFA / Authentication Method Recovery

## Ticket

Rachel reported an MFA issue after replacing her mobile device.

She could no longer use the Microsoft Authenticator registration associated with her previous device.

The ticket was received by the IAM team for investigation.

## Investigation

I reviewed Rachel's authentication methods in Microsoft Entra.

The existing method showed:

**Microsoft Authenticator — iPad 6th generation**

This represented Rachel's previous device.

To simulate the device replacement scenario, I removed the existing Microsoft Authenticator registration.

## Finding

Rachel no longer had access to the device associated with her previous Microsoft Authenticator registration.

The old authentication method therefore needed to be replaced.

## Remediation

I created a Temporary Access Pass (TAP) for Rachel.

The TAP was configured with:

- Immediate activation
- One-hour activation duration
- One-time use

The TAP was used as a temporary recovery method to allow Rachel to access the security information registration process.

Rachel then registered a replacement Microsoft Authenticator method.

Microsoft documents TAP as a time-limited credential that can be used to help users register authentication methods or recover access when a strong authentication method is unavailable.

## Verification

Rachel successfully completed the registration process for the replacement Microsoft Authenticator method.

The new authentication method was visible in Rachel's security information.

## Audit Verification

I reviewed the Microsoft Entra audit logs and confirmed the administrative activity associated with Rachel's authentication-method changes.

Microsoft Entra audit logs provide records of changes made to users, groups, applications, and other tenant resources. 

## Result

Rachel's MFA registration was successfully recovered and a replacement Microsoft Authenticator method was registered.

### Evidence

- Original Microsoft Authenticator registration
- Old authentication method removed
- Temporary Access Pass created
- Replacement Authenticator registered
- Audit log evidence

> **Security Note:** The actual Temporary Access Pass value was not included in screenshots, documentation, or the repository.

---

# CVH-IAM-403 — Application Authorization Troubleshooting

**User:** Demarcus Turner

**Department:** Operations

**Job Title:** Operations Analyst

**Issue Type:** Authorization / Enterprise Application Assignment

## Ticket

Demarcus was expected to have access to the CVH Operations Portal.

The IAM team received the issue and investigated the Enterprise Application configuration and Demarcus's group memberships.

## Investigation

I created the **CVH Operations Portal** Enterprise Application for the lab.

The application was configured with assignment required.

The application was assigned to:

`CVH-Operations-Team`

I then reviewed Demarcus's group memberships.

Demarcus was not initially a member of the `CVH-Operations-Team` group.

## Finding

The application assignment depended on membership in the `CVH-Operations-Team` group.

Demarcus was missing the required group membership.

This represented an authorization issue rather than an authentication issue.

## Remediation

I added Demarcus Turner to:

`CVH-Operations-Team`

## Verification

I reviewed Demarcus's group memberships after the change and confirmed that he was now a member of the group assigned to the CVH Operations Portal.

I also reviewed the Enterprise Application assignment to confirm that the application was assigned through the appropriate security group.

## Audit Verification

I reviewed the Microsoft Entra audit logs and confirmed the group membership change.

## Result

Demarcus was added to the appropriate Operations security group and the Enterprise Application assignment was verified.

## Scope Note

This scenario focused on the Microsoft Entra authorization and application-assignment portion of the troubleshooting process.

I did not configure a functional application endpoint or perform a live application access-denied test.

The actual **"user is not assigned to this application"** scenario will be demonstrated later during **Phase 6 — SAML Single Sign-On (SSO)**.

### Evidence

- CVH Operations Portal application assignment
- Demarcus's group membership before remediation
- Demarcus's group membership after remediation
- Audit log showing the group membership change

---

# Phase 4 Ticket Summary

| Ticket | User | Issue | Remediation | Status |
|---|---|---|---|---|
| CVH-IAM-401 | Danielle Carter | Invalid credentials | Password reset | ✅ Resolved |
| CVH-IAM-402 | Rachel Thompson | Lost MFA registration | TAP + replacement Authenticator | ✅ Resolved |
| CVH-IAM-403 | Demarcus Turner | Missing application authorization | Added to Operations group | ✅ Resolved |

---

# Operational Takeaway

The main focus of these tickets was not simply making a change.

For each issue, I investigated the available evidence, determined whether the problem involved authentication or authorization, performed the appropriate remediation, and verified the administrative activity through Microsoft Entra logs.

This reinforced the importance of being able to **prove what happened**, not just make the change.
