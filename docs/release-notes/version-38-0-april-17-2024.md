---
title: "Version 38.0 April 17, 2024"
---
# Version 38.0 (AppSource Version 1033)
BI for Intune Version 38.0, shown as version 1033 in AppSource, was released on April 17, 2024.


## Below Are the Changes in Version 38.0


- **Features:**New “Application Category” category and fields in the data model to get the category information assigned to application deployments. Fields include:App Category Name
New fields added to the "Autopilot Deployment State" category. Fields include:
- Ap Deployment Duration (m)
- Ap Deployment Duration (h)
**Enhancements:**
- Added "App Category Name" to the default filters on the App Deployment page.
- Added "Group Name" and "Device Name" default filters to the App Inventory page.
**Bug Fixes:**
- In some Azure datacenters there is an issue that was causing the number of devices in Windows Update for Business Reports to decrease on Monday - Thursday and increase on Friday - Sunday. We implemented a code change to work around this issue.
**Important Notes:**
- Always backup your custom reports using our [backup process.](backup-custom-reports.md)
