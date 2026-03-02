---
title: "Version 61.0 Oct. 28, 2025"
---
# What's New in BI for Intune v61
**Release Date**: October 27, 2025
**App Source Version**: 1053

Version 61 mainly brings improved stability and better synchronization performance to BI for Intune.

**Important Notes:**
Several customers have recently reported upgrade failures resulting in the loss of their custom reports. Please do not forget to [backup before you upgrade](backup-custom-reports.md)!


# Version 61.0 Release Details


### Product Enhancements

- Added a retry function for all API calls that use redirects to improve reliability in unstable network conditions.
- Updated the **"Device Timeline Event"** parameter — default value is now **-1 (Disabled)** instead of **7 days**, to prevent unnecessary calls for customers not using Intune Advanced Analytics.

### New Features

- N/A

### Bug Fixes

- Added a new parameter "**AzureAD Application Assignment Enable"** *(Default:**TRUE**)* to disable **"Application Assignment"** data collection in environments where the Microsoft Graph API intermittently returns 503 or 504 errors.
- Fixed issue in **"Autopilot Enrollment"** where some Autopilot devices were missing their assigned profiles.
- Resolved issues with parameters **"AzureAD Group Members Filter Starts With"** and **"AzureAD Group Members Nested Crawler Enable"**, which previously caused timeouts.
- Updated the [**Custom Inventory for Windows**](https://github.com/PowerStacks-BI/Windows-Custom-Inventory) script to resolve a bug in the driver matching process.

### Semantic Model Changes

- Updated the **"Compliance State Device”** object — removed summarization on **"Update Installed Time (Days)"** and **"Update Release Time (Days)"** for more granular reporting.
- Updated the **"Authorization"** object to include a new **"Viewer Email"** field.
- Renamed object “Renamed object **"User Proxy Addresses"** to **"User Proxy Address"** for naming consistency.

### Important Notes

- Microsoft Graph API instability (HTTP 503/504) continues to affect some tenants intermittently. The new **"AzureAD Application Assignment Enable"** parameter provides a temporary workaround. Please contact us if you have this issue. We need more support cases opened with Microsoft so they will prioritize resolving this!
- If you have existing custom reports referencing the renamed object **"User Proxy Addresses"**, you must update them to use **"User Proxy Address"**.
- Always [backup your custom reports](backup-custom-reports.md) before upgrading!
