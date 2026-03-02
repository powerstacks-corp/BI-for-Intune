---
title: "Version 40.0 June 8, 2024"
---
# Version 40.0 (AppSource Version 1035)
BI for Intune Version 40.0, shown as version 1035 in AppSource, was released on June 8, 2024. This version includes some modifications to our Windows custom inventory script. Customers should update to the latest version of the [custom inventory script](windows-inventory-collection-script.md).


## Below Are the Changes in Version 40.0


- **Features:**Windows custom inventory script changes:Collect friendly model name from Lenovo computers.
- Remove built-in laptop LCD's from inventory. This is configurable with a new parameter in the script.
- New script parameter to change the format for inventory date so that we Americans don't get too confused by seeing the format the rest of the World uses. (Examples: "MM-dd HH:mm", "dd-MM HH:mm")
**Enhancements:**
- On the App Deployment page, we replaced "App Pending Install" with "App Install Pending".
- On the Device Configurations page, we replaced the "Not Applicable" KPI with a "Conflict" KPI.
- Renamed all "UC" pages to use the prefix "WUfB" for clarity.
**Bug Fixes:**
- Implemented a fix for a Microsoft issue in Log Analytics.For large customers in the Illinois Azure data center, the Log Analytics pagination is not working properly, some records are pulled multiple times, and others are never pulled.
Fixed "Last Logon" being blank.
- Format in the Microsoft API was changed from EPOCH to Datetime. We had to make changes to accommodate for this.
**Important Notes:**
- Always backup your custom reports using our [backup process.](backup-custom-reports.md)
