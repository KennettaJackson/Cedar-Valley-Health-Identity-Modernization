# Phase 10 — Data Loss Prevention (DLP)

## Overview

This phase focuses on configuring Microsoft Purview Data Loss Prevention (DLP) to identify sensitive information in Microsoft 365.

Cedar Valley Health is a fictional healthcare organization used for this portfolio project. The scenario involves identifying documents containing sensitive information, such as U.S. Social Security Numbers (SSNs).

The goal is to configure a DLP policy, test its detection capabilities using synthetic data, and review the results before enabling protective enforcement actions.

## Scenario

**Organization:** Cedar Valley Health  
**Platform:** Microsoft 365 Business Premium  
**Technology:** Microsoft Purview Data Loss Prevention  
**Project:** Identity Modernization  
**Status:** In Progress

Cedar Valley Health wants to reduce the risk of sensitive information being exposed through documents stored in Microsoft 365.

As the Microsoft 365 security administrator, I configured a DLP policy in simulation mode to evaluate whether content containing SSNs can be identified before enforcement is enabled.

## Policy Configuration

**Policy Name:** CVH – Protect Patient Information

**Rule Name:** CVH – Detect Sensitive Patient Data

**Sensitive Information Type:** U.S. Social Security Number (SSN)

**Confidence Level:** Medium

**Instance Count:** 1 to Any

**Rule Action:** Send alerts to administrator

**Policy Mode:** Simulation

**Validation Status:** Pending

## Implementation Approach

The implementation followed this general process:

**Create DLP Policy → Configure Detection Rule → Configure Administrator Alerts → Enable Simulation Mode → Prepare Test Content → Verify Synchronization → Review Simulation Results**

The implementation included:

- Creating a Microsoft Purview DLP policy using a healthcare-related template
- Customizing the policy's advanced rules
- Configuring detection for U.S. Social Security Numbers
- Selecting a medium confidence level
- Configuring the rule to detect one or more instances
- Configuring administrator alerts for qualifying rule matches
- Selecting simulation mode to evaluate policy behavior before enforcement
- Preparing a fictional test document containing synthetic data
- Monitoring policy synchronization and simulation status

 ## Test Document

A fictional test document containing synthetic data was created and uploaded to OneDrive to support DLP policy validation.

The document is intended to test whether Microsoft Purview identifies content containing the configured U.S. Social Security Number (SSN) sensitive information type.

**Test Status:** Document uploaded; DLP detection not yet verified.

The upload confirms that the test content was prepared and placed in OneDrive. It does not, by itself, confirm that the DLP policy detected a match.

- **Synthetic test document prepared and uploaded to OneDrive:** Completed
- **DLP detection of test document:** Pending
- **Policy synchronization:** Awaiting confirmation
- **Simulation results review:** Pending

## Key Configuration

The DLP policy was configured to identify content containing the U.S. Social Security Number sensitive information type.

Administrator alerts were configured to support monitoring when qualifying rule matches occur.

The policy remains in simulation mode while detection behavior and policy synchronization are validated.

**Final detection results have not yet been verified.**

## Testing Results

The initial policy configuration steps have been completed.

- **DLP policy creation:** Completed
- **SSN detection rule:** Configured
- **Administrator alert action:** Configured
- **Policy synchronization:** Awaiting confirmation
- **Synthetic test document detection:** Pending
- **Simulation results review:** Pending

The lab remains in progress until policy synchronization is confirmed, the synthetic test document is evaluated, and the simulation results are reviewed.

No successful detection is being claimed at this stage.

## Security Considerations

- **Use synthetic test data only.** Do not include real patient records, SSNs, or other personal identifiers.
- **Keep the policy in simulation mode** while testing is completed.
- **Verify policy scope.** Confirm that the intended Microsoft 365 locations are covered.
- **Confirm synchronization** before interpreting test results.
- **Validate detection before enforcement.** Review simulation results before enabling restrictive actions.
- **Protect portfolio evidence.** Do not upload real patient information or personal identifiers to GitHub.
- **Avoid unsupported compliance claims.** This lab does not independently establish HIPAA or other regulatory compliance.

## Evidence

Screenshots and supporting evidence will be added after the corresponding steps have been verified.

**Planned evidence includes:**

- [ ] DLP policy configuration
- [ ] Advanced rule conditions
- [ ] Policy synchronization status
- [ ] Simulation results
- [ ] Detection evidence, if a match occurs
- [ ] Troubleshooting steps and findings, if applicable

Evidence will reflect actual results observed in Microsoft Purview. Pending tests will not be presented as completed.

## Lessons Learned

This lab demonstrates the difference between configuring a DLP policy, synchronizing its settings, evaluating content in simulation mode, and enabling protective enforcement actions.

It also reinforces the importance of validating policy scope, confirming synchronization, and reviewing simulation results before relying on a DLP policy to identify sensitive information.

The final findings will document the observed detection behavior, any troubleshooting performed, and recommendations for moving toward enforcement.

## Future Enhancements

- [ ] Complete DLP simulation testing and document the results
- [ ] Explore Microsoft Purview sensitivity labels
- [ ] Test label-based DLP conditions where supported
- [ ] Investigate relevant Microsoft 365 audit events
- [ ] Document the relationship between data classification, DLP, and information protection
- [ ] Evaluate protective enforcement actions after successful validation

## Technologies

- Microsoft 365 Business Premium
- Microsoft Purview
- Data Loss Prevention (DLP)
- Sensitive Information Types
- GitHub

## Author

**Kennetta Jackson**

Aspiring Identity and Access Management (IAM) Engineer interested in cloud security, identity governance, data protection, and security investigations.

## Disclaimer

This project is an educational lab using a fictional healthcare organization and synthetic test data. It does not involve real patient information or represent a production DLP deployment.

Implementation findings will be updated as policy synchronization, detection testing, and simulation review are completed.
