# Phase 4 - IAM Operations & Troubleshooting 🔐

## Overview

After completing the Identity Governance and Access Reviews phase, Cedar Valley Health (CVH) moved into normal day-to-day identity operations.

For this phase, I focused on three common IAM troubleshooting scenarios involving authentication, MFA recovery, and application authorization.

The goal was to practice investigating identity issues, identifying the cause, performing the appropriate remediation, and verifying the result.

The troubleshooting workflow used throughout the phase was:

**Ticket → Investigate → Identify Root Cause → Remediate → Verify → Document**

---

## 🎥 Short Overview & Video Walkthrough

A short 3–5 minute video walkthrough is included below, providing a high-level overview of Phase 4 rather than a step-by-step demonstration of every action performed in Microsoft Entra ID.

The walkthrough briefly covers:

- The purpose and background of Phase 4
- **Ticket 401:** Danielle Carter's sign-in failure and the `50126` authentication error
- **Ticket 402:** Rachel Thompson's MFA recovery using a Temporary Access Pass and replacement Microsoft Authenticator registration
- **Ticket 403:** Demarcus Turner's application authorization investigation involving Enterprise Application assignment and group membership
- How Microsoft Entra sign-in logs and audit logs were used as evidence
- The difference between authentication and authorization
- Key lessons learned from the troubleshooting exercises

🎬 **Video Walkthrough:**https://www.loom.com/share/8718fcbb1e364dcc8ecbff6609cba642

---

## 🎯 Objectives

- Troubleshoot common identity and authentication issues
- Investigate Microsoft Entra sign-in activity
- Troubleshoot MFA registration and recovery
- Investigate Enterprise Application access
- Identify authorization and group membership issues
- Perform appropriate IAM remediation
- Verify that remediation resolved the issue
- Review audit logs after administrative changes
- Document troubleshooting results and evidence

---

# 🏥 Scenario Background

Several months have passed since Cedar Valley Health completed the Identity Governance and Access Reviews phase.

The IAM team is now handling normal day-to-day identity operations.

Three operational tickets were received by the IAM team involving common identity and access issues.

The scenarios were intentionally kept small and focused on investigation and evidence rather than predetermined answers.

---

# 🎫 Operational Scenarios

## Ticket 401 — Sign-In Troubleshooting

**User:** Danielle Carter  
**Department:** Finance  
**Job Title:** Financial Analyst

Danielle reported that she was unable to sign in to Cedar Valley Health resources.

The IAM team investigated the user's account and Microsoft Entra sign-in activity to determine the cause of the authentication failure.

The sign-in logs showed an authentication failure with error code **50126**, indicating that the credentials could not be validated.

IAM performed a password reset and verified that Danielle was able to successfully authenticate afterward.

The audit logs were reviewed to verify the administrative activity.

### Skills Demonstrated

- Sign-in investigation
- Authentication troubleshooting
- Error-code analysis
- Password reset
- Successful sign-in verification
- Audit-log review

---

## Ticket 402 — MFA Troubleshooting

**User:** Rachel Thompson

**Department:** Finance  
**Job Title:** Financial Analyst

Rachel replaced her mobile device and was no longer able to use her previously registered Microsoft Authenticator method.

The IAM team investigated Rachel's authentication methods and determined that the previous Microsoft Authenticator registration was associated with her old device.

The old registration was removed and a Temporary Access Pass (TAP) was created to provide a temporary recovery method.

Rachel used the TAP to access the security information registration process and registered a replacement Microsoft Authenticator method.

The MFA configuration and administrative activity were verified through Microsoft Entra.

### Skills Demonstrated

- Authentication-method investigation
- MFA troubleshooting
- Temporary Access Pass
- MFA recovery
- Microsoft Authenticator registration
- Audit-log review

---

## Ticket 403 — Application Authorization Troubleshooting

**User:** Demarcus Turner  
**Department:** Operations  
**Job Title:** Operations Analyst

Demarcus was expected to have access to the CVH Operations Portal.

The IAM team investigated the Enterprise Application assignment and the user's group memberships.

The CVH Operations Portal was assigned to the `CVH-Operations-Team` security group, but Demarcus was not initially a member of that group.

The IAM team identified the missing group membership as the access issue and added Demarcus to the appropriate group.

The membership change was verified and the corresponding audit activity was reviewed.

> **Note:** This lab focused on the Entra authorization and assignment side of the issue. A live application access-denied test was not performed because the non-gallery Enterprise Application used in this phase was not configured with a production-style application endpoint.

### Skills Demonstrated

- Enterprise Application investigation
- Application assignment
- Group membership investigation
- Authorization troubleshooting
- Access remediation
- Audit-log verification

---

# 🔎 Troubleshooting Approach

For each ticket, I followed a consistent troubleshooting process:

1. Review the reported issue
2. Investigate the user's account
3. Review relevant Entra information and logs
4. Determine the likely cause
5. Perform the appropriate remediation
6. Verify the result
7. Review audit evidence
8. Document the outcome

The purpose of this approach was to avoid simply applying a remediation without first understanding the problem.

---

# 🧾 Evidence

Screenshots are organized by scenario:

- Sign-In
- MFA
- Application Access

Screenshots were captured before and after remediation where appropriate.

Sensitive information such as passwords, Temporary Access Pass values, and other credentials is intentionally excluded from the repository.

---

# 🧠 Key Takeaways

This phase focused on the operational side of IAM.

The biggest takeaway was that troubleshooting is more than simply changing a setting.

For each issue, I investigated the user's identity, reviewed available evidence, determined whether the problem involved authentication or authorization, performed the appropriate remediation, and verified the change.

Audit logs were also reviewed after administrative changes to provide evidence that the remediation actually occurred.

This phase also reinforced the difference between:

**Authentication**

> Can the user prove who they are?

and

**Authorization**

> Does the user have permission to access the requested resource?

---

# 🛠️ Technologies

- Microsoft Entra ID
- Microsoft Entra ID P2
- Microsoft Entra Sign-in Logs
- Microsoft Entra Audit Logs
- Microsoft Authenticator
- Temporary Access Pass
- Microsoft Entra Enterprise Applications
- Microsoft Entra Security Groups

---

# 📁 Repository Structure

```text
Phase 4 - IAM Operations & Troubleshooting/
│
├── README.md
│
├── Tickets/
│   └── phase-4-iam-tickets.md
│
├── Scenarios/
│   ├── 401-sign-in-troubleshooting.md
│   ├── 402-mfa-troubleshooting.md
│   └── 403-application-access.md
│
└── Screenshots/
    ├── Sign-In/
    ├── MFA/
    └── Application-Access/
