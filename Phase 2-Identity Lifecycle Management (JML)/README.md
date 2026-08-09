🔐 Phase 2 – Identity Lifecycle Management (JML)

Project: Cedar Valley Health – Microsoft Entra ID IAM Lab
Phase: 2
Focus: Joiner, Mover, Leaver (JML)
Platform: Microsoft Entra ID



📋 Overview

In Phase 2, I expanded the Cedar Valley Health (CVH) IAM environment by simulating the acquisition of a small healthcare clinic.

The acquisition introduced new employees and clinical/business roles that needed to be onboarded into the existing Microsoft Entra ID environment.

I used this scenario to practice the Joiner, Mover, and Leaver (JML) identity lifecycle.

The goal was not simply to create and modify accounts, but to demonstrate how IAM supports the employee lifecycle through appropriate provisioning, access changes, access removal, and secure offboarding.



🏥 Business Scenario

Cedar Valley Health Acquires a Small Clinic

Cedar Valley Health has acquired a small outpatient clinic.

As part of the acquisition, the IAM team was responsible for integrating new employees into the existing identity environment while ensuring users received access appropriate to their job responsibilities.

The IAM team needed to:

Provision new employees
Assign appropriate security groups
Maintain accurate identity attributes
Modify access when employees changed roles
Remove unnecessary access during role changes
Disable accounts when employees left the organization
Revoke active sessions during offboarding
Review audit logs to verify IAM actions
Maintain documentation and HR requests for lifecycle changes
This phase demonstrates the importance of the Principle of Least Privilege and Role-Based Access Control (RBAC) throughout the identity lifecycle.



🎯 Objectives

The objectives for Phase 2 were to:

Practice bulk user provisioning using CSV
Create and manage role-based security groups
Provision users based on department and job responsibilities
Update identity properties when employees change roles
Remove previous access before assigning new access
Simulate employee offboarding
Revoke active sessions
Verify disabled accounts cannot sign in
Review Microsoft Entra audit logs
Simulate HR-driven IAM requests through tickets
Document IAM decisions and outcomes


🔄 JML Lifecycle

Lifecycle Stage

Scenario

Status

👤 Joiner

Onboard employees from acquired clinic

✅ Complete

🔄 Mover

Modify access after role/department changes

✅ Complete

🚪 Leaver

Securely offboard terminated employee

✅ Complete

🔎 Audit

Review administrative activity and verify changes

✅ Complete



👤 1. Joiner – New Employee Provisioning

Acquisition Onboarding

As part of the clinic acquisition, eight representative employees were onboarded into Cedar Valley Health.

New Users

User

Lifecycle Event

Method

Dr. Emily Carter

Joiner

CSV Bulk Provisioning

Jessica Brooks

Joiner

CSV Bulk Provisioning

Michael Reed

Joiner

CSV Bulk Provisioning

Olivia Harris

Joiner

CSV Bulk Provisioning

Daniel Lewis

Joiner

CSV Bulk Provisioning

Chloe Martin

Joiner

CSV Bulk Provisioning

Corey Johnson

Joiner

CSV Bulk Provisioning

Sophia Allen

Joiner

CSV Bulk Provisioning

The users were bulk-created using a CSV import.

After provisioning, user properties and security group memberships were reviewed to ensure each identity was associated with the appropriate department and role.



👥 New Security Groups

The acquisition also required additional role-based security groups:

CVH-Billing
CVH-Front-Desk
CVH-IAM-Team
CVH-Nurse-Managers
CVH-Nurses
CVH-Physicians
These groups were used to organize access according to job responsibilities rather than assigning permissions individually.

IAM Concept Demonstrated

Role-Based Access Control (RBAC)

Users are assigned access based on their job responsibilities and organizational role.



🛠️ Joiner Process

The simulated onboarding workflow included:

HR provides employee information.
IAM provisions the identity.
User properties are populated.
Appropriate security group membership is assigned.
Access is reviewed against the employee’s role.
Provisioning activity is verified.
Relevant screenshots and evidence are documented.
Result

The new clinic workforce was successfully represented within the CVH Entra ID environment using role-based security groups.



🔄 2. Mover – Role Changes

The Mover portion simulated employees changing departments or responsibilities after joining Cedar Valley Health.

The focus was on ensuring that employees did not accumulate unnecessary access when their responsibilities changed.



🔄 Scenario 1 – Corey Johnson

Role Change

Previous: IT Department
New Role: IAM Analyst

IAM Actions

Updated the user’s properties
Updated department/role information
Removed previous IT-related group access
Added the user to CVH-IAM-Team
Reviewed resulting group memberships
Verified the changes through Microsoft Entra audit logs
IAM Principle

When an employee changes roles, their previous access should not automatically remain indefinitely.

Corey’s access was reviewed and adjusted to align with his new IAM Analyst responsibilities.



🔄 Scenario 2 – Mia Turner

Role Change

Previous: Sales
New Role: Financial Analyst
New Department: Finance

IAM Actions

Updated user properties
Changed department from Sales to Finance
Updated job title
Removed Sales-related group access
Added appropriate Finance-related group access
Verified updated memberships
Reviewed audit logs
IAM Principle

