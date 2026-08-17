# 🚪 Exception Scenario – Leaver With Former Manager

## Scenario

Cedar Valley Health receives a termination request for an employee.

During the review, IAM discovers that the employee's assigned manager has already left the organization.

The former manager is no longer an active employee and cannot provide current authorization.

This creates an exception to the normal manager approval path.

---

## Employee

**Name:** Marcus Williams

**Role:** Customer Service Representative

**Department:** Customer Service

**Status:** Employee termination

**Manager:** Former employee / no longer active

---

## Business Request

HR submits a termination request for Marcus Williams.

During validation, IAM identifies that the assigned manager is no longer employed by Cedar Valley Health.

The former manager's account is no longer active, so IAM does not rely on that person for current approval.

---

## Escalation

The request is escalated through the appropriate HR authority.

For this simulation, the escalation path is:

**HR Request → HR Authority → IAM**

The purpose is to make sure the termination request has appropriate authorization before IAM processes the access removal.

---

## IAM Process

Once the termination request has been validated, IAM will:

1. Disable the user's account.
2. Remove security group memberships.
3. Remove access that is no longer required.
4. Revoke active sessions.
5. Verify the account is disabled.
6. Confirm the user cannot successfully sign in.
7. Review Microsoft Entra audit logs.

---

## Audit Verification

After completing the leaver process, I will review the audit logs for evidence of the administrative actions.

I will also verify the final account state.

The goal is to confirm:

- Account is disabled.
- Access has been removed.
- Sessions have been revoked.
- Sign-in is no longer successful.
- Administrative activity was recorded in the audit logs.

---

## Why This Scenario Matters

A normal lifecycle process may assume that the employee's manager is available to approve or validate a request.

In a real environment, that will not always be the case.

Managers leave organizations, accounts become disabled, and reporting relationships change.

IAM needs a defined escalation path so that lifecycle events can still be processed without relying on an inactive account or creating an unauthorized approval.

---

## Evidence

Screenshots will include:

- HR termination request
- User account before termination
- Group memberships
- Account disabled
- Session revocation
- Sign-in verification
- Audit log evidence
