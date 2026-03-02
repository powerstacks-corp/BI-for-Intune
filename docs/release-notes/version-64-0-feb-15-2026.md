---
title: "Version 64.0 Feb. 15, 2026"
---
# What's New in BI for Intune v64
**Release Date**: February 15, 2026
**App Source Version**: 1056

BI for Intune v64 introduces expanded Microsoft Defender for Endpoint and Microsoft Entra ID risk visibility.

This release adds the new User Risk object and Risky Users page, providing insight into user risk posture and sign-in risk state. It also enhances Windows Protection reporting with additional onboarding and sensor status fields.

Improved sync reliability and updated policy reporting ensure more accurate visibility across devices and users.

**Important Notes:**

- [**Action Required**] This version requires an additional Microsoft Graph permission to be added to the app registration in **Microsoft Entra ID**. Please add **Read.All**. Without this permission, the **Risky Users** page and related sync processes will not populate properly. Update your installation documentation to include this permission.
- Several customers have recently reported upgrade failures resulting in the loss of their custom reports. Please do not forget to [backup before you upgrade](backup-custom-reports.md)!


# Version 64.0 Release Details


### Product Enhancements

- Updated the **Configuration Policy** data to ensure all policy types are properly displayed, including Elevation settings policy and Local user group membership.
- Updated the **Windows Protection** data source for improved reliability and completeness.
- Added new fields to the **Device Info** page: **OS Quality Update Version**, **OS Quality Update Release Date**, and **OS Quality Update Type** to improve visibility into Windows servicing status.
- Updated the **Windows Protection** page filters by removing **Filter by ATP Status** and adding **Filter by MDE Onboarding Status**.
- Added new fields to the **User** object: Last Interactive Sign-In, Last Interactive Sign-In (Days), Last Non-Interactive Sign-In, Last Non-Interactive Sign-In (Days), Last Successful Sign-In, Last Successful Sign-In (Days).
- Updated the **Group** object to include **Distribution** as a supported **Group Type**.
- Added **Risk State** and **Risk Level** to the **Sign-Ins** page main table and added related filters to improve visibility into sign-in risk posture.

### New Features

- Added new object **User Risk** to provide visibility into user risk posture and remediation status.
- Added new page **Risky Users** to support reporting on Microsoft Entra ID risky users.

### Semantic Model Changes

- Removed object **Windows Defender ATP** and associated fields: ATP Compliant, ATP Conflict, ATP Error, ATP Non Compliant, ATP Not Applicable, ATP Not Assigned, ATP Remediated, ATP State, ATP Status, ATP Unknown.
- Added new fields to the **Windows Protection** object: Critical Failure, MDE Can Be Onboarded, MDE Failed, MDE Insufficient Info, MDE Not Onboarded, MDE Onboarded, MDE Onboarding Status, MDE Sensor State, MDE Unsupported, Pending Full Scan, Pending Manual Steps, Pending Offline Scan, Pending Reboot, Tamper Protection Enabled.
- Added new object **User Risk** with fields: Risk Lasted Updated, Risk Lasted Updated (Days), User Risk Count, User Risk Level, User Risk Level Hidden, User Risk Level High, User Risk Level Low, User Risk Level Medium, User Risk Level None, User Risk Level Unknown Future Value, User Risk State, User Risk State At Risk, User Risk State Confirmed Compromised, User Risk State Confirmed Safe, User Risk State Dismissed, User Risk State None, User Risk State Remediated, User Risk State Unknown Future Value.
- Added new fields to the **User Sign-Ins** object: Sign-In Risk Level, Sign-In Risk Level Hidden, Sign-In Risk Level High, Sign-In Risk Level Low, Sign-In Risk Level Medium, Sign-In Risk Level None, Sign-In Risk Level Unknown Future Value, Sign-In Risk State, Sign-In Risk State At Risk, Sign-In Risk State Confirmed Compromised, Sign-In Risk State Confirmed Safe, Sign-In Risk State Dismissed, Sign-In Risk State None, Sign-In Risk State Remediated, Sign-In Risk State Unknown Future State.

### Bug Fixes

- Resolved an issue where some **Configuration Policy** types were not appearing in reports.

### Important Notes

- [**Action Required**] This version requires an additional Microsoft Graph permission to be added to the app registration in **Microsoft Entra ID**. Please add **Read.All**. Without this permission, the **Risky Users** page and related sync processes will not populate properly. Update your installation documentation to include this permission.
- Removed the **Windows Defender ATP** Custom reports referencing ATP fields must be updated to use **Windows Protection** fields.
- Microsoft Graph API instability (HTTP 503/504) continues to affect some tenants intermittently. The new **"AzureAD Application Assignment Enable"** parameter provides a temporary workaround. Please contact us if you have this issue. We need more support cases opened with Microsoft so they will prioritize resolving this!
- Always [backup your custom reports](backup-custom-reports.md) before upgrading!
