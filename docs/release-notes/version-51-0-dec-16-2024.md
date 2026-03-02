---
title: "Version 51.0 Dec. 16, 2024"
---
# Versions 51.0 (AppSource Versions 1046)
On December 11, 2024, we released BI for Intune version 51. This update is primarily targeted to GCC and GCC high customers.

**Important Notes:**
Several customers have recently reported upgrade failures resulting in the loss of their custom reports. Please do not forget to [backup before you upgrade](backup-custom-reports.md)!


## Below Are the Changes in Version 51.0


- **Semantic Model Changes**:New parameters on the semantic model allows changing the cloud sources. This means that Power BI can be in the commercial cloud and Intune in GCC or GCC high for example. AzureAD Login URL: Commercial & GCC (Default) "https://login.microsoftonline.com", GCC High "https://login.microsoftonline.us"
- AzureAD Graph URL: Commercial & GCC (Default) "https://graph.microsoft.com", GCC High "https://graph.microsoft.us"
- AzureAD LogAnalytics URL: Commercial & GCC (Default) "https://api.loganalytics.io", GCC High "https://api.loganalytics.us"
**Bug fix**:
- In some environments devices were missing from the "Autopilot Enrollment Status" page.
