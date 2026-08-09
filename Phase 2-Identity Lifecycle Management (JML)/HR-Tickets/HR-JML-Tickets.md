# Phase 2 – HR JML Requests

---

## Ticket JML-001 – New Employee Onboarding

**Request Type:** Joiner  
**Requested By:** HR – Cedar Valley Health  
**Priority:** Normal  
**Status:** Completed

### Request

Cedar Valley Health has acquired a small outpatient clinic. Please provision the following employees in Microsoft Entra ID and assign access based on their job responsibilities:

- Dr. Emily Carter
- Jessica Brooks
- Michael Reed
- Olivia Harris
- Daniel Lewis
- Chloe Martin
- Corey Johnson
- Sophia Allen

### IAM Actions

- Users bulk-created using CSV.
- User properties reviewed.
- Appropriate security groups assigned.
- New clinic-related security groups created.
- Group memberships verified.

### Result

**Completed successfully.**

---

## Ticket JML-002 – Role Change: Corey Johnson

**Request Type:** Mover  
**Requested By:** HR  
**Priority:** Normal  
**Status:** Completed

### Request

Corey Johnson has moved from the IT Department into the role of **IAM Analyst**.

Please update his identity information and modify his access to reflect his new responsibilities.

### IAM Actions

- Updated user properties.
- Updated role/department.
- Removed previous IT-related access.
- Added **CVH-IAM-Team**.
- Verified group membership.
- Reviewed audit logs.

### Result

**Completed successfully.**

---

## Ticket JML-003 – Role Change: Mia Turner

**Request Type:** Mover  
**Requested By:** HR  
**Priority:** Normal  
**Status:** Completed

### Request

Mia Turner has transferred from Sales to Finance and is now a **Financial Analyst**.

Please update her identity information and modify her access accordingly.

### IAM Actions

- Updated department.
- Updated job title.
- Removed previous Sales-related access.
- Added appropriate Finance access.
- Verified group memberships.
- Reviewed audit logs.

### Result

**Completed successfully.**

---

## Ticket JML-004 – Promotion: Jessica Brooks

**Request Type:** Mover  
**Requested By:** HR  
**Priority:** Normal  
**Status:** Completed

### Request

Jessica Brooks has been promoted from Nurse to **Nurse Manager**.

Please update her access to reflect her new responsibilities.

### IAM Actions

- Updated role information.
- Removed **CVH-Nurses**.
- Added **CVH-Nurse-Managers**.
- Verified new access.
- Reviewed audit logs.

### Result

**Completed successfully.**

---

## Ticket JML-005 – Employee Termination: David King

**Request Type:** Leaver  
**Requested By:** HR  
**Priority:** High  
**Status:** Completed

### Request

David King is no longer employed by Cedar Valley Health.

Please immediately remove his access to company resources.

### IAM Actions

- Disabled account.
- Removed access and group memberships.
- Revoked active sessions.
- Confirmed account status.
- Verified that sign-in was no longer permitted.
- Reviewed audit logs.

### Result

**Completed successfully.**

### Security Consideration

The account was disabled to prevent future authentication. Active sessions were also revoked to reduce the risk of an already-authenticated session remaining usable after termination.

---

# Ticket Closure Standard

Each JML request was considered complete only after:

- The requested identity change was performed.
- Access was reviewed.
- Unnecessary access was removed where applicable.
- The resulting configuration was verified.
- Audit evidence was reviewed.
- The ticket outcome was documented.
