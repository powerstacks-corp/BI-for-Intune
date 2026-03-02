---
title: "Version 59.0 May 27, 2025"
---
# What's New in BI for Intune v59
**Release Date**: May 27, 2025
**App Source Version**: 1051

Version 59 is a small release that adds some newly requested features and improves performance. Some features in this release require an updated version of the [Custom Inventory Script for Windows](windows-inventory-collection-script.md). Please see the full details below.

**Important Notes:**
Several customers have recently reported upgrade failures resulting in the loss of their custom reports. Please do not forget to [backup before you upgrade](backup-custom-reports.md)!


## Version 59.0 Release Details


**Product Enhancements:**

- Changes to the Driver Inventory page:Moved the Last Update field from the Summary Visual to the Device Visual
Changes to the App Inventory page:
- Added new filter: App Inventory Type (available in the filters pane)
Optimized code to reduce memory usage from the recently added Driver Inventory object
**New Features:**

- None in this release.

**Bug Fixes:**

- None in this release.

**Semantic Model Changes:**

- **Updates to existing objects:**App Inventory object:Added field: App Inventory Type**Note:** Requires an updated version of the [Custom Inventory Script for Windows](windows-inventory-collection-script.md). The script must collect UWP apps and populate a new field named AppType with values Win32 or UWP.
Configuration State, iOS/iPadOS Update Policy State, macOS Update Policy State, Windows Update Ring State objects:
- These objects now report Device Status only. Previously, status was derived from Device + User Status, which caused updates to be missed for devices with a primary owner but no associated user status.

**Important Notes:**

- Always back up your custom reports before upgrading!
