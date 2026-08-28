# 🔐 Phase 5 — Conditional Access Documentation

## 📋 Overview

Phase 5 focused on implementing and testing Microsoft Entra Conditional Access policies within the Cedar Valley Health (CVH) identity environment.

The goal was to practice how Conditional Access evaluates users, resources, authentication requirements, and network/location signals before allowing or denying access.

### Lab Activities

- 🚨 Emergency / break-glass account
- 🔑 MFA Conditional Access
- 🚫 Application/resource access blocking
- 📍 Location-based Conditional Access
- 🧪 Report-only testing
- 📊 Sign-in log analysis
- ✅ Policy enforcement

---

# 🧪 Lab Environment

## Platform

- Microsoft Entra ID
- Microsoft Entra Conditional Access
- Microsoft Entra ID P2


## Test Users

### 🔑 MFA Scenario

`Jordan Crosby`

### 🚫 Application/Resource Block Scenario

`Danielle Carter`

## Emergency Access Account

`CVH-BreakGlass-01`

---

# 🚨 Break-Glass Account

## Objective

Create an emergency access account that could be used if normal administrative access became unavailable because of a Conditional Access configuration issue.

## Account Created

`CVH-BreakGlass-01`

The account was created specifically for emergency access purposes within the lab environment.

## Conditional Access Exclusion

The break-glass account was excluded from the Conditional Access policies used during testing.

This helped reduce the risk of accidentally locking out administrative access while testing access-control policies.

---

# 🔑 CA-501 — MFA Enforcement

## 🎯 Objective

Create and test a Conditional Access policy requiring multifactor authentication for a selected CVH test user.

### Test User

`Jordan Crosby`

## ⚙️ Policy Configuration

**Policy Name:** `CA-501`

**Included User:** `Jordan Crosby`

**Excluded User:** `CVH-BreakGlass-01`

**Access Control:** Grant access

**Requirement:** Multifactor authentication

**Initial Policy Mode:** Report-only

Report-only mode was used to evaluate the expected behavior of the policy before enforcement.

## 🧪 Testing

The test was performed using the `Jordan Crosby` account.

The sign-in process was reviewed to determine whether MFA was triggered and whether the Conditional Access policy was evaluated.

Microsoft Entra sign-in logs were reviewed after the authentication attempt.

## 📊 Sign-In Log Analysis

The sign-in logs were reviewed for:

- User
- Application
- Resource
- Sign-in status
- Authentication details
- Conditional Access result
- Timestamp

The Conditional Access section was used to determine whether the MFA policy was evaluated during the sign-in.

## ✅ Result

The MFA Conditional Access scenario was successfully configured and tested.

- MFA policy created
- Jordan Crosby targeted
- Break-glass account excluded
- Report-only testing completed
- Sign-in activity reviewed
- MFA requirement validated
- Policy enforcement tested

**Status: ✅ Completed**

---

# 🚫 CA-502 — Block Azure Portal

## 🎯 Objective

Create and test a Conditional Access policy that blocks a specific test user from accessing an Azure resource.

The purpose of this scenario was to demonstrate a direct Conditional Access access-denial workflow.

### Test User

`Danielle Carter`

## ⚙️ Policy Configuration

**Policy Name:** `CA-502-Block Azure Portal`

**Included User:** `Danielle Carter`

**Excluded User:** `CVH-BreakGlass-01`

**Target Resource:** Azure Resource Manager

**Access Control:** Block access

**Initial Policy Mode:** Report-only

**Final Policy State:** On

## 🧪 Testing

The test was performed using the `Danielle Carter` account.

A fresh browser session was used to sign in and access the Azure Portal.

The purpose of the test was to determine whether Conditional Access would prevent Danielle from accessing the protected Azure resource.

## 📊 Sign-In Log Analysis

After the access attempt, Microsoft Entra sign-in logs were reviewed.

The relevant sign-in event was identified using:

- User
- Application
- Resource
- Status
- Timestamp
- Conditional Access results

The sign-in event showed Azure Portal activity associated with the test.

The Conditional Access results showed:

`CA-502-Block Azure Portal`

The policy was evaluated and the access attempt was blocked.

## 🚫 Result

The Azure Portal access-block scenario was successfully validated.

- Policy created
- Danielle Carter targeted
- Break-glass account excluded
- Azure Resource Manager targeted
- Block access configured
- Report-only testing completed
- Policy enabled
- Azure Portal access blocked
- Sign-in logs reviewed
- Conditional Access failure confirmed

