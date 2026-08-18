# 🔐 Phase 3 – Identity Governance & Access Reviews

**Project:** Cedar Valley Health – Microsoft Entra ID IAM Lab  
**Phase:** 3  
**Focus:** Identity Governance, Access Reviews, Least Privilege & Audit Verification  
**Platform:** Microsoft Entra ID P2

---

## 📋 Overview

Six months have passed since Cedar Valley Health acquired a small outpatient clinic.

Since the acquisition, the IAM team has continued onboarding employees, processing role changes, removing access for leavers, and managing security group memberships.

Now that the environment has been running for several months, Cedar Valley Health wants to perform an access review to make sure users still have the access they need based on their current roles.

This phase focuses on moving beyond simply provisioning access and looking at how access is reviewed and governed over time.

The main question for this phase is:

> **Does this person still need this access?**

---

## 🎥 Project Walkthrough

A short Loom walkthrough provides a high-level overview of the completed Phase 3 Identity Governance and Access Reviews lab.

The walkthrough highlights:

- Microsoft Entra Identity Governance
- Access Reviews
- Access remediation
- IAM administrative access review
- Least Privilege
- Lifecycle exception scenarios
- Audit verification
- Project documentation and evidence

### 🎬 Loom Walkthrough

https://www.loom.com/share/2732e9b7a40e40dbb001851e8bd1bf33

> **Note:** The video provides a high-level overview of the completed lab. Detailed documentation, access review results, screenshots, and audit evidence are available throughout this repository.

---



## 🎯 Objectives

In this phase, I will practice:

- Creating and performing Microsoft Entra Access Reviews
- Reviewing security group memberships
- Applying the Principle of Least Privilege
- Identifying unnecessary or stale access
- Reviewing IAM team access
- Handling exceptions to the normal JML process
- Removing access that is no longer needed
- Verifying that the change actually occurred
- Reviewing Microsoft Entra audit logs
- Documenting the request, decision, remediation, and evidence

---

## 🏥 Business Scenario

Six months after the clinic acquisition, Cedar Valley Health's Security and HR teams request a quarterly access review.

The IAM team will review selected users and groups to determine whether their current access still matches their job responsibilities.

Most users should have appropriate access. The purpose of the review is not to make everyone fail. The goal is to determine whether access is still appropriate and document the decision.

During the review, the IAM team will also work through two situations that do not follow the normal JML workflow:

1. An employee changes roles while on leave.
2. An employee leaves the company while their assigned manager has already left.

These scenarios are meant to show how IAM handles situations where the normal process is not as straightforward.

---

## 🔄 Phase 3 Workflow

The workflow for this phase is:

**Request → Authorization → IAM Action → Review → Decision → Remediation → Verification → Audit Evidence**

I am using this process to make sure I am not only making the IAM change, but also understanding why the change was made and how I can prove it happened.

---

## 🔎 Access Review

Selected users will be reviewed based on their:

- Current department
- Current job title
- Current responsibilities
- Security group memberships
- Business need for the access

Each access decision will be documented as:

- ✅ Approve
- ❌ Remove


The detailed results will be maintained in an Excel spreadsheet and supported by screenshots from Microsoft Entra.

---

## ⚠️ Exception Scenarios

### 1. Mover While on Leave

A new employee scenario will be used to simulate a role change while the employee is on leave.

The employee does not need to personally log into Entra or validate the organizational change.

The change is based on an authorized HR/business request and an effective date.

IAM will validate the request, update the user's access, verify the final state, and review the audit logs.

### 2. Leaver With Former Manager

A new employee scenario will be used where the employee's assigned manager has already left Cedar Valley Health.

Since the former manager is no longer an active employee, the normal approval path is no longer available.

The request will be escalated through the appropriate HR authority before IAM processes the termination.

IAM will then disable the account, remove access, revoke sessions, verify the account is disabled, and review the audit logs.

---

## 🔎 Audit Log Verification

One of the main things I want to improve in this phase is audit verification.

It is not enough to say:

> "I changed the access."

I want to be able to prove that the change actually happened.

For relevant IAM actions, I will review Microsoft Entra audit logs to confirm events such as:

- Group membership changes
- User property changes
- Account disablement
- Other relevant identity administration activity

I will also verify the final user or group state after the change.

This creates an evidence trail:

**What was requested → What I changed → Did it work → What does the audit log show?**

---

## 📊 Documentation

The project includes:

- Access review documentation
- Excel access review results
- HR/IAM request simulations
- Exception scenarios
- Remediation evidence
- Microsoft Entra audit log screenshots

---

## 🧠 What I Am Practicing

This phase helps me understand that IAM is not only about creating users and assigning access.

Access needs to be reviewed over time because people's roles, responsibilities, and business needs change.

The main process I am practicing is:

**Review → Decide → Remediate → Verify → Prove**

---

## 🚀 Phase 3 Outcome

By the end of this phase, I want to demonstrate that I can:

- Review user access
- Determine whether access is still appropriate
- Identify stale or unnecessary access
- Remediate access
- Handle exceptions to normal JML processes
- Verify that changes were successful
- Use audit logs as evidence

The goal is to show that I can not only make IAM changes, but also understand the business reason behind the change and provide evidence that it was completed correctly.

---

## 🔜 Next Phase

### Phase 4 – IAM Operations & Troubleshooting

The next phase will focus more on day-to-day IAM operations and troubleshooting.

Possible scenarios include:

- Account lockouts
- MFA issues
- Sign-in failures
- Access problems
- Identity troubleshooting
- Audit investigation
- IAM tickets
- Incident-style troubleshooting
