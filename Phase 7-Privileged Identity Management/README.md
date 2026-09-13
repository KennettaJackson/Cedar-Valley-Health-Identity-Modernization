# 🔐 Phase 7 — Privileged Identity Management

## 🏥 Cedar Valley Health Identity Modernization

### 🎥 Video Overview

>  **https://www.loom.com/share/88906966a36a46fc94f228ee1a57b0ae**

This short walkthrough demonstrates the CVH privileged identity management scenario, including the transition from standing administrative privileges to eligible access, just-in-time role activation, temporary administrative access, and PIM audit validation.

---

## 📋 Overview

This phase demonstrates the implementation of **Microsoft Entra Privileged Identity Management (PIM)** to reduce standing administrative privileges within Cedar Valley Health.

Two CVH users already held **standing User Administrator privileges** from previous identity administration labs:

* 👤 **Michael Rivera** — IT Department
* 👤 **Corey Johnson** — IAM Analyst

As part of the CVH identity modernization effort, their standing administrative access was transitioned to **eligible PIM assignments**.

This allowed both users to retain the ability to perform User Administrator responsibilities while requiring them to activate their privileged role only when administrative access was needed.

---

## 🎯 Security Objective

The original access model was:

```text id="f7x3kp"
Michael Rivera
      ↓
User Administrator
      ↓
🔴 Standing Active Privilege
```

```text id="n5r8wd"
Corey Johnson
      ↓
User Administrator
      ↓
🔴 Standing Active Privilege
```

The improved model became:

```text id="k4m7qx"
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
      │
      ▼
🟢 Eligible
```

```text id="r8c2vz"
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
      │
      ▼
🟢 Eligible
```

---

## 🖥️ Environment

| Component                 | Configuration                   |
| ------------------------- | ------------------------------- |
| 🆔 Identity Platform      | Microsoft Entra ID              |
| 🔐 Privileged Access Tool | Microsoft Entra PIM             |
| 👤 User 1                 | Michael Rivera                  |
| 👤 User 2                 | Corey Johnson                   |
| 🛡️ Privileged Role       | User Administrator              |
| 🔴 Initial Access Model   | Standing Active Privilege       |
| 🟢 Target Access Model    | Eligible                        |
| ⏱️ Activation Model       | Just-in-Time                    |
| 📊 Validation             | PIM Assignments & Audit History |

---

## 👥 CVH Privileged Users

### 👨 Michael Rivera — IT Department

Michael Rivera performs user administration responsibilities within the CVH IT department.

Prior to Phase 7, Michael had a **standing User Administrator assignment**.

The PIM implementation transitioned Michael from:

**Standing Active → Eligible**

Michael can now activate User Administrator privileges when administrative work is required.

---

### 👨 Corey Johnson — IAM Analyst

Corey Johnson performs identity administration responsibilities as an IAM Analyst.

Prior to Phase 7, Corey also had a **standing User Administrator assignment**.

The PIM implementation transitioned Corey from:

**Standing Active → Eligible**

Corey can now activate User Administrator privileges when administrative work is required.

---

## 🔄 Privileged Access Workflow

The CVH PIM workflow follows a just-in-time access model:

```text id="z6w3pn"
              Administrative Need
                      │
                      ▼
                Eligible Role
                      │
                      │ Activation Request
                      ▼
                MFA / Controls
                      │
                      ▼
              Temporary Privilege
                      │
                      ▼
             Administrative Work
                      │
                      ▼
                  Expiration
                      │
                      ▼
              Eligible / Inactive
```

---

## ⚙️ Implementation

The implementation consisted of:

1. 🔎 Reviewing existing standing User Administrator assignments
2. 🛡️ Identifying the need to reduce standing privilege
3. 🔄 Transitioning Michael Rivera to an eligible assignment
4. 🔄 Transitioning Corey Johnson to an eligible assignment
5. 🔑 Testing role activation
6. ⏱️ Validating temporary privileged access
7. 📝 Reviewing activation justification
8. 📊 Reviewing PIM audit history
9. 🔄 Confirming the final eligible state

---

## 🧪 Validation

The implementation was validated through:

* ✅ Review of the original standing assignments
* 🟢 Eligible role assignments
* 🔑 Successful role activation
* 📝 Activation justification
* ⏱️ Temporary privileged access
* 📊 PIM audit history
* 🔄 Post-activation role state
* 🛡️ Controlled administrative testing

---

## 🧠 Key IAM Concepts Demonstrated

* 🔐 Privileged Identity Management
* 🛡️ Least privilege
* ⏱️ Just-in-time access
* 🔴 Standing administrative access
* 🟢 Eligible assignments
* 🟡 Active assignments
* 🔑 Privileged role activation
* 📝 Activation justification
* ⏳ Time-limited privilege
* 📊 Privileged access auditing
* 🔄 Privilege lifecycle management

---

## 📸 Evidence

Screenshots and supporting documentation are maintained in the `Documentation` directory.

Evidence focuses on:

1. 👥 Initial standing administrative access
2. 🔄 Michael Rivera's transition to eligible access
3. 🔄 Corey Johnson's transition to eligible access
4. 🔑 Michael Rivera's role activation
5. ⏱️ Michael Rivera's temporary active role
6. 📊 Michael Rivera's PIM audit event
7. 🔑 Corey Johnson's role activation
8. ⏱️ Corey Johnson's temporary active role
9. 📊 Corey Johnson's PIM audit event
10. 🔄 Final eligible state


---

## 🛡️ Security Improvement

### Before Phase 7

```text id="q3x7mk"
Standing Administrative Access
            │
            ▼
User Administrator
            │
            ▼
     Active Continuously
```

### After Phase 7

```text id="c9v4ra"
Eligible Access
      │
      │ Activate when needed
      ▼
Temporary Active Privilege
      │
      ▼
Administrative Work
      │
      ▼
Expiration
      │
      ▼
Eligible
```

The change reduces the amount of time privileged administrative access remains active while preserving authorized administrative functionality.

---

## 🏁 Outcome

Cedar Valley Health successfully transitioned two existing User Administrators from **standing administrative access** to a **just-in-time privileged access model** using Microsoft Entra PIM.

| User              | Previous State     | Final State |
| ----------------- | ------------------ | ----------- |
| 👨 Michael Rivera | 🔴 Standing Active | 🟢 Eligible |
| 👨 Corey Johnson  | 🔴 Standing Active | 🟢 Eligible |

Both users retained the ability to activate the User Administrator role when needed while eliminating unnecessary continuous active privilege.

Their privileged activations were also recorded through PIM auditing, providing visibility into privileged access usage.

---

## 💡 Key Takeaway

> **Authorized administrative access does not have to mean permanent administrative access.**

Phase 7 demonstrates how CVH can maintain operational access for trusted administrators while applying **least privilege, just-in-time elevation, temporary access, and auditability**.






