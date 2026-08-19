# 403 — Application Access Troubleshooting 💻

## User

* **Name:** Demarcus Turner
* **Department:** Operations
* **Job Title:** Operations Analyst
* **Issue Type:** Authorization / Enterprise Application Assignment

---

## Scenario

Demarcus Turner is an Operations Analyst at Cedar Valley Health who was expected to have access to the **CVH Operations Portal**.

The IAM team received the issue and was asked to investigate whether the problem was related to Demarcus's group membership or the Enterprise Application assignment.

---

## Initial Investigation

I created a test Enterprise Application named:

**CVH Operations Portal**

The application was configured with **Assignment required** enabled.

The application was assigned to:

```text
CVH-Operations-Team
```

I then reviewed Demarcus Turner's existing group memberships.

---

## Finding

Demarcus was not initially a member of:

```text
CVH-Operations-Team
```

Because the application assignment was based on membership in this group, Demarcus was missing the group membership required for the application's assignment.

This was identified as an **authorization issue** rather than an authentication issue.

### Before Remediation

```text
CVH Operations Portal
        ↓
CVH-Operations-Team
        ↓
Demarcus Turner
        ❌ Not a member
```

---

## Remediation

I added Demarcus Turner to the:

```text
CVH-Operations-Team
```

security group.

The purpose of the change was to align Demarcus's group membership with the security group assigned to the CVH Operations Portal.

---

## Verification

After adding Demarcus to the group, I returned to his user account in Microsoft Entra ID and reviewed his group memberships.

I confirmed that Demarcus was now a member of:

```text
CVH-Operations-Team
```

I then reviewed the **CVH Operations Portal** Enterprise Application and confirmed that the application was assigned to the appropriate Operations group.

### After Remediation

```text
CVH Operations Portal
        ↓
CVH-Operations-Team
        ↓
Demarcus Turner
        ✅ Member
```
---

## Audit Log Verification

After completing the group membership change, I reviewed the Microsoft Entra audit logs.

The audit log showed the administrative change associated with Demarcus's group membership.

This allowed me to verify that the change was recorded rather than relying only on the updated group membership screen.

---

## Authentication vs. Authorization

This scenario helped reinforce the difference between **authentication** and **authorization**.

### Authentication

> **"Can Demarcus prove who he is?"**

Authentication determines whether the user's identity can be verified.

### Authorization

> **"Does Demarcus have permission to access the resource?"**

Authorization determines whether the authenticated user has the required permissions or assignments.

In this scenario, the investigation focused on the **authorization** side of the issue.

---

## Troubleshooting Workflow

I followed the same basic troubleshooting process used throughout Phase 4:

```text
Access issue reported
        ↓
Review Enterprise Application
        ↓
Check application assignment
        ↓
Review Demarcus's group memberships
        ↓
Identify missing group membership
        ↓
Add Demarcus to CVH-Operations-Team
        ↓
Verify group membership
        ↓
Verify Enterprise Application assignment
        ↓
Review audit logs
        ↓
Document the result
```

---

## Final Result

Demarcus was added to the `CVH-Operations-Team` security group used for the CVH Operations Portal assignment.

His updated group membership was verified, the Enterprise Application assignment was reviewed, and the corresponding audit log activity was confirmed.

The issue demonstrated how an incorrect or missing group membership can affect application authorization.

---

## Scope Note

This lab focused on the Microsoft Entra authorization and Enterprise Application assignment portion of the troubleshooting process.

The non-gallery Enterprise Application created for this exercise was **not configured with a functional application endpoint**. Because of this, I did not claim that Demarcus received a live application access-denied message.

Instead, I investigated the application assignment and group membership that would determine whether the user was authorized for the application.

The actual **"User is not assigned to this application"** access-denied scenario will be addressed during:

**Phase 6 — SAML Single Sign-On (SSO)**

This keeps Phase 4 focused on common IAM operations and troubleshooting while leaving application authentication and SSO troubleshooting for the appropriate phase of the project.

---

## Key Takeaway

This scenario demonstrated that having an active Entra ID account does not automatically mean a user has access to every application.

Application assignments and group memberships need to align with the user's role and access requirements.

The biggest takeaway for me was the importance of checking the configuration and then verifying the change through audit logs.

The goal was not just to make the access change, but to be able to explain **why the change was needed and provide evidence that it occurred**.
