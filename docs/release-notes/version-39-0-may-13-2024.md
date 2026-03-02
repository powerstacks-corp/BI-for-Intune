---
title: "Version 39.0 May 13, 2024"
---
# Version 39.0 (AppSource Version 1034)
BI for Intune Version 39.0, shown as version 1033 in AppSource, was released on May 13, 2024. This version introduces a new Delivery Optimization report, a new Windows 11 Readiness Report, and Windows Firewall status.


## Below Are the Changes in Version 39.0


- **Features:**Add new "UC Windows 11 Readiness" page.
- Added new "UC Delivery Optimization" page.
- Added new "Firewall Status" page.
- New "Update Compliance Delivery Optimization" category and fields in the data model to report upon bandwidth savings with Delivery Optimization. This data is coming from the Windows Update for Business Reports logs. Fields include:DO BW (%)
- DO BW (GB)
- DO BW (MB)
- DO BW (TB)
- DO CDN (%)
- DO CDN (GB)
- DO CDN (MB)
- DO CDN (TB)
- DO City
- DO Configuration
- DO Content Type
- DO Country
- DO Group ID
- DO ISP DO MCC (%)
- DO MCC (GB)
- DO MCC (MB)
- DO MCC (TB)
- DO P2P (%)
- DO P2P (GB)
- DO P2P (MB)
- DO P2P (TB)
- DO Peering Status
- Last Update
- Last Update (Days)
New "Update Compliance Windows Readiness" category and fields in the data model to report on Windows 11 readiness using Windows Update for Business Reports data. Fields include:
- CPU Cores Ready
- CPU Family Ready
- Last Readiness Scan
- Last Readiness Scan (Days)
- Last Update
- Last Update (Days)
- Other Ready
- Other Reason
- RAM Ready
- Secure Boot Ready
- Storage Ready
- Target OS
- Target Release ID
- Target Version
- TPM Ready
New "Device Firewall" category and fields in the data model. Fields include:
- Firewall Disabled
- Firewall Enabled
- Firewall Limited
- Firewall Not Applicable
- Firewall Status
- Firewall Temporarily Disabled (default)
**Enhancements:**
- N/A
**Bug Fixes:**
- N/A
**Important Notes:**
- Always backup your custom reports using our [backup process.](backup-custom-reports.md)


## New UC Delivery Optimization Page
![uc do page](images/uc_do_page-1024x574.png)
