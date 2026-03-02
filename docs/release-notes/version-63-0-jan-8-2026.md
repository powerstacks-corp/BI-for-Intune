---
title: "Version 63.0 Jan. 8, 2026"
---
# What's New in BI for Intune v63
**Release Date**: January 8, 2026
**App Source Version**: 1055

Version 63 brings additional configuration profile type data to BI for Intune.

**Important Notes:**
Several customers have recently reported upgrade failures resulting in the loss of their custom reports. Please do not forget to [backup before you upgrade](backup-custom-reports.md)!


# Version 63.0 Release Details


### Product Enhancements

- N/A

### New Features

- Added Endpoint Security **Configuration Policy** types to the data model. Policy types include:**App and Browser Isolation**
- **App Control for Business**
- **BitLocker**
- **Microsoft Defender Antivirus**
- **Endpoint Detection and Response**
- **Windows Firewall**
- **macOS FileVault**

### Bug Fixes

- N/A

### Semantic Model Changes

- Extended the data model to include Endpoint Security **Configuration Policy** objects.

### Important Notes

- Microsoft Graph API instability (HTTP 503/504) continues to affect some tenants intermittently. The new **"AzureAD Application Assignment Enable"** parameter provides a temporary workaround. Please contact us if you have this issue. We need more support cases opened with Microsoft so they will prioritize resolving this!
- Always [backup your custom reports](backup-custom-reports.md) before upgrading!
