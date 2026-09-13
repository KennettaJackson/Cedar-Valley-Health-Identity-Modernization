# Ticket 801 — Suspected Account Compromise

## Ticket Information

* **Ticket:** 801
* **User:** Rachel Thompson
* **Role:** Financial Analyst
* **Issue:** Suspected account compromise / unexpected Microsoft Authenticator activity
* **Environment:** Microsoft Entra ID
* **Investigation Type:** Controlled security identity investigation

---

## Reported Issue

Rachel Thompson reported receiving an unexpected Microsoft Authenticator prompt that she did not initiate.

The objective of this investigation was to determine whether Rachel's account showed authentication activity that differed from her normal sign-in pattern and whether the available evidence supported a potential account compromise.

---

## Investigation Objective

The investigation focused on:

* Establishing Rachel's normal sign-in pattern
* Reviewing successful and failed sign-in activity
* Comparing the normal sign-in pattern with the suspicious-looking activity
* Reviewing IP address and reported location
* Reviewing browser and operating system information
* Reviewing authentication details
* Reviewing Conditional Access results
* Reviewing Entra audit logs for related account changes
* Determining whether the evidence supported an actual compromise
* Identifying appropriate IAM remediation if this were a real incident

---

## Normal Sign-In Baseline

Before investigating the unusual activity, I reviewed Rachel Thompson's normal sign-in activity to establish a baseline.

The baseline showed Rachel commonly signing in using:

* Windows 10
* Chrome browser
* Her normal network/IP pattern
* Her expected authentication process

This baseline was used to compare the later sign-in activity.

---

## Controlled VPN Test

A controlled sign-in was performed using a VPN to simulate authentication from a different network.

The resulting sign-in was:

* **Status:** Successful
* **IP address:** 159.26.99.222
* **Reported location:** El Segundo, California
* **Browser:** Firefox 155.0
* **Operating system:** Windows 10
* **Conditional Access:** Report-only policy showed success

The activity differed from Rachel's normal pattern, particularly in the IP address, reported location, and browser.

Because the VPN was intentionally used as part of this lab, this event represents a **controlled simulation and not evidence of an actual attacker accessing the account**.

---

## Authentication Investigation

The authentication details were reviewed to determine whether the sign-in involved a new MFA challenge.

The sign-in showed that MFA was satisfied through an existing claim in the token.

The authentication requirement was listed as previously satisfied.

This is important because the successful sign-in does not by itself demonstrate that a new MFA prompt was approved during this specific event.

---

## Conditional Access Investigation

A Conditional Access policy was configured in Report-only mode to evaluate Rachel's sign-in when it originated from a network outside the defined normal network.

The policy evaluated the sign-in successfully.

The Report-only result provided additional investigation evidence without enforcing an access block during the controlled test.

The Conditional Access result was treated as supporting evidence rather than proof of compromise.

---

## Audit Log Investigation

Entra audit logs were reviewed for activity involving Rachel's account around the time of the unusual sign-in.

An audit event involving the **Azure MFA Strong Authentication Service** was identified earlier in the evening.

The event occurred at approximately 9:12 PM, while the controlled VPN sign-in occurred at approximately 10:09 PM.

Because the events were not directly correlated by the available evidence, the MFA service event was **not treated as the cause of the VPN sign-in**.

No related account or authentication-method change was identified around the controlled VPN sign-in that would establish an actual compromise.

---

## Findings

The investigation identified the following:

1. A successful sign-in occurred from an IP address and reported location that differed from Rachel's normal activity.
2. The browser also differed from Rachel's normal browser.
3. The operating system remained Windows 10.
4. MFA was satisfied through an existing token claim.
5. Conditional Access evaluated the activity successfully in Report-only mode.
6. No related account or authentication-method change was identified around the controlled VPN sign-in.
7. The VPN was intentionally used to generate the unusual sign-in as part of the lab.

---

## Determination

**Determination: No confirmed account compromise.**

The controlled VPN test generated authentication activity that differed from Rachel Thompson's normal sign-in pattern, including a different IP address, reported location, and browser.

However, the activity was intentionally generated as part of the investigation lab. The available evidence did not establish that an unauthorized person accessed Rachel's account.

The different location should therefore be treated as a **suspicious indicator requiring investigation**, rather than automatic proof of compromise.

---

## Remediation

### Lab Remediation

No destructive remediation was performed because the unusual sign-in was intentionally generated for this controlled investigation.

Rachel's account was not disabled, and her existing authentication configuration was not unnecessarily changed.

This prevented the lab simulation from creating an artificial account lockout or disrupting the test environment.

### Real-World IAM Response

If the same activity occurred in a real environment and Rachel confirmed that she did not perform the sign-in, IAM/security personnel would investigate and respond according to the organization's incident-response procedures.

Potential response actions could include:

* Confirming the activity with the user
* Reviewing additional sign-in history
* Reviewing authentication methods and recent changes
* Revoking active sessions/tokens if compromise is suspected
* Requiring a password reset when appropriate
* Requiring MFA re-registration if the authentication method may be compromised
* Temporarily blocking or restricting the account when warranted
* Reviewing related audit activity for additional changes
* Escalating to the appropriate security/incident-response team
* Verifying the account is secure after remediation

The specific response would depend on the evidence and organizational procedures.

---

## Verification

Because no actual compromise was confirmed, no destructive remediation was required in the lab.

The investigation was considered complete after:

* Reviewing Rachel's baseline
* Reviewing the controlled VPN sign-in
* Reviewing authentication details
* Reviewing Conditional Access results
* Reviewing audit logs
* Comparing the available evidence
* Documenting the final determination

---

## Lessons Learned

This investigation reinforced several IAM and security concepts:

* A successful sign-in is not automatically a legitimate sign-in.
* IP address and location should be investigated rather than treated as definitive proof of compromise.
* VPNs can cause sign-in activity to appear from a different location.
* Browser, operating system, IP, and authentication information can help establish a user's normal baseline.
* Authentication and authorization are separate concepts.
* Conditional Access Report-only mode can be useful for testing policies without immediately enforcing them.
* Audit logs provide evidence that can help build an investigation timeline.
* Security conclusions should be based on multiple pieces of evidence rather than a single indicator.
* Controlled testing should be clearly separated from real security incidents.

---

## Evidence

Evidence collected during the investigation includes screenshots and supporting documentation showing:

* Normal sign-in activity
* Controlled VPN sign-in
* Authentication details
* Conditional Access evaluation
* Relevant audit-log activity
* Investigation findings

---

## Investigation Status

**Status: Completed**

The investigation demonstrated a controlled workflow for reviewing unusual identity activity and determining whether available evidence supports a suspected account compromise.

