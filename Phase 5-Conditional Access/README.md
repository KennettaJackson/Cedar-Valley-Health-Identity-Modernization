# 🔐 Phase 5 — Conditional Access

## 📋 Overview

In Phase 5, I worked with Microsoft Entra Conditional Access to control access based on authentication and application access requirements.

The goal was to understand how Conditional Access evaluates sign-in signals and enforces access policies.

---

## 🧪 Lab Environment

- Microsoft Entra ID
- Microsoft Entra Conditional Access
- Test user: `Danielle Carter`
- Emergency access account: `CVH-BreakGlass-01`

---

## 🚨 Break-Glass Account

Created a dedicated emergency access account:

`CVH-BreakGlass-01`

The account was excluded from Conditional Access policies to reduce the risk of administrative lockout.

---

## 🔑 CA-501 — MFA Enforcement

### 🎯 Objective

Require MFA for the selected CVH test user.

### ⚙️ Configuration

- Created a Conditional Access policy
- Targeted `Jordan Crosby`
- Excluded the break-glass account
- Configured MFA as the access control
- Initially tested the policy using **Report-only**
- Reviewed the resulting sign-in activity
- Enabled the policy after testing

### ✅ Result

Successfully triggered MFA for Jordan Crosby and confirmed the Conditional Access policy through the Microsoft Entra sign-in logs.

---

## 🚫 CA-502 — Block Azure Portal

### 🎯 Objective

Test Conditional Access by blocking access to an Azure resource for a specific test user.

### ⚙️ Configuration

- Created `CA-502-Block Azure Portal`
- Targeted `Danielle Carter`
- Excluded `CVH-BreakGlass-01`
- Targeted **Azure Resource Manager**
- Configured **Block access**
- Tested the policy in Report-only
- Enabled the policy

### 🧪 Validation

Danielle attempted to access the Azure Portal after the policy was enabled.

The sign-in was blocked.

The Microsoft Entra sign-in logs confirmed:

- Danielle Carter was the affected user
- The sign-in resulted in a failure
- Azure Portal/Azure Resource Manager was involved
- `CA-502-Block Azure Portal` was evaluated and caused the access failure

---

## 📍 Location-Based Access Policy

### 🎯 Objective

Practice configuring Conditional Access based on network/location signals.

### ⚙️ Configuration

- Created a named location
- Configured a location-based Conditional Access policy
- Reviewed the available network/location conditions
- Configured the policy for testing

### ⚠️ Result

The location-based policy was successfully configured but was not live validated because the lab environment did not provide a reliable external location/VPN testing method.

---

## 🧠 What I Learned

- How Conditional Access evaluates user and sign-in conditions
- How to require MFA through Conditional Access
- How to block access to a protected resource
- How to exclude an emergency access account
- How to use Report-only mode before enforcement
- How to analyze Conditional Access results in Entra sign-in logs
- How location-based policies can be used as an additional access control

---

## 🎥 Quick Overview

Want a quick walkthrough of the project?

https://www.loom.com/share/ce332e6ed0844e71bed24d4388aa94fa

This short video provides an overview of the Phase 5 Conditional Access work, including:

- 🔑 MFA enforcement
- 🚫 Azure Portal access blocking
- 📊 Microsoft Entra sign-in log analysis
- 📍 Location-based Conditional Access configuration
- 🛡️ Break-glass account considerations
- 🧠 Lessons learned from testing Conditional Access

---

## 📸 Evidence

Screenshots are included in this repository showing:

- Conditional Access policy configuration
- Break-glass account configuration
- MFA policy testing
- Azure Portal access block
- Entra sign-in log results
- Location-based policy configuration

---

## 🏁 Phase 5 Outcome

Phase 5 demonstrated practical Conditional Access configuration, testing, enforcement, and sign-in log analysis using a controlled CVH lab environment.

**Status: ✅ Complete**