**Status: ✅ Completed**

---

# 📍 Location-Based Conditional Access

## 🎯 Objective

Practice configuring Conditional Access using network and location-based conditions.

The goal was to understand how a user's network location can be used as a Conditional Access signal.

## ⚙️ Configuration

A named location was created within Microsoft Entra Conditional Access.

A location-based Conditional Access policy was configured to evaluate the user's network/location.

The policy configuration included the appropriate location condition.

## 🧪 Testing

The location-based policy was successfully configured.

However, the policy was not live validated because the lab environment did not provide a reliable external VPN or alternate-location testing setup.

Rather than claim a successful access block without evidence, the scenario is documented as a configuration exercise.

## ⚠️ Result

### Completed

- Named location created
- Location condition configured
- Conditional Access policy created
- Policy configuration reviewed

### Not Completed

- External location/VPN validation
- Confirmed live access block from a different geographic location

**Status: 🟡 Configured — Not Live Validated**

---

# 🔎 Conditional Access Testing Approach

The Conditional Access policies were tested using a controlled workflow:

1. Create policy
2. Assign test user
3. Exclude break-glass account
4. Configure target resource
5. Configure access control
6. Use Report-only mode
7. Review sign-in logs
8. Enable policy
9. Perform live test
10. Review sign-in logs again

This approach helped reduce the risk of accidentally applying an incorrect policy to an administrative account.

The **What If** tool was also reviewed as part of the Conditional Access testing process.

---

# 📊 Sign-In Log Analysis

Microsoft Entra sign-in logs were used throughout Phase 5 to determine whether Conditional Access policies were affecting authentication attempts.

The main information reviewed included:

- User
- Application
- Resource
- Sign-in status
- IP address
- Location
- Conditional Access result
- Authentication details
- Timestamp

The **Conditional Access** tab was particularly useful for determining which policies were evaluated during a specific sign-in event.

---

# 🛡️ Security Considerations

Conditional Access policies can significantly affect user access.

A poorly configured block policy can potentially prevent administrators from accessing the environment.

For this reason, the emergency access account was excluded from the Conditional Access policies used during testing.

Report-only mode was also used before enforcement to help identify unintended policy matches before applying access restrictions.

---

# 🧠 Lessons Learned

This phase provided hands-on experience with:

- Creating Conditional Access policies
- Assigning policies to specific users
- Excluding emergency access accounts
- Requiring MFA
- Blocking access to protected resources
- Using Report-only mode
- Enabling Conditional Access enforcement
- Testing access restrictions
- Reviewing Microsoft Entra sign-in logs
- Understanding Conditional Access results
- Configuring location-based access controls
- Troubleshooting Conditional Access behavior

---

# 📸 Evidence Collected

Screenshots were captured during the lab to document the configuration and testing process.

## 🚨 Break-Glass Account

- `CVH-BreakGlass-01`
- Conditional Access exclusions

## 🔑 CA-501 — MFA Enforcement

- MFA policy configuration
- Jordan Crosby assignment
- Break-glass exclusion
- Report-only configuration
- MFA testing
- Sign-in log results

## 🚫 CA-502 — Azure Portal Block

- Azure Portal block policy
- Danielle Carter assignment
- Azure Resource Manager target
- Block access control
- Policy enabled
- Blocked sign-in
- Conditional Access result
- Sign-in log evidence

## 📍 Location-Based Policy

- Named location configuration
- Location-based Conditional Access configuration

---

# 📌 Final Phase 5 Summary

Phase 5 demonstrated practical Microsoft Entra Conditional Access implementation.

Two scenarios were successfully completed and validated.

## 🔑 CA-501 — MFA Enforcement

**Status: ✅ Completed**

## 🚫 CA-502 — Block Azure Portal

**Status: ✅ Completed**

## 📍 Location-Based Access

The location-based Conditional Access policy was configured but not live validated.

**Status: 🟡 Configured — Not Live Validated**

---

# 🏁 Phase 5 Outcome

| Scenario | Status |
|---|---|
| 🔑 CA-501 — MFA Enforcement | ✅ Completed |
| 🚫 CA-502 — Block Azure Portal | ✅ Completed |
| 📍 Location-Based Access | 🟡 Configured — Not Live Validated |

### Validation Summary

**Validated Scenarios:** 2

**Additional Configuration Exercise:** 1

**Phase 5 Status:** ✅ Complete
