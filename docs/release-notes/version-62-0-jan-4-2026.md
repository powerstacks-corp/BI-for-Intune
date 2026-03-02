---
title: "Version 62.0 Jan 4, 2026"
---
# What's New in BI for Intune v62
**Release Date**: January 4, 2026
**App Source Version**: 1054

Version 62 adds a new data source, the "Windows Distribution Report" data from Intune, to provide greater details about installed Windows versions.

**Important Notes:**
Several customers have recently reported upgrade failures resulting in the loss of their custom reports. Please do not forget to [backup before you upgrade](backup-custom-reports.md)!


# Version 62.0 Release Details


### Product Enhancements

- Windows devices managed by **MAM-WE** now display a friendly **Device Type** of **“Windows”** instead of **“1”**.

### New Features

- Added a new data source: **Windows Distribution Report**.
- Added new fields under the **Device** category (sourced from **Windows Distribution Report**):Device Tag
- OS Build Number
- OS Build Revision
- OS Quality Update Release Date
- OS Quality Update Release Date (Months)
- OS Quality Update Type
- OS Quality Update Version
- WU Distribution Enrolled
**“OS Release ID”** in the **Device** category is now populated by **Windows Distribution Report** data.Added a new **Device Tag** category to the model with a new field:
- **Tag** *(Note: This is only populated for Windows devices.)*
Changes to the **Device Info** page:
- Added **OS Quality Update Version**
- Added **OS Quality Update Release Date**
- Added **OS Quality Update Type**

### Bug Fixes

- N/A

### Semantic Model Changes

- Added new **Device** fields sourced from the **Windows Distribution Report**:Device Tag
- OS Build Number
- OS Build Revision
- OS Quality Update Release Date
- OS Quality Update Release Date (Months)
- OS Quality Update Type
- OS Quality Update Version
- WU Distribution Enrolled
**“OS Release ID”** in the **Device** category is now populated by **Windows Distribution Report** data.Added a new **Device Tag** category with the new **Tag** field *(Windows devices only)*.
### Important Notes

- Microsoft Graph API instability (HTTP 503/504) continues to affect some tenants intermittently. The new **"AzureAD Application Assignment Enable"** parameter provides a temporary workaround. Please contact us if you have this issue. We need more support cases opened with Microsoft so they will prioritize resolving this!
- Always [backup your custom reports](backup-custom-reports.md) before upgrading!
