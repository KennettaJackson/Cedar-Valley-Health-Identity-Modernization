# 🎫 Phase 3 – HR / IAM Requests

## Purpose

These are simulated HR requests used to represent the business events that trigger IAM activities during Phase 3.

I am using these tickets to connect the business side of the request with the technical work performed in Microsoft Entra.

The basic workflow is:

**HR Request → Authorization → IAM Action → Verification → Audit Evidence**

---

# Ticket 001 – Quarterly Access Review

**Ticket:** CVH-IAM-001  
**Requestor:** Cedar Valley Health Security / HR  
**Request Type:** Access Review  
**Priority:** Normal  
**Status:** Completed

## Request

Cedar Valley Health is conducting a quarterly review of employee and IAM access six months after the clinic acquisition.

IAM is being asked to review selected users and determine whether their current access is still appropriate based on their current responsibilities.

## Scope

The review includes:

- Employee group memberships
- IAM team membership
- Current job responsibilities
- Identification of unnecessary or stale access

## Expected Outcome

Access that is no longer required should be removed.

The changes should be verified in Microsoft Entra and supported by audit evidence.

---

# Ticket 002 – Review of Temporary Sales Access

**Ticket:** CVH-IAM-002  
**Employee:** Rachel Thompson  
**Current Role:** Financial Analyst  
**Department:** Finance  
**Request Type:** Access Review  
**Status:** Completed

## Request

As part of the quarterly access review, IAM is reviewing Rachel Thompson's current group memberships.

Rachel previously assisted the Sales department with a temporary reporting project and was granted Sales access.

The project has ended.

## Current Required Access

`CVH-Finance-Team`

## Access Being Reviewed

`CVH-Sales-Team`

## IAM Decision

Remove:

`CVH-Sales-Team`

Retain:

`CVH-Finance-Team`

## Verification

IAM verified the updated group membership and reviewed the related Microsoft Entra audit event.

---

# Ticket 003 – Mover While on Leave

**Ticket:** CVH-IAM-003  
**Employee:** Ashley Morgan  
**Current Role:** Financial Analyst  
**New Role:** Operations Analyst  
**Request Type:** Mover  
**Employee Status:** On Leave  
**Status:** Completed

## Request

HR submitted an approved role-change request for Ashley Morgan while she was on leave. The role change had an established effective date, so IAM processed the access changes according to the authorized HR request rather than waiting for Ashley to return.

The change will take effect on the approved effective date.

## IAM Consideration

Ashley does not need to personally log into Microsoft Entra or validate the organizational role change.

IAM will rely on the authorized HR/business request and the documented effective date.

## IAM Actions

- Update relevant user properties.
- Remove Finance access that is no longer required.
- Assign `CVH-Operations-Team`.
- Verify final group membership.
- Review Microsoft Entra audit logs.

---

# Ticket 004 – Leaver With Former Manager

**Ticket:** CVH-IAM-004  
**Employee:** Marcus Williams  
**Request Type:** Employee Termination  
**Status:** Completed

## Request

HR submitted a termination request for Marcus Williams.

During validation, IAM determined that Marcus's assigned manager is no longer employed by Cedar Valley Health.

## Exception

The former manager cannot provide current approval because they are no longer an active employee.

## Escalation

The request was escalated through the designated HR authority for validation before IAM processed the termination.

## IAM Actions

- Disable account.
- Remove security group memberships.
- Remove access.
- Revoke active sessions.
- Verify account status.
- Verify sign-in behavior.
- Review audit logs.

---

# Ticket 005 – IAM Administrative Access Review

**Ticket:** CVH-IAM-005  
**Request Type:** Administrative Access Review  
**Requestor:** Security  
**Status:** Completed

## Request

Security requested a review of the `CVH-IAM-Team` group and applicable IAM administrative access.

The purpose is to confirm that IAM personnel continue to require their current level of access based on their responsibilities.

## Review

Each IAM team member was reviewed based on:

- Current role
- Current responsibilities
- Group membership
- Administrative access

## Expected Outcome

Users who no longer require IAM access should be removed from the appropriate group or administrative role.

The final decisions and remediation will be documented in the Phase 3 access review spreadsheet.
