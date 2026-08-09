# Phase 2 – Leaver Documentation

## Overview

The Leaver process represents the secure offboarding of an employee who is no longer employed by Cedar Valley Health.

For this phase, David King was used to simulate an employee termination.

The objective was to disable the identity, remove access, revoke active sessions, verify the account could no longer sign in, and review the administrative activity through Microsoft Entra audit logs.

---

## Business Scenario

David King was used to simulate an employee leaving Cedar Valley Health.

The IAM team received an HR termination request requiring the employee's access to be removed.

The request was documented as:

**JML-005 – Employee Termination: David King**

The HR request is documented in:

`../HR-Tickets/HR-JML-Tickets.md`

---

## HR Request

HR submitted a termination request requiring IAM to immediately remove David King's access to company resources.

The request was treated as a high-priority lifecycle event.

---

## IAM Actions

The following actions were performed:

1. Disabled the account.
2. Removed access and group memberships.
3. Revoked active sessions.
4. Confirmed the account status.
5. Verified that sign-in was no longer permitted.
6. Reviewed Microsoft Entra audit logs.
7. Documented the outcome.

---

## Security Rationale

Disabling the account prevents future authentication attempts.

However, disabling an account alone does not necessarily address existing authenticated sessions.

For this reason, active sessions were also revoked.

Group memberships and other assigned access were removed to reduce the possibility of the former employee retaining access through previously assigned permissions.

---

## Verification

The following were verified during the offboarding process:

- David King's account was disabled.
- Access and group memberships were removed.
- Active sessions were revoked.
- The account could no longer be used to sign in.
- Administrative changes appeared in Microsoft Entra audit logs.

---

## Audit Verification

Microsoft Entra audit logs were reviewed to provide evidence of the administrative changes performed during the offboarding process.

The audit review helped verify that the requested lifecycle actions were completed.

---

## Leaver Workflow

The simulated Leaver workflow was:

1. HR submits a termination request.
2. IAM reviews the request.
3. The user account is disabled.
4. Existing access is removed.
5. Group memberships are removed.
6. Active sessions are revoked.
7. Account status is verified.
8. Sign-in is tested/verified as no longer permitted.
9. Audit activity is reviewed.
10. The ticket outcome is documented.

---

## Evidence

Supporting screenshots are stored under:

`../Screenshots/Leaver/`

The screenshots provide evidence of the account disablement, access removal, session revocation, and verification performed during the lab.

---

## Result

David King's account was successfully offboarded from the Cedar Valley Health Microsoft Entra ID environment.

The Leaver process demonstrated that secure offboarding requires more than disabling an account. Access, group memberships, active sessions, and verification should also be addressed.
