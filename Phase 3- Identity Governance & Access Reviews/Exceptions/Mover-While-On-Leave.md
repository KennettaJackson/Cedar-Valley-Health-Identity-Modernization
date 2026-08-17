# 🔄 Exception Scenario – Mover While on Leave

## Scenario

Cedar Valley Health has an employee who is currently on leave.

While the employee is away, HR submits an approved role-change request.

The employee will be transferring from Finance to Operations when they return.

For this scenario, I am using a new user who was not part of the previous JML scenarios so the workflow can be tested separately.

---

## Employee

**Name:** Ashley Morgan

**Current Role:** Financial Analyst

**Current Department:** Finance

**New Role:** Operations Analyst

**New Department:** Operations

**Status:** On Leave

---

## Business Request

HR submits a role-change request with the approved effective date.

The request includes:

- Employee name
- Current position
- New position
- Current department
- New department
- Effective date
- Authorized requestor/approver

The employee does not need to personally log into Entra or validate the organizational change.

The IAM team is relying on the authorized HR/business request.

---

## IAM Process

### 1. Validate the Request

I will verify that:

- The request came from an authorized source.
- The new role is documented.
- The effective date is clear.
- The requested access matches the new role.

### 2. Update the User

The user's relevant properties will be updated.

### 3. Update Access

Remove the user's previous Finance access where appropriate.

Assign:

`CVH-Operations-Team`

### 4. Verify

After making the changes, I will verify the user's group memberships and properties.

### 5. Audit Log Verification

I will review Microsoft Entra audit logs to confirm that the administrative changes were recorded.

---

## Why This Scenario Matters

The employee being on leave does not stop the organization from processing an approved role change.

The lifecycle event is based on an authorized business/HR decision, not on the employee personally logging into the identity system.

This scenario helped me understand that the employee does not have to be physically available for every lifecycle event.

The important part is having an authorized request, the correct effective date, appropriate access changes, and evidence that the change was completed.

---

## Evidence

Screenshots will include:

- HR request
- User properties before/after
- Group membership before/after
- Audit log event
- Final access state
