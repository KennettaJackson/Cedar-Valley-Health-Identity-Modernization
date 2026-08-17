# 🔎 Phase 3 – Access Review Documentation

## Purpose

Cedar Valley Health is conducting a quarterly access review six months after the clinic acquisition.

The purpose of the review is to determine whether selected users still have the access they need based on their current job responsibilities.

I am using Microsoft Entra Access Reviews to practice reviewing access instead of assuming that access is still appropriate simply because it was originally granted.

---

## Review Process

The process I am following is:

**Identify → Review → Decide → Remediate → Verify → Document**

For each user, I will look at:

- Current department
- Current job title
- Current security group membership
- Why the user has the access
- Whether the access is still needed
- Whether any remediation is necessary

---

# 👥 Employee Access Review

The first review will include selected users from different areas of Cedar Valley Health.

| User | Current Role | Access Reviewed | Decision |
|---|---|---|---|
| Dr. Emily Carter | Physician | CVH-Physicians | Approve |
| Jessica Brooks | Nurse Manager | CVH-Nurse-Managers | Approve |
| Mia Turner | Financial Analyst | CVH-Finance-Team | Approve |
| Rachel Thompson | Financial Analyst | CVH-Sales-Team | Remove |
| Corey Johnson | IAM Analyst | CVH-IAM-Team | Approve |
| Taylor Brooks | IT Support Specialist | CVH-IAM-Team | Remove |
| Jordan Crosby | IAM Analyst | CVH-IAM-Team | Approve |

Most of the users are expected to have appropriate access. The purpose is to identify any access that no longer matches the user's current responsibilities.

---

# ⚠️ Finding – Rachel Thompson

Rachel Thompson is currently a Financial Analyst in the Finance department.

Her required access is:

`CVH-Finance-Team`

Several months earlier, Rachel temporarily helped the Sales department with a reporting project.

She was given:

`CVH-Sales-Team`

The project has ended, but the Sales access was never removed.

The access was originally appropriate for a legitimate business reason. The issue is that Rachel no longer needs it for her current position.

### Decision

**Remove `CVH-Sales-Team`**

### Remediation

Rachel was removed from:

`CVH-Sales-Team`

Her required Finance access remained assigned:

`CVH-Finance-Team`

### Verification

After the change, I will verify that:

- Rachel is no longer a member of `CVH-Sales-Team`
- Rachel remains a member of `CVH-Finance-Team`
- The related administrative activity appears in the Microsoft Entra audit logs

Screenshots will be stored in the project repository.

---

# 👤 IAM Team Access Review

The IAM team will also be reviewed.

The purpose is to determine whether members of the `CVH-IAM-Team` group still need IAM-related access based on their current responsibilities.

Two additional fictional IAM team members will be added for this review so the group contains more than just Corey Johnson.

The review will include:

- Current role
- Current responsibilities
- Membership in `CVH-IAM-Team`
- Whether IAM access is still required

If a user no longer performs IAM-related duties, their access will be removed.

---

# 🔎 Audit Verification

After remediation, I will review the Microsoft Entra audit logs.

The purpose is to verify that the administrative change was actually recorded.

I will look for relevant events such as:

- Group membership removal
- Group membership addition
- User property changes
- Account disablement

The audit log provides evidence that the change occurred instead of relying only on the final configuration.

---

# 📸 Evidence

Screenshots will be organized in the project repository.

### Access Reviews

`Screenshots/Access-Reviews/`

### Remediation

`Screenshots/Remediation/`

### Audit Logs

`Screenshots/Audit-Logs/`

---

# 📊 Access Review Results

The detailed review results will also be maintained in:

`Phase-3-Access-Review-Results.xlsx`

The spreadsheet will track:

- User
- Department
- Job title
- Access reviewed
- Business need
- Decision
- Remediation
- Verification
- Audit log evidence
- Final status

---

## Conclusion

This review demonstrates that access should not be treated as permanent.

A user can receive legitimate access for a business reason and later no longer need it because their role, responsibilities, or project has changed.

The goal of this review is to identify those situations, make the appropriate decision, remediate the access, and verify the result.

**Review → Decide → Remediate → Verify → Prove**
