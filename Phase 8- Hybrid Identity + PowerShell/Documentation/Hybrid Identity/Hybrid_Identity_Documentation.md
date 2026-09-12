# 🏥 Cedar Valley Health — Hybrid Identity Modernization Lab

> **Hands-on Microsoft identity lab focused on Active Directory, Microsoft Entra ID, Microsoft Entra Connect, and hybrid identity synchronization.**

---
# 📌 Project Overview

Cedar Valley Health (CVH) is a fictional healthcare organization that has adopted Microsoft Entra ID as its primary cloud identity platform while retaining a small on-premises Active Directory environment for selected legacy and administrative requirements.

This lab demonstrates how CVH can maintain a controlled hybrid identity environment by synchronizing selected Active Directory users to Microsoft Entra ID.

The project uses Microsoft Entra Connect with Password Hash Synchronization (PHS) and OU-based synchronization filtering.

The lab is designed for educational and portfolio purposes and does not represent a production healthcare identity deployment.

---
# 🎯 Objectives

#### The lab demonstrates practical experience with:

- Windows Server 2022
- Active Directory Domain Services
- Active Directory Organizational Units
- Active Directory users and security groups
- Microsoft Entra ID
- Microsoft Entra Connect
- Password Hash Synchronization
- OU-based synchronization filtering
- PowerShell administration
- Identity synchronization
- Network troubleshooting
- Synchronization troubleshooting
- Identity validation
- Technical documentation

---

# 🖥️ Lab Environment

- Component	Configuration
- Server	CVH-DC01
- Operating System	Windows Server 2022
- Active Directory Domain	CVH.local
- Directory Service	Active Directory Domain Services
- DNS	Windows DNS
- Cloud Identity	Microsoft Entra ID
- Synchronization	Microsoft Entra Connect
- Authentication	Password Hash Synchronization
- Entra Tenant	kjack628outlook.onmicrosoft.com

---

# 📁 Active Directory Structure

```text
CVH.local
│
└── CVH
    │
    ├── Users
    │   ├── James Wilson
    │   ├── Ashley Brooks
    │   └── Robert Davis
    │
    └── Groups
        └── CVH-Entra-Sync
```



####  User OU:
- OU=Users,OU=CVH,DC=CVH,DC=local

#### Synchronization Group:
- CN=CVH-Entra-Sync,OU=Groups,OU=CVH,DC=CVH,DC=local

---

# 👥 Phase 8 Test Users


| User | Department | Role |
|---|---|---|
| James Wilson | Finance | Finance Specialist |
| Ashley Brooks | Clinical Operations | Clinical Coordinator |
| Robert Davis | IT | Support Technician |


These users were created in Active Directory and subsequently synchronized to Microsoft Entra ID.

---

# 🔄 Hybrid Identity Architecture
                 Cedar Valley Health
                         │
                         ▼
                Microsoft Entra ID
              Primary Identity Platform
                         ▲
                         │
                  Synchronization
                         │
                         ▼
              Microsoft Entra Connect
                         │
                  Password Hash Sync
                         │
                         ▼
                     CVH-DC01
                         │
                  CVH.local AD DS
                         │
          ┌──────────────┼──────────────┐
          │              │              │
          ▼              ▼              ▼
       James          Ashley         Robert
       Wilson         Brooks         Davis
       Finance     Clinical Ops        IT

---

# 🔐 Authentication Model

The lab uses Password Hash Synchronization (PHS).

PHS allows password hash information from Active Directory to be synchronized to Microsoft Entra ID so that users can authenticate to cloud services using their existing credentials.

The lab does not use:

- AD FS
- Federation
- Pass-through Authentication

The architecture was intentionally kept simple to demonstrate a practical hybrid identity configuration.

---

# ⚙️ Synchronization Configuration

#### The final environment uses:

- Microsoft Entra Connect
- Active Directory synchronization
- Password Hash Synchronization
- OU filtering
- Automatic synchronization
- Initial synchronization
- Delta synchronization

#### The synchronization server is:

- CVH-DC01


#### The Active Directory forest is:

- CVH.local

---

# 🎯 Synchronization Scope

OU-based filtering was used to limit synchronization to the intended user population.

```text
CVH.local
│
└── CVH
    │
    └── Users
        ├── James Wilson
        ├── Ashley Brooks
        └── Robert Davis
```

This prevents the entire Active Directory environment from automatically being synchronized to Microsoft Entra ID.

Synchronization scope is an important security and administrative consideration when connecting an on-premises directory to a cloud identity platform.

---

# 🧰 PowerShell Validation

#### Verify a user:

- Get-ADUser jwilson

#### Verify the user's location:

- Get-ADUser jwilson |
Select-Object Name, DistinguishedName

#### Verify identity attributes:

- Get-ADUser jwilson -Properties mail,UserPrincipalName |
Select-Object Name,UserPrincipalName,mail

