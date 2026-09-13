# Phase 8 — Security Identity Investigation Capstone


## Overview

This phase focused on investigating a suspected identity compromise using Microsoft Entra ID.

The scenario involved an employee reporting an unexpected Microsoft Authenticator prompt. The investigation used normal sign-in activity as a baseline and compared it against a controlled sign-in generated from a different network.

The goal was not to create a fake breach, but to practice how an IAM analyst would investigate unusual authentication activity and make an evidence-based determination.

---

## Video

**Video walkthrough.**

https://www.loom.com/share/88906966a36a46fc94f228ee1a57b0ae

The walkthrough will demonstrate the investigation process, including the sign-in investigation, authentication details, Conditional Access evaluation, audit-log review, and final determination.

---

## Scenario

* **User:** Rachel Thompson
* **Role:** Financial Analyst
* **Ticket:** 801 — Suspected Account Compromise

Rachel reported receiving an unexpected Microsoft Authenticator prompt that she did not initiate.

The investigation focused on determining whether Rachel's account showed suspicious authentication activity and whether the available evidence supported a potential compromise.

---

## Investigation Approach

The investigation followed this general process:

**Establish Baseline → Investigate Sign-In → Review Authentication → Review Conditional Access → Review Audit Logs → Correlate Evidence → Determine Risk → Document Response**

The investigation included:

* Reviewing Rachel's normal sign-in behavior
* Comparing IP addresses and reported locations
* Comparing browser and operating system information
* Reviewing authentication details
* Reviewing Conditional Access results
* Reviewing audit logs
* Building a basic event timeline
* Determining whether compromise could be established from the evidence
* Documenting appropriate IAM remediation

---

## Key Finding

A controlled VPN test generated a successful sign-in from:

* **IP:** 159.26.99.222
* **Reported location:** El Segundo, California
* **Browser:** Firefox 155.0
* **Operating system:** Windows 10

Rachel's normal activity showed a different browser and network pattern.

The Conditional Access investigation also showed that the sign-in was evaluated successfully in Report-only mode.

Authentication details showed that the MFA requirement was satisfied through an existing token claim rather than demonstrating a new MFA approval during the specific sign-in.

---

## Investigation Determination

**No confirmed account compromise.**

The sign-in contained indicators that would warrant investigation in a real environment, particularly the different IP address, reported location, and browser.

However, the sign-in was intentionally generated using a VPN as part of this controlled lab. No related account or authentication-method change was identified around the event that would establish an actual compromise.

Therefore, the evidence was documented as a **controlled suspicious-looking authentication event rather than a confirmed security incident**.

---

## IAM Response

Because this was a controlled lab event, no destructive remediation was performed.

In a real incident where the user confirmed that the activity was unauthorized, potential IAM/security response actions could include:

* Revoke active sessions/tokens
* Require a password reset
* Review and validate MFA methods
* Require MFA re-registration when appropriate
* Temporarily restrict or disable the account when warranted
* Review additional sign-in and audit activity
* Escalate to security/incident response
* Verify the account after remediation

The appropriate response would depend on the evidence and the organization's incident-response procedures.

---

## Skills Demonstrated

* Microsoft Entra ID
* Sign-in log investigation
* Authentication troubleshooting
* MFA investigation
* Conditional Access
* Report-only policy testing
* Audit log review
* IP/location analysis
* Identity investigation
* Evidence correlation
* Incident documentation
* IAM remediation concepts

---

## Key Takeaways

This investigation helped reinforce that unusual authentication activity should be investigated using multiple pieces of evidence.

A different location or IP address can be a useful indicator, but it does not automatically mean an account has been compromised. VPNs, proxies, mobile networks, and other factors can affect the location reported by identity systems.

The most important part of the investigation was comparing the unusual activity against the user's normal baseline and documenting a conclusion supported by the available evidence.

---

## Evidence

Screenshots and supporting evidence from the investigation are included with this project.

---

## Disclaimer

This project is a controlled educational lab using test identities and intentionally generated activity. It does not represent a real security incident or actual unauthorized access.

