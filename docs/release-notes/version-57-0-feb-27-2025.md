---
title: "Version 57.0 Feb. 27, 2025"
---
# Versions 57.0 (AppSource Versions 1049)
**BI for Intune Version 57 (February 27, 2025)**

Version 57 resolves an issue in some environments that use Windows 365 (Cloud PC). This version also brings many new features that have been requested by customers. Please see the full list below.

**Important Notes:**
Several customers have recently reported upgrade failures resulting in the loss of their custom reports. Please do not forget to [backup before you upgrade](backup-custom-reports.md)!


## Below Are the Changes in Version 57.0


- **Product Enhancements:**

  Updated the Device Info page:

  Added the new fields "Sign-In User" and "Sign-In"

  **Note**: These might be blank for all devices depending upon your dataset parameters "AzureAD Sign-Ins Failure Only" and "AzureAD Sign-Ins Day(s)".


Added filters "Has Enrolled User", "Has Last Logon User", "Has Primary User", "Has Sign-in user"


**Semantic Model Changes:**

- Updates to existing objects:

  Added new fields to the “Device” object:

  Has Enrolled User
- Has Last Logon User
- Has Primary User
- Has Sign-in user


Updated values in the “OS” field in the “Device” object. It now displays “Windows 10” for Windows OS versions starting with “10.0.1*” and “Windows 11” for OS Versions starting with “10.0.2*”. Previously it only showed “Windows” for both.
Added new fields to the “User Devices” object:

- Sign-in
- Sign-in (Days)
- Sign-in User
- **Note**: These new "Sign-in" fields are using sign-in data which, by default, only collects failed sign-ins and only collects data for the last 1 day.


Updated values in the "Control Name" field of the "Conditional Access Control" object. Previously the value displayed as "Require Domain-Joined Device" now it is displayed as "Require Hybrid-Joined Device".


Added new semantic model parameter(s):

- AzureAD Group Members Filter Starts With

  Default: % (Filter is disabled)
- Add a prefix to limit group sync to only get members of groups beginning with the prefix.


AzureAD Group Members Nested Crawler Enable:

- Default: False
- If True the sync will crawl any nested group, and bring back all their transitive members. **Note**: This mode only works when "AzureAD Group Dynamic Members Only" is "False"


**Bug Fixes:**

- Fixed Sync Error:

  Customers using CloudPC might see the error, “Error: Column 'Intune Device ID' in Table 'Cloud PC Insight' contains blank values and this is not allowed for columns on the one side of a many-to-one relationship or for columns that are used as the primary key of a table.” This is because there is a delay between when a CloudPC is deleted, and when the Cloud PC Insight Report is updated. **Note:** This might cause the Insight data to report on deleted devices.