#### Verify the synchronization group:

- Get-ADGroup "CVH-Entra-Sync" |
Select-Object Name,DistinguishedName

#### Verify the synchronization service:

- Get-Service ADSync

#### Check the synchronization scheduler:

- Get-ADSyncScheduler

#### Check configured connectors:

- Get-ADSyncConnector |
Select-Object Name,Type

#### Start an initial synchronization:

- Start-ADSyncSyncCycle -PolicyType Initial

---

# 🚀 Synchronization Validation

#### The synchronization service was verified as running:

- Status: Running
- Name: ADSync 
- DisplayName: Microsoft Azure AD Sync
 

#### The initial synchronization was manually started:

- Start-ADSyncSyncCycle -PolicyType Initial


#### Result: Success


#### After the initial synchronization completed, the scheduler returned to normal delta synchronization.

-Get-ADSyncScheduler |
Select-Object SyncCycleInProgress,
              NextSyncCyclePolicyType,
              NextSyncCycleStartTimeInUTC


#### Expected final state:

- SyncCycleInProgress       : False
NextSyncCyclePolicyType   : Delta

---

# 🔌 Entra Connect Connectors

#### The configured connectors were inspected using:

-Get-ADSyncConnector |
Select-Object Name,Type


#### The environment contained:

- kjack628outlook.onmicrosoft.com - AAD
- CVH.local                         - AD


This confirms the connection between the on-premises Active Directory forest and Microsoft Entra ID.

---

# 🛠️ Troubleshooting

The lab initially attempted to use Microsoft Entra Cloud Sync.

The provisioning agent successfully installed and registered, but the Cloud Sync agent encountered connectivity issues reaching required Microsoft service infrastructure.

Network testing indicated that the issue was not simply an Active Directory configuration problem.

The lab therefore transitioned to Microsoft Entra Connect.

This provided an opportunity to practice a structured troubleshooting methodology:

# 🧭 Troubleshooting Approach

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


The troubleshooting process emphasized identifying which layer was failing instead of making configuration changes at random.

---

# ✅ Final Validation

| Active Directory | Microsoft Entra ID | Result |
|---|---|---|
| James Wilson | James Wilson | ✅ Synchronized |
| Ashley Brooks | Ashley Brooks | ✅ Synchronized |
| Robert Davis | Robert Davis | ✅ Synchronized |


## The final environment confirmed:

- Synchronization service running
- Initial synchronization successful
- Normal delta synchronization restored
- Three test users synchronized
- Users visible in Microsoft Entra ID
- OU-based synchronization scope configured

---

# 📚 What This Project Demonstrates

#### This lab demonstrates hands-on experience with:

### Identity

- Active Directory
- Microsoft Entra ID
- Hybrid identity
- User lifecycle management
- Identity synchronization

### Microsoft Infrastructure

- Windows Server 2022
- AD DS
-  DNS
- Microsoft Entra Connect

### Administration

- PowerShell
- Organizational Units
- Security groups
- Synchronization scheduling
- Connector inspection

### Troubleshooting

- Cloud Sync troubleshooting
- Network connectivity analysis
- Synchronization troubleshooting
- Layered problem isolation

---

# 💡 Key Takeaways
Hybrid identity requires planning

Not every Active Directory object needs to be synchronized to Microsoft Entra ID.

Defining an appropriate synchronization scope helps reduce unnecessary synchronization and provides greater administrative control.

# Troubleshooting should be methodical

#### When synchronization fails, each layer should be evaluated independently:

AD → DNS → Network → Agent → Configuration → Entra ID

PowerShell is valuable for identity administration

# PowerShell provides a fast and repeatable method for inspecting:

- Users
- Attributes
- Groups
- Services
- Connectors
- Synchronization status

# Failed approaches are still valuable

The initial Cloud Sync implementation did not become the final solution. However, troubleshooting the failure helped distinguish an external connectivity problem from an Active Directory configuration problem.

---

# 🔮 Future Lab Expansion

Future iterations could include:

- Adding additional hybrid users
- Testing user attribute changes
- Testing user disablement
- Testing user deletion
- Testing employee mover scenarios
- Testing employee leaver scenarios
- Measuring synchronization delays
- Simulating synchronization failures
- Automating identity administration with PowerShell
- Expanding synchronization scope
- Testing cloud-to-on-premises identity dependencies

---

# ⚠️ Lab Disclaimer

Cedar Valley Health is a fictional organization created for educational and portfolio purposes.

This project is a controlled laboratory environment and does not represent a production healthcare identity deployment.

No real patient information or protected health information (PHI) is used.

---

# 👤 Author

Kennetta Jackson

Microsoft Identity & Hybrid Identity Lab

Focus: Active Directory • Microsoft Entra ID • Microsoft Entra Connect • PowerShell • Hybrid Identity

