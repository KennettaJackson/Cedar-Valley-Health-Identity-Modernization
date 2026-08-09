# Phase 2 – Mover Documentation

## Overview

The Mover process represents employees changing departments, roles, or responsibilities within Cedar Valley Health.

The objective was to ensure that user access changed along with the employee's current responsibilities.

The Mover scenarios focused on reviewing existing access, removing obsolete permissions, assigning appropriate new access, and verifying the resulting configuration.

---

## Mover Security Principle

When an employee changes roles, their previous access should be reviewed rather than automatically retained.

Simply adding new permissions without removing obsolete access can result in excessive access over time.

The Mover process therefore supports:

- Role-Based Access Control (RBAC)
- Principle of Least Privilege
- Access modification
- Access removal
- Prevention of permission creep

---

# Scenario 1 – Corey Johnson

## Role Change

**Previous Role:** IT Department  
**New Role:** IAM Analyst

### IAM Actions

- Updated user properties.
- Updated department/role information.
- Removed previous IT-related access.
- Added **CVH-IAM-Team**.
- Verified group membership.
- Reviewed audit logs.

### Security Objective

Ensure Corey receives access appropriate to his new IAM responsibilities without retaining unnecessary access from his previous IT role.

### Verification

The resulting group membership and user properties were reviewed after the role change.

Microsoft Entra audit logs were reviewed to verify the administrative changes.

---

# Scenario 2 – Mia Turner

## Role Change

**Previous Role:** Sales  
**New Role:** Financial Analyst  
**New Department:** Finance

### IAM Actions

- Updated user properties.
- Changed department from Sales to Finance.
- Updated job title.
- Removed previous Sales-related access.
- Added appropriate Finance-related access.
- Verified group memberships.
- Reviewed audit logs.

### Security Objective

Prevent access accumulation by removing permissions associated with the previous position before assigning access required for the new role.

### Verification

The updated identity information and resulting group memberships were reviewed.

Microsoft Entra audit logs were reviewed to verify the administrative changes.

---

# Scenario 3 – Jessica Brooks

## Promotion

**Previous Role:** Nurse  
**New Role:** Nurse Manager

### IAM Actions

- Updated role information.
- Removed **CVH-Nurses**.
- Added **CVH-Nurse-Managers**.
- Verified new access.
- Reviewed audit logs.

### Security Objective

Align Jessica's access with her increased responsibilities while removing the previous role-based access.

### Verification

The previous nurse group membership was removed and the Nurse Manager group membership was verified.

Microsoft Entra audit logs were reviewed to verify the administrative changes.

---

# Mover Workflow

The simulated Mover workflow was:

1. HR submits a role or department change request.
2. IAM reviews the requested change.
3. User identity properties are updated.
4. Existing access is reviewed.
5. Obsolete access is removed.
6. New role-based access is assigned.
7. Resulting group memberships are verified.
8. Audit logs are reviewed.
9. The lifecycle request is documented.

---

# Evidence

Supporting screenshots are stored under:

`../Screenshots/Mover/`

The screenshots provide evidence of the role changes, access modifications, and verification performed during the lab.

---

## Result

The Mover scenarios demonstrated that access should follow an employee's current business responsibilities.

Previous access was reviewed and removed where appropriate before new role-based access was assigned.
