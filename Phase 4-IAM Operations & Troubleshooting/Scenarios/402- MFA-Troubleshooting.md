# 402 — MFA Troubleshooting 📱

## User

**Name:** Rachel Thompson

**Department:** Finance

**Job Title:** Financial Analyst

**Issue Type:** MFA / Authentication Method Recovery

---

## Scenario

Rachel Thompson is a Financial Analyst with Cedar Valley Health who recently replaced her mobile device and could no longer use the Microsoft Authenticator method that was registered to her previous device.

The ticket was received by the IAM team to investigate the MFA issue and help restore Rachel's ability to register and use a replacement authentication method.

---

## Initial Investigation

I opened Rachel's user account in Microsoft Entra ID and reviewed her authentication methods.

The existing authentication method showed:

**Microsoft Authenticator — iPad 6th generation**

This represented the device that Rachel no longer had access to.

### Initial Finding

Rachel's existing Microsoft Authenticator registration was associated with her previous device.

---

## Simulating the Device Replacement

To reproduce the issue in the lab, I removed the existing Microsoft Authenticator registration.

This simulated the situation where Rachel had replaced or lost the device that was previously registered for MFA.

---

## Temporary Access Pass Recovery

Because Rachel no longer had access to the previous authentication method, I created a **Temporary Access Pass (TAP)**.

The TAP was configured with:

- Immediate activation
- One-hour activation duration
- One-time use

The purpose of the TAP was to provide a temporary recovery method so Rachel could access the security information registration process.

> **Security Note:** The actual TAP value was intentionally excluded from screenshots and documentation.

---

## Replacement Authentication Method

Rachel used the Temporary Access Pass to access the Microsoft security information registration process.

From there, she registered a replacement Microsoft Authenticator method.

The new Microsoft Authenticator registration was then visible in Rachel's authentication methods.

---

## Verification

The replacement authentication method was successfully registered.

The registration confirmed that Rachel's MFA recovery process was completed successfully.

---

## Audit Log Verification

I reviewed the Microsoft Entra audit logs after completing the authentication-method changes.

The audit logs provided evidence of the administrative activity associated with Rachel's authentication methods.


---

## Final Result

Rachel's previous Microsoft Authenticator registration was removed, a temporary recovery method was provided through TAP, and a replacement Microsoft Authenticator registration was successfully established.

Rachel was able to complete the MFA recovery process and register a new Microsoft Authenticator method.

---

## Troubleshooting Workflow

```text
Rachel reports MFA issue
        ↓
Review authentication methods
        ↓
Identify old Authenticator registration
        ↓
Remove old registration
        ↓
Create Temporary Access Pass
        ↓
Rachel accesses Security Info
        ↓
Register replacement Authenticator
        ↓
Verify registration
        ↓
Review audit logs
