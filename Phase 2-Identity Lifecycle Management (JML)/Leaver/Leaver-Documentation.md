## Leaver

### Leaver Scenario – David King

David King was used to simulate an employee leaving Cedar Valley Health.

### HR Request

HR submitted a termination request requiring IAM to remove David’s access.

### IAM Actions

1. Disabled the account.
2. Removed group memberships/access.
3. Revoked active sessions.
4. Confirmed the account was disabled.
5. Attempted/verified sign-in was no longer permitted.
6. Reviewed audit logs for the administrative changes.
7. Documented the outcome.

### Security Objective

Prevent a former employee from continuing to access Cedar Valley Health resources after termination.

### Verification

The account was confirmed as disabled and the user was unable to sign in.

Audit logs were reviewed to provide evidence that the offboarding actions occurred.

---

# JML Security Principles

## Least Privilege

Users should receive only the access required for their current responsibilities.

## Role-Based Access Control

Security groups were used to organize access according to job roles and departments.

## Access Removal

Mover events require reviewing and removing obsolete access rather than simply adding new permissions.

## Secure Offboarding

Leaver processing requires more than disabling the account. Active sessions and access memberships should also be addressed.

## Auditability

Administrative actions were reviewed through Entra ID audit logs to provide evidence of lifecycle changes.

---

# Evidence

Screenshots for each scenario are stored under:

```text
/Screenshots/Joiner/

/Screenshots/Mover/

/Screenshots/Leaver/
