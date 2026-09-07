# 🔐 Phase 7 — Privileged Identity Management Lab

## 🏥 Cedar Valley Health Identity Modernization

**Platform:** Microsoft Entra ID
**Security Control:** Microsoft Entra Privileged Identity Management
**Privileged Role:** User Administrator
**Test User 1:** Michael Rivera
**Test User 2:** Corey Johnson

---

# 1. Scenario

Cedar Valley Health previously assigned administrative privileges directly to employees who required identity administration capabilities.

Two CVH users had **standing administrative privileges** from earlier identity administration labs:

* **Michael Rivera** — IT Department
* **Corey Johnson** — IAM Analyst

Both users held the **User Administrator** role with standing administrative access.

As part of CVH's identity modernization effort, the organization wanted to reduce standing privileged access and implement a **just-in-time (JIT)** administrative model.

Microsoft Entra Privileged Identity Management (PIM) was introduced to replace the users' standing active assignments with **eligible assignments**.

### Before PIM

```text id="6f2wq8"
Michael Rivera
      ↓
User Administrator
      ↓
🔴 Standing Active Privilege
```

```text id="m7k3rx"
Corey Johnson
      ↓
User Administrator
      ↓
🔴 Standing Active Privilege
```

### After PIM

```text id="p8v4nd"
Michael Rivera
      ↓
User Administrator
      ↓
🟢 Eligible
      │
      │ Activate when needed
      ▼
🟡 Temporary Active Access
      │
      ▼
⏳ Expiration
```

```text id="q5c9tz"
Corey Johnson
      ↓
User Administrator
      ↓
🟢 Eligible
      │
      │ Activate when needed
      ▼
🟡 Temporary Active Access
      │
      ▼
⏳ Expiration
```

---

# 2. Business Objective

The objective was to reduce the amount of time privileged administrative access remained active while allowing authorized CVH administrators to continue performing their responsibilities.

The PIM implementation was designed around four principles:

* 🛡️ Least privilege
* ⏱️ Just-in-time access
* 🔑 Temporary elevation
* 📊 Auditable privileged activity

---

# 3. Objectives

The objectives of this lab were to:

* Identify existing standing administrative privileges
* Replace standing User Administrator access with eligible assignments
* Configure Microsoft Entra PIM
* Demonstrate just-in-time role activation
* Require appropriate activation controls
* Perform controlled administrative testing
* Review privileged access audit information
* Validate the final privileged-access state

---

# 4. Initial State

Before implementing PIM, both users had standing User Administrator privileges as a result of assignments established during previous CVH identity administration labs.

| User           | Department / Role | Privileged Role    | Initial State      |
| -------------- | ----------------- | ------------------ | ------------------ |
| Michael Rivera | IT Department     | User Administrator | 🔴 Standing Active |
| Corey Johnson  | IAM Analyst       | User Administrator | 🔴 Standing Active |

This created unnecessary standing administrative access.

The purpose of Phase 7 was therefore **not to introduce new administrative responsibilities**, but to improve the security model surrounding existing responsibilities.

---

# 5. Security Improvement

The existing model was:

```text id="w6n4ph"
Administrative Need
       ↓
Permanent Active Role
       ↓
Standing Privilege
```

The improved model became:

```text id="c3r8xm"
Administrative Need
       ↓
Eligible Assignment
       ↓
Activation Request
       ↓
Verification / Justification
       ↓
Temporary Active Role
       ↓
Administrative Work
       ↓
Expiration
       ↓
Eligible
```

This reduced the amount of time each administrator maintained active privileged access.

---

# 6. Michael Rivera

## User

**Michael Rivera**

## Department

**IT**

## Privileged Role

**User Administrator**

### Initial State

Michael initially had:

**User Administrator — Active**

This standing assignment was created during an earlier CVH identity administration lab.

### PIM Target State

The standing assignment was replaced with:

**User Administrator — Eligible**

Michael remained authorized to perform User Administrator duties, but the role would only become active when explicitly activated.

---

# 7. Michael Rivera — PIM Assignment

Navigation:

```text id="2p7x6m"
Microsoft Entra Admin Center
        ↓
Identity Governance
        ↓
Privileged Identity Management
        ↓
Microsoft Entra Roles
        ↓
Assignments
```

Michael's existing standing assignment was reviewed before the PIM change.

The target assignment was configured as:

**User Administrator → Eligible**

The eligibility was configured as permanent.

This means Michael remains eligible to activate the role when required but does not maintain continuous active administrative access.

---

# 8. Michael Rivera — Activation

Michael accessed:

**PIM → My roles**

The User Administrator role appeared as:

**Eligible**

Michael selected:

**Activate**

The activation process used the available security controls configured in the environment.

### Example justification

> Performing scheduled CVH user administration and validating privileged access controls.

After successful activation, the role became temporarily active.

```text id="h4k9cs"
Michael Rivera
      ↓
User Administrator
      ↓
🟢 Eligible
      │
      │ Activate
      ▼
🟡 Active
      │
      ▼
⏳ Temporary access
```

---

# 9. Michael Rivera — Administrative Validation

While the User Administrator role was active, Michael performed a controlled administrative task.

