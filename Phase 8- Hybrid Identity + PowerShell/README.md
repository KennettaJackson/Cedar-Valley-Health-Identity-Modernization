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


The project ultimately transitioned to Microsoft Entra Connect, which successfully completed the synchronization requirements.

## 🎥 Video Coming Soon

A short project walkthrough will be added soon, providing a quick overview of:

- 🖥️ Lab environment
- 🏢 Active Directory configuration
- 🔄 Microsoft Entra Connect setup
- 👥 User synchronization
- ☁️ Final validation in Microsoft Entra ID

🎬 *Walkthrough video coming soon.*
