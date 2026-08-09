# Phase 2 – Joiner Documentation

## Overview

The Joiner process represents the onboarding of new employees into the Cedar Valley Health Microsoft Entra ID environment.

For this phase, Cedar Valley Health simulated the acquisition of a small outpatient clinic. Eight representative employees were provisioned into the existing identity environment.

The objective was to create the identities, populate appropriate identity information, assign role-based security groups, and verify the resulting configuration.

---

## Business Scenario

Cedar Valley Health acquired a small outpatient clinic.

The IAM team received an HR request to provision the incoming employees and provide access appropriate to their job responsibilities.

The onboarding request was documented as:

**JML-001 – New Employee Onboarding**

The HR request is documented in:

`../HR-Tickets/HR-JML-Tickets.md`

---

## Users Provisioned

Eight representative employees were provisioned:

1. Dr. Emily Carter
2. Jessica Brooks
3. Michael Reed
4. Olivia Harris
5. Daniel Lewis
6. Chloe Martin
7. Corey Johnson
8. Sophia Allen

---

## Provisioning Method

The users were bulk-created using Microsoft Entra ID CSV user provisioning.

The CSV provisioning process was used to simulate an efficient onboarding workflow rather than creating each user individually.

### User Information

The provisioned identities included relevant information such as:

- First name
- Last name
- Display name
- User Principal Name (UPN)
- Department
- Job title

---

## Security Groups

The acquisition required additional role-based security groups:

- CVH-Billing
- CVH-Front-Desk
- CVH-IAM-Team
- CVH-Nurse-Managers
- CVH-Nurses
- CVH-Physicians

These groups were used to organize users according to their job responsibilities.

---

## Joiner Workflow

The simulated onboarding workflow was:

1. HR provides employee information.
2. IAM reviews the onboarding request.
3. Users are bulk-created using CSV.
4. User properties are reviewed and populated.
5. Appropriate security group membership is assigned.
6. Access is reviewed against the employee's role.
7. Provisioning results are verified.
8. Relevant evidence is documented.

---

## Access Management

Access was organized through role-based security groups rather than assigning permissions individually to each user.

This approach supports:

- Role-Based Access Control (RBAC)
- Principle of Least Privilege
- Consistent access administration
- Easier access management as the organization grows

---

## Validation

The following were reviewed after provisioning:

- User accounts were created successfully.
- User properties were populated correctly.
- Appropriate security groups were assigned.
- Group memberships were verified.
- Provisioning activity was reviewed through Microsoft Entra administrative records.

---

## Evidence

Supporting screenshots are stored under:

`../Screenshots/Joiner/`

The screenshots provide evidence of the provisioning and access configuration performed during the lab.

---

## Result

The new clinic workforce was successfully represented within the Cedar Valley Health Microsoft Entra ID environment using CSV bulk provisioning and role-based security groups.

The Joiner process established the identities and initial access required for the employees to begin their assigned responsibilities.
