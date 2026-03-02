---
title: "Version 60.0 June 14, 2025"
---
# What's New in BI for Intune v60
**Release Date**: June 14, 2025
**App Source Version**: 1052

Version 60 brings some very exciting new features. Most notably the ability to track actions over time. We've added measures added new fields and measures for tracking device enrollments, OS installations, and cumulative update installations over time.  This will be very handy for reporting on how many days it takes to reach compliance after updates are released, tracking the progress of migrating to Intune, and/or tracking the progress of migrating to a new OS version.

**Important Notes:**
Several customers have recently reported upgrade failures resulting in the loss of their custom reports. Please do not forget to [backup before you upgrade](backup-custom-reports.md)!


# Version 60.0 Release Details


### Product Enhancements

- For "**Startup Performance**" data we now use the Export API instead of Graph. This will improve sync performance times.
- For "**Device Enrollment Failure**" data we now use the Export API instead of Graph. This will improve sync performance times.
- For "**Proactive Remediation State**" data we now use the Export API instead of Graph. This will improve sync performance times.
- The [Custom Inventory Script for Windows](windows-inventory-collection-script.md) has been updated to include HP warranty information. (**Note**: In our testing the HP API has shown to be highly unreliable so it might take a while to get inventory data back for all of your HP devices.)
- The **Custom Inventory Script for Windows** now caches warranty data to a .json file locally on each device so that it is no longer necessary to call the warranty API's monthly.

### New Features

- Added the ability to track device enrollments per day.
- Added the ability to track cumulative update installations per day.
- Added the ability to track Windows OS installations per day. (**Note**: OS Install date is updated during feature updates as well as Windows upgrades)

### Bug Fixes

- Renamed "**Battery Design Capacity (MWh)**" to "**Battery Design Capacity (mWh)**" on the "**Device Details**" object. (**Note**: This is a breaking change. Please see the important notes section.)
- Renamed "**Battery Full Charge Capacity (MWh)**" to "**Battery Full Charge Capacity (mWh)**" on the "**Device Details**" object. (**Note**: This is a breaking change. Please see the important notes section.)

### Semantic Model Changes

- Added “**Autopilot ID**” column to the “**Device**” object. This is the “**ID**” column returned by the “**windowsAutopilotDeviceIdentities**” API. (**Note**: Intune uses this as an object key, but Autopilot doesn’t use the value at all.)
- Renamed “**Enrolled Date**” to “**Enrolled Time**” on the “**Device**” object.
- Renamed “**Enrolled Date (Days)**” to “**Enrolled Time (Days)**” on the Device object.
- Added new “**Enrolled Date**” column to the “**Device**” object. This is used to track enrollment history per day. It’s simply the enrolled date without the exact time.
- Added “**Enrolled Cumulative Count**” column to the “**Device**” object. This is a cumulative count of devices enrolled on each day.
- Added “**Update Installed Date**” column to the “**Update Compliance State Device**” object.
- Added “**Update Installed Cumulative Count**” column to the “**Update Compliance State Device**” object. This is a cumulative count of devices that installed a given update each day.
- Added "**OS Install Time**" column to the “**Device Details**” object.
- Added "**OS Install Time (Days)**" column to the “**Device Details**” object.
- Added "**OS Install Date**" column to the “Device Details” object.
- Added "**OS Install Cumulative Count**" column to the “**Device Details**” object.

### Important Notes

- Changes to the “**Device Details**” object will break the Battery page in custom reports. Replace the old column(s) “**Battery Design Capacity (MWh)**” and “**Battery Full Charge Capacity (MWh)**” with the new column(s) "**Battery Design Capacity (mWh)**" and "**Battery Full Charge Capacity (mWh)**".
- The OS install date information requires upgrading to the latest version of the Custom Inventory script for Windows.$ComputerOSInstallDate=$ComputerInfo.OsInstallDate.ToUniversalTime().ToString("yyyy-MM-ddTHH:mm:ss.fffffffZ")
- $Inventory | Add-Member -MemberType NoteProperty -Name "OSInstallDate" -Value "$ComputerOSInstallDate" -Force

- Always [backup your custom reports](backup-custom-reports.md) before upgrading!


## Example Report of Cumulative Updates Installed Per Day


This report has been added to the Windows Update for Business custom report available on [GitHub](https://github.com/PowerStacks-BI/BI-for-Intune/tree/main/Windows%20Update%20for%20Business%20Reports). For more information, please see [this blog](https://powerstacks.com/windows-update-for-business-reports-reimagined-a-simpler-way-to-analyze-updates/).
![windows update progression](images/windows_update_progression-1024x566.png)
