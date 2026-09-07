# Phase 6 — SAML Single Sign-On Lab

## Cedar Valley Health Identity Modernization

**Platform:** Microsoft Entra ID
**Application:** SAML Toolkit
**Protocol:** SAML 2.0
**Primary Test User:** Danielle Carter
**Secondary Test User:** Mia Turner

---

# 1. Scenario

Cedar Valley Health (CVH) needs to provide employees with secure Single Sign-On access to an external application.

Microsoft Entra ID will act as the **Identity Provider (IdP)**, while the SAML Toolkit represents the application/service provider used to validate the SSO configuration.

The lab will demonstrate:

1. SAML application configuration
2. User assignment
3. SSO authentication
4. Application authorization
5. Troubleshooting
6. Remediation
7. Log validation

---

# 2. Architecture

```text
                    CVH User
                       |
                       v
              Microsoft Entra ID
                 Identity Provider
                       |
                       | SAML 2.0
                       v
                SAML Toolkit
               Enterprise App
                       |
                       v
                Application
```

Microsoft Entra ID authenticates the user and issues a signed SAML response to the application.

---

# 3. Objectives

The objectives of this lab were to:

* Configure a SAML enterprise application
* Configure SAML Single Sign-On
* Review the SAML trust configuration
* Configure application attributes and claims
* Assign users to the application
* Validate successful SSO
* Investigate an application access failure
* Remediate the access issue
* Validate the remediation using logs

---

# 4. SAML Application Configuration

The SAML Toolkit was configured as an Enterprise Application in Microsoft Entra ID.

Navigation:

```text
Microsoft Entra Admin Center
        ↓
Enterprise Applications
        ↓
SAML Toolkit
        ↓
Single Sign-On
        ↓
SAML
```

The SAML configuration included the following components:

* Identifier (Entity ID)
* Reply URL / Assertion Consumer Service URL
* Sign-on URL
* Attributes & Claims
* SAML signing certificate

---

# 5. Identity Provider

Microsoft Entra ID served as the Identity Provider.

The authentication process was:

```text
User
 ↓
Microsoft Entra ID
 ↓
User authentication
 ↓
SAML assertion generated
 ↓
SAML Toolkit
 ↓
Application access
```

The SAML assertion contains identity information that allows the application to recognize the authenticated user.

---

# 6. Attributes and Claims

The SAML configuration was reviewed to determine which user attributes were being issued to the application.

Relevant identity information may include:

* Name identifier
* User principal name
* Email
* First name
* Last name

The claims configuration was reviewed to ensure the application received the expected identity information.

---

# 7. Primary Test — Danielle Carter

## Objective

Danielle Carter was selected as the primary test user for the SAML SSO implementation.

Expected flow:

```text
Danielle Carter
       ↓
Microsoft Entra ID
       ↓
Authentication
       ↓
SAML Assertion
       ↓
SAML Toolkit
       ↓
Application
       ↓
Access Granted
```

## Test Result

**Result: Successful**

Danielle Carter successfully authenticated to the SAML application.

This confirmed that:

* The enterprise application was configured correctly.
* Danielle had application access.
* SAML authentication was functioning.
* The application accepted the authentication response.

---

# 8. Secondary Test — Mia Turner

Mia Turner was used as a secondary validation account.

The purpose of this test was to determine whether application access was correctly controlled through user assignment.

## Initial Test

Mia attempted to access the SAML application.

### Result

**Access was unsuccessful.**

At this point, the failure was investigated rather than immediately changing the SAML configuration.

---

# 9. Troubleshooting Methodology

The issue was approached using an authentication-versus-authorization model.

```text
                 Access Failure
                       |
              +--------+--------+
              |                 |
        Authentication     Authorization
              |                 |
        Can Entra           Is the user
        authenticate        assigned?
        the user?
```

The application configuration was reviewed first to determine whether the SAML configuration itself was functioning.

Because Danielle Carter had already successfully authenticated, this provided an important comparison point.

### Comparison

| Test                 | Danielle Carter | Mia Turner             |
| -------------------- | --------------- | ---------------------- |
| Entra identity       | Valid           | Valid                  |
| Application access   | Assigned        | Not initially assigned |
| SSO test             | Successful      | Failed                 |
| SAML configuration   | Working         | Working                |
| Remediation required | No              | Yes                    |

This indicated that the problem was more consistent with **application authorization/access assignment** than with a broken SAML configuration.

---

# 10. Remediation

Mia Turner was registered appropriately and added to the SAML enterprise application.

The access path became:

```text
Mia Turner
      ↓
Microsoft Entra ID
      ↓
Enterprise Application
      ↓
User Assignment
      ↓
SAML Authentication
      ↓
SAML Toolkit
      ↓
Application
```

The SAML configuration itself did not need to be rebuilt.

The remediation focused on granting the appropriate user access to the enterprise application.

---

# 11. Post-Remediation Test

Mia Turner repeated the application access test after the remediation.

### Expected Result

```text
Mia Turner
      ↓
Microsoft Entra authentication
      ↓
Application assignment validated
      ↓
SAML assertion
      ↓
SAML Toolkit
      ↓
Access Granted
```

### Result

**Successful**

Mia was able to access the application after being appropriately registered and assigned.

---

# 12. Log Validation

Microsoft Entra sign-in logs were reviewed to validate authentication activity.

Navigation:

```text
Microsoft Entra Admin Center
        ↓
Entra ID
        ↓
Monitoring & Health
        ↓
Sign-in Logs
```

The investigation focused on:

* User
* Application
* Date/time
* Sign-in status
* Authentication details
* Conditional Access results where applicable

The logs provided evidence supporting the successful authentication tests.

---

# 13. Lessons Learned

This scenario demonstrated an important distinction between **authentication** and **authorization**.

### Authentication

Authentication answers:

> "Who is this user?"

Microsoft Entra ID successfully authenticated the users.

### Authorization

Authorization answers:

> "Is this user allowed to access this application?"

Mia Turner's initial failure demonstrated that a user can have a valid Entra identity but still lack authorization to use a particular enterprise application.

---

# 14. Troubleshooting Decision Model

The troubleshooting process can be summarized as:

```text
User cannot access application
            |
            v
Can the user authenticate?
       /             \
     No               Yes
     |                 |
Investigate         Check application
authentication      authorization
     |                 |
MFA / account       Assignment
claims / policy     registration
                       |
                       v
                 Remediate access
                       |
                       v
                 Retest application
                       |
                       v
                 Validate logs
```

This approach avoids unnecessarily modifying working SAML configuration when the actual problem is application access.

---

# 15. Final Result

The CVH SAML Single Sign-On implementation was successfully validated.

### Danielle Carter

**Successful on initial SSO test.**

### Mia Turner

**Initial access failure → investigated → registered/assigned → successful access.**

The scenario demonstrated:

* SAML 2.0
* Microsoft Entra Enterprise Applications
* SSO
* Identity Provider concepts
* SAML claims
* User assignment
* Authentication troubleshooting
* Authorization troubleshooting
* Sign-in log validation

---

# 16. Portfolio Takeaway

This lab demonstrates the ability to do more than configure an SSO application.

It demonstrates the ability to:

1. Configure SAML.
2. Test authentication.
3. Compare successful and unsuccessful users.
4. Identify whether a failure is authentication or authorization related.
5. Remediate application access.
6. Validate the result through logs.

This represents a practical IAM administration and troubleshooting workflow.
