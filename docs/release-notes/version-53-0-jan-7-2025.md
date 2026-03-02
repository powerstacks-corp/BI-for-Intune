---
title: "Version 53.0 Jan. 7, 2025"
---
# Versions 53.0 (AppSource Versions 1047)
**BI for Intune Version 53 (January 7, 2025)**

Version 53 resolves a critical issue caused by a recent change to a Microsoft API, which disrupted the functionality of our Autopilot Deployments report page. This update restores full functionality and ensures compatibility with the latest API standards.


**Important Notes:**

Several customers have recently reported upgrade failures resulting in the loss of their custom reports. Please do not forget to [backup before you upgrade](backup-custom-reports.md)!



## Below Are the Changes in Version 53.0



- **Bug fixes:**The "**Autopilot Deployments**" page was not showing any data.This was due a change in the Microsoft API. "Order By" is no longer supported by the API.
**Semantic Model Changes:**
- **Updates to Existing Objects:**Added new fields to the "**Cloud PC Provisioning Status**" object:**notProvisioned**
- **provisioning**
- **provisioned**
- **inGracePeriod**
- **deprovisioning**
- **failed**
- **provisionedWithWarnings**
- **resizing**
- **restoring**
- **pendingProvision**
- **unknownFutureValue**
- **movingRegion**
- **resizePendingLicense**
- **modifyingSingleSignOn**
- **preparing**
Added new semantic model parameter "**AzureAD Export URL CloudPC Enable**" to enable/disable the redirection of the CloudPC Download URL. Default value is False.
- Previously this was controlled by "AzureAD Export URL Enable".
**Product Enhancements:**
- Implemented retry logic for the Export API when the download file is corrupted or empty.
**Updates to Existing Pages:**
- Updated the "**Cloud PC Provisioning Status**" page to show items with no data when “join type” or “connection” information is missing.
