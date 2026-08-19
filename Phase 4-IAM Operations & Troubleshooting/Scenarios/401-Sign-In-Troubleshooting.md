# Ticket 401 — Sign-In Troubleshooting 🔐

## User

**Name:** Danielle Carter  
**Department:** Finance  
**Job Title:** Financial Analyst

---

## Scenario

Danielle reported that she was unable to sign in to Cedar Valley Health resources.

The ticket was received by the IAM team for investigation.

---

## Investigation

I reviewed Danielle's account and Microsoft Entra sign-in activity.

The failed sign-in event showed:

**Error Code:** 50126

**Failure Reason:** Error validating credentials due to invalid username or password.

**Additional Details:** The user did not enter the correct credentials.

---

## Root Cause

The authentication failure was caused by invalid credentials.

---

## Remediation

I performed a password reset for Danielle's account using Microsoft Entra ID.

---

## Verification

After the password reset, Danielle was able to successfully authenticate.

A successful sign-in event was captured in the Microsoft Entra sign-in logs.

---

## Audit Verification

I reviewed the Microsoft Entra audit logs after performing the password reset.

The administrative password-reset activity was recorded in the audit logs.

---

## Evidence

- Danielle account
- Failed sign-in showing error 50126
- Password reset
- Successful sign-in
- Password-reset audit event
