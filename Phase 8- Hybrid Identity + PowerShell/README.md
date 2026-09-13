# 🏥 Cedar Valley Health — Hybrid Identity Lab

> A hands-on Microsoft identity lab demonstrating **hybrid identity synchronization** between on-premises **Active Directory** and **Microsoft Entra ID**.

---

## 📌 Project Overview

Cedar Valley Health (CVH) is a fictional healthcare organization using **Microsoft Entra ID** as its primary cloud identity platform while maintaining a small on-premises Active Directory environment for legacy requirements.

This project demonstrates the implementation and validation of a hybrid identity environment using:

- 🔄 **Microsoft Entra Connect**
- 🔐 **Password Hash Synchronization (PHS)**
- 🏢 **Active Directory Domain Services**
- ⚡ **PowerShell**

---

## 🛠️ Technologies

| Technology | Purpose |
|---|---|
| 🖥️ **Windows Server 2022** | Server operating system |
| 🏢 **Active Directory Domain Services** | On-premises identity management |
| ☁️ **Microsoft Entra ID** | Cloud identity platform |
| 🔄 **Microsoft Entra Connect** | Identity synchronization |
| 🔐 **Password Hash Synchronization** | Authentication synchronization |
| ⚡ **PowerShell** | Administration and validation |

---

## 🎯 Key Objectives

- 🏗️ Build a small Active Directory environment
- 🔄 Configure Microsoft Entra Connect
- 📁 Configure OU-based synchronization
- 👥 Synchronize selected users to Microsoft Entra ID
- 🔎 Validate identity synchronization
- 🛠️ Troubleshoot synchronization and connectivity issues

---

## ⚡ PowerShell Learning

PowerShell was used throughout this lab for **administration, validation, and testing**.

I am still developing my PowerShell skills and consider myself a **beginner**. This lab gave me practical experience running scripts, observing their behavior, and understanding how PowerShell can interact with Active Directory and identity administration tasks.

This was especially valuable for understanding how scripting and automation are commonly used in **enterprise IT environments**.

> 💡 **Learning Note:** This project helped me move beyond simply reading about PowerShell and gain hands-on experience seeing how scripts execute and affect a lab environment.

---

## 🏗️ Hybrid Identity Flow

```text
┌─────────────────────────────┐
│     Active Directory        │
│         CVH.local           │
└──────────────┬──────────────┘
               │
               ▼
┌─────────────────────────────┐
│   Microsoft Entra Connect   │
│                             │
│ Password Hash Synchronization│
└──────────────┬──────────────┘
               │
               ▼
┌─────────────────────────────┐
│      Microsoft Entra ID     │
│     Cloud Identity Platform │
└─────────────────────────────┘
```

---

# Active Directory to Microsoft Entra ID Synchronization Lab

## Overview
This lab successfully synchronized three test users from Active Directory to Microsoft Entra ID using Microsoft Entra Connect.

## ✅ Synchronization Results

| Active Directory | Microsoft Entra ID | Result |
|---|---|---|
| James Wilson | James Wilson | ✅ Synchronized |
| Ashley Brooks | Ashley Brooks | ✅ Synchronized |
| Robert Davis | Robert Davis | ✅ Synchronized |

## 🔍 Validation

| Validation | Status |
|---|---|
| Microsoft Entra Connect configured | ✅ |
| Password Hash Synchronization enabled | ✅ |
| OU filtering configured | ✅ |
| Test users synchronized | ✅ |
| Synchronization validated | ✅ |

The project also included troubleshooting an initial Microsoft Entra Cloud Sync implementation before successfully transitioning to Microsoft Entra Connect.

## 👥 Test Users

| User | Department | Role |
|---|---|---|
| James Wilson | Finance | Finance Specialist |
| Ashley Brooks | Clinical Operations | Clinical Coordinator |
| Robert Davis | IT | Support Technician |

## 🧭 Troubleshooting Approach

The initial Cloud Sync implementation experienced connectivity issues. Troubleshooting followed a layered approach:

```text
Active Directory
       │
       ▼
DNS
       │
       ▼
Network Connectivity
       │
       ▼
Synchronization Agent
       │
       ▼
Synchronization Configuration
       │
       ▼
Microsoft Entra ID
```
---

## Phase 8: Cloud Sync Deployment and Troubleshooting

The Microsoft Entra provisioning agent and on-premises Active Directory environment were successfully configured, including gMSA authentication and directory connectivity.

Testing identified an external TCP 443 connectivity failure to the required Azure Service Bus endpoint. Because the restriction existed beyond the Windows VM and modification of the household network was not permitted, synchronization could not reach steady state.

Given this environmental limitation, Microsoft Entra Connect was used to complete the synchronization objective instead. While Cloud Sync could not be finalized, the troubleshooting processfrom DNS and network validation through agent and configuration review still provided valuable hands-on experience diagnosing hybrid identity connectivity issues.

The project ultimately transitioned to Microsoft Entra Connect, which successfully completed the synchronization requirements.

---
## 📸 Evidence & Documentation

This phase is documentation and evidence focused and does not include a video walkthrough.

The implementation and troubleshooting process is documented through screenshots and supporting documentation maintained in the project repository.

Evidence includes:

* Active Directory configuration
* Organizational Unit structure
* Test user creation
* Microsoft Entra provisioning configuration
* Microsoft Entra Connect configuration
* Password Hash Synchronization configuration
* OU filtering
* Synchronization results
* Microsoft Entra user validation
* PowerShell administration and validation
* Cloud Sync connectivity troubleshooting
* DNS and network troubleshooting
* Final successful synchronization using Microsoft Entra Connect

The screenshots provide visual evidence of the configuration, troubleshooting process, and final synchronization results.