A department change can require both removal and addition of access.

Simply adding new access without removing old permissions could result in excessive access over time.



🔄 Scenario 3 – Jessica Brooks

Promotion

Previous Role: Nurse
New Role: Nurse Manager

IAM Actions

Updated her role/job information
Removed CVH-Nurses
Added CVH-Nurse-Managers
Verified the new group membership
Reviewed the audit logs
IAM Principle

When an employee receives a promotion or assumes new responsibilities, their access should be reviewed and adjusted to match their current role.

Jessica’s previous nurse-level access was removed before assigning the Nurse Manager group.



🚪 3. Leaver – Employee Offboarding

Scenario – David King

David King was used to simulate an employee leaving Cedar Valley Health.

The IAM team received an HR termination request.

IAM Actions

Disabled the account
Removed access
Removed group memberships
Revoked active sessions
Confirmed the account was disabled
Verified the user could no longer sign in
Reviewed Microsoft Entra audit logs


🔒 Security Rationale

Disabling the account prevents future authentication attempts.

However, disabling an account alone does not necessarily address existing authenticated sessions.

For this reason, active sessions were also revoked.

Group memberships and other assigned access were removed to reduce the possibility of the former employee retaining access through previously assigned permissions.



🔎 Audit & Verification

Audit logs were reviewed throughout the JML process to verify administrative changes.

The audit review included activities such as:

User creation
User property changes
Group membership changes
Account disabling
Session revocation
Other relevant identity administration activities
Verification

The following were verified during the lab:

User accounts were created successfully
Appropriate security groups were assigned
Previous access was removed during role changes
New access was assigned according to the employee’s new role
Administrative changes appeared in audit logs
David King’s account was disabled
David King was unable to sign in after offboarding
Active sessions were revoked during the leaver process
Screenshots of relevant evidence are stored in the Screenshots directory.



🎫 HR-to-IAM Ticket Workflow

To simulate a real IAM operational environment, HR requests were represented through JML tickets.

The tickets covered:

Joiner

JML-001 – New Employee Onboarding

Request to provision the eight employees from the acquired clinic.

Mover

JML-002 – Corey Johnson

IT Department → IAM Analyst

JML-003 – Mia Turner

Sales → Finance / Financial Analyst

JML-004 – Jessica Brooks

Nurse → Nurse Manager

Leaver

JML-005 – David King

Employee termination and access removal.

The HR ticket documentation is stored separately in:

HR-Tickets/HR-JML-Tickets.md



🧰 Tools & Technologies

Microsoft Entra ID
Microsoft Entra Users
Microsoft Entra Groups
CSV Bulk User Provisioning
Microsoft Entra Audit Logs
Sign-in Verification
Account Management
Security Groups
Identity Lifecycle Management


🧪 Lab Environment

This project was completed using Microsoft Entra ID Free.

Premium capabilities such as:

Identity Governance
Access Reviews
Privileged Identity Management (PIM)
Entitlement Management
Other premium identity features
are reserved for later phases where applicable.

This phase focuses primarily on the core identity lifecycle process and does not require Microsoft 365 license assignment.



🔐 Key IAM Concepts Demonstrated

IAM Concept

How It Was Demonstrated

Joiner

Bulk-created new clinic employees

Mover

Modified access after role/department changes

Leaver

Disabled and offboarded a terminated employee

RBAC

Used security groups based on job responsibilities

Least Privilege

Removed unnecessary access during role changes

Provisioning

Created and configured user identities

Deprovisioning

Removed access and disabled a departing employee

Access Modification

Updated groups and user properties

Session Revocation

Revoked active sessions during offboarding

Auditability

Reviewed Entra ID audit logs

HR-to-IAM Workflow

Simulated lifecycle requests through tickets



🧠 Lessons Learned

Phase 2 demonstrated that IAM is not simply about creating accounts.

Access needs to follow the employee’s current business responsibilities throughout the identity lifecycle.

The Mover scenarios especially demonstrated why access should be reviewed when an employee changes roles.

Adding new access without removing obsolete access can gradually lead to excessive permissions and violate the Principle of Least Privilege.

The Leaver scenario also demonstrated why disabling an account is only one part of the offboarding process.

Existing sessions, group memberships, and other access should also be addressed.



📊 Phase 2 Outcome

The JML process was successfully simulated for Cedar Valley Health’s acquired clinic.

The project demonstrated the ability to:

Provision → Modify → Verify → Deprovision

This phase established the foundation for the next stage of the project:

🚀 Phase 3 – Identity Governance & Access Reviews

In Phase 3, Cedar Valley Health will evaluate whether users continue to have appropriate access after being provisioned and after experiencing role changes.

The focus will shift from:

“Did we give the user access?”

to:

“Does the user still need this access?”



📁 Repository Structure

Phase 2 - Identity Lifecycle Management (JML)/

│

├── README.md

│

├── Joiner/

│   └── joiner-documentation.md

│

├── Mover/

│   └── mover-documentation.md

│

├── Leaver/

│   └── leaver-documentation.md

│

├── HR-Tickets/

│   └── HR-JML-Tickets.md

│

└── Screenshots/

    ├── Joiner/

    ├── Mover/

    └── Leaver/