The purpose of the task was to validate that the PIM activation provided the required administrative capability.

The test was intentionally limited to the CVH lab environment.

---

# 10. Michael Rivera — Audit Validation

PIM audit information was reviewed after activation.

The review focused on:

* User
* Role
* Activation time
* Expiration
* Justification
* Result

This provided evidence that Michael's privileged access was activated and recorded.

---

# 11. Corey Johnson

## User

**Corey Johnson**

## Role

**IAM Analyst**

## Privileged Role

**User Administrator**

### Initial State

Corey also had:

**User Administrator — Active**

from previous CVH identity administration work.

### PIM Target State

The standing active assignment was replaced with:

**User Administrator — Eligible**

---

# 12. Corey Johnson — PIM Assignment

Corey's existing User Administrator assignment was reviewed.

The standing administrative access was replaced with an eligible PIM assignment.

Configuration:

**User Administrator → Eligible**

**Eligibility:** Permanent

Corey retained the ability to perform administrative work but would now activate the privileged role only when required.

---

# 13. Corey Johnson — Activation

Corey accessed:

**PIM → My roles**

Corey selected:

**User Administrator → Activate**

### Example justification

> Performing CVH identity administration and validating just-in-time privileged access.

After completing the required activation controls, Corey received temporary active User Administrator access.

```text id="v2r8nb"
Corey Johnson
      ↓
User Administrator
      ↓
🟢 Eligible
      │
      │ Activate
      ▼
🟡 Active
      │
      ▼
⏳ Temporary access
```

---

# 14. Corey Johnson — Administrative Validation

Corey performed a controlled User Administrator task while the role was active.

The purpose was to verify that the elevated role provided the expected administrative capability.

No unnecessary production changes were performed.

---

# 15. Corey Johnson — Audit Validation

PIM audit history was reviewed to validate Corey's activation.

The investigation focused on:

* User
* Role
* Activation time
* Duration
* Justification
* Result

This demonstrated that privileged activity was recorded and auditable.

---

# 16. Final State

After the PIM implementation, the standing administrative assignments were replaced with eligible assignments.

| User           | Role               | Before             | After       |
| -------------- | ------------------ | ------------------ | ----------- |
| Michael Rivera | User Administrator | 🔴 Standing Active | 🟢 Eligible |
| Corey Johnson  | User Administrator | 🔴 Standing Active | 🟢 Eligible |

The final architecture is:

```text id="k8m3qy"
                 CVH
                  │
                  ▼
          Microsoft Entra ID
                  │
                  ▼
                 PIM
                  │
        ┌─────────┴─────────┐
        ▼                   ▼
 Michael Rivera        Corey Johnson
      IT                  IAM Analyst
        │                   │
        ▼                   ▼
 User Administrator   User Administrator
        │                   │
        ▼                   ▼
     Eligible            Eligible
        │                   │
        └─────────┬─────────┘
                  ▼
          Activate when needed
                  │
                  ▼
         Temporary privilege
                  │
                  ▼
              Expiration
                  │
                  ▼
              Eligible
```

---

# 17. Security Improvement

The implementation changed CVH's privileged-access model from:

**Standing privilege**

to:

**Just-in-time privilege**

### Before

```text id="e2y6hf"
User
 ↓
User Administrator
 ↓
Active continuously
```

### After

```text id="n5c8ra"
User
 ↓
Eligible
 ↓
Activate
 ↓
Temporary Active
 ↓
Expiration
 ↓
Eligible
```

This reduces unnecessary standing administrative access while maintaining operational capability.


---

# 18. Key IAM Concepts Demonstrated

* 🔐 Privileged Identity Management
* 🛡️ Least privilege
* ⏱️ Just-in-time access
* 🔴 Standing privileged access
* 🟢 Eligible assignments
* 🟡 Active assignments
* 🔑 Role activation
* 📝 Activation justification
* ⏳ Temporary privilege
* 📊 Privileged access auditing
* 🔄 Privilege lifecycle management

---

# 19. Lessons Learned

The most significant improvement was recognizing that **having a legitimate administrative need does not require permanent administrative access**.

Michael Rivera and Corey Johnson still require User Administrator capabilities as part of their CVH responsibilities.

However, PIM changes how that privilege is provided:

> **Eligible when not needed. Active only when required.**

This provides a more controlled privileged-access model while preserving administrative functionality.

---

# 20. Final Result

Cedar Valley Health successfully transitioned two existing User Administrators from **standing administrative access** to a **just-in-time privileged access model** using Microsoft Entra PIM.

### Michael Rivera

**User Administrator → Eligible**

### Corey Johnson

**User Administrator → Eligible**

Both users successfully demonstrated privileged role activation, temporary administrative access, controlled administrative testing, and auditable activation events.

The final implementation reduced standing privilege while maintaining the ability for authorized administrators to perform their required IAM responsibilities.

---

# 21. Portfolio Takeaway

This scenario demonstrates practical experience with:

**Existing Privilege → PIM → Eligible Access → JIT Activation → Temporary Privilege → Audit**

The lab demonstrates how an IAM administrator can identify standing administrative access and transition it to a more secure, auditable privileged-access model.
