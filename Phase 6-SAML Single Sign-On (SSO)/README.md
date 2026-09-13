# 🔐 Phase 6 — SAML Single Sign-On

## 🏥 Cedar Valley Health Identity Modernization

## 📋 Overview

This phase demonstrates the implementation and validation of **SAML-based Single Sign-On (SSO)** using Microsoft Entra ID and the SAML Toolkit.

The objective was to configure a SAML enterprise application, assign authorized users, validate successful authentication, and troubleshoot an initial application-access issue.

---

### 🎥 Video Overview

> **Watch the short walkthrough:**

 **https://www.loom.com/share/cbb8645634d041e19c6d03285d6ce5c7**

This short walkthrough demonstrates the Cedar Valley Health SAML SSO configuration, user testing, the initial access issue encountered with Mia Turner, and the remediation process.

---


## 🖥️ Environment

| Component                  | Configuration                |
| -------------------------- | ---------------------------- |
| 🆔 Identity Provider       | Microsoft Entra ID           |
| 🔐 Authentication Protocol | SAML 2.0                     |
| 🧪 Application             | Microsoft Entra SAML Toolkit |
| 👤 Primary Test User       | Danielle Carter              |
| 👤 Secondary Test User     | Mia Turner                   |
| ⚙️ Management Plane        | Microsoft Entra Admin Center |

---

## 🎯 Objectives

* ⚙️ Configure a SAML enterprise application in Microsoft Entra ID
* 🔐 Configure SAML-based Single Sign-On
* 🔎 Review SAML configuration and claims
* 👥 Assign users to the application
* ✅ Validate successful SSO
* 🛠️ Troubleshoot an application-access failure
* 🔄 Verify remediation through successful authentication
* 📊 Review Entra sign-in and audit evidence

---

## ⚙️ Implementation

The SAML Toolkit was configured as an enterprise application within Microsoft Entra ID.

The configuration included:

* 🔐 SAML-based Single Sign-On
* 🆔 Identifier (Entity ID)
* 🔗 Reply URL / Assertion Consumer Service URL
* 🌐 Sign-on URL
* 🏷️ Attributes and Claims
* 📜 SAML signing certificate
* 👥 User assignment

The application was tested using two CVH test identities.

---

## 👤 Test Users

### 👩 Danielle Carter

Danielle Carter was used as the primary SSO test account.

**Expected result:**

```text
Danielle Carter
        ↓
Microsoft Entra ID
        ↓
SAML Authentication
        ↓
SAML Toolkit
        ↓
✅ Access Granted
```

Danielle successfully authenticated to the application.

### 👩 Mia Turner

Mia Turner was initially unable to access the application.

The issue was investigated and determined to be related to application access/assignment rather than a failure of SAML authentication itself.

Mia was subsequently registered and assigned access to the enterprise application.

**After remediation:**

```text
Mia Turner
        ↓
Microsoft Entra ID
        ↓
Application Assignment
        ↓
SAML Authentication
        ↓
SAML Toolkit
        ↓
✅ Access Granted
```

This provided an opportunity to demonstrate both **authentication and authorization troubleshooting**.

---

## 🧪 Validation

The implementation was validated using:

* ✅ Successful application authentication
* 👥 Enterprise application user assignment
* 📊 Microsoft Entra sign-in logs
* ⚙️ Application access configuration
* 🔐 SAML configuration review
* 🔄 Post-remediation testing

---

## 🧠 Key IAM Concepts Demonstrated

* 🔐 SAML 2.0
* 🚪 Single Sign-On
* 🆔 Identity Provider (IdP)
* 🏢 Service Provider (SP)
* 📱 Enterprise Applications
* 👥 User assignment
* 🔎 Authentication vs. authorization
* 🏷️ SAML claims
* 📜 Certificate-based trust
* 📊 Sign-in log investigation
* 🛠️ Access troubleshooting

---

## 📸 Evidence

Screenshots and supporting documentation are maintained in the `Documentation` directory.

Evidence focuses on:

1. ⚙️ SAML application configuration
2. 🏷️ Attributes and Claims
3. 👥 User assignment
4. ✅ Danielle Carter successful authentication
5. ⚠️ Mia Turner's initial access issue
6. 🔧 Remediation
7. ✅ Successful post-remediation authentication
8. 📊 Entra sign-in/audit evidence

---

## 🏁 Outcome

The CVH SAML application was successfully configured and validated.

Danielle Carter successfully completed SSO testing, while Mia Turner's initial access failure was investigated and remediated through appropriate application registration and assignment.

This phase demonstrates practical experience configuring SAML SSO and troubleshooting the difference between **authentication** and **application authorization** within Microsoft Entra ID.

---



