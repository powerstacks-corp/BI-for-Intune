---
title: "Versions 54.0 Feb. 6, 2025"
---
# Versions 54.0 (AppSource Versions 1048)
**BI for Intune Version 54 (February 6, 2025)**

Version 54 resolves an issue in some environments that have the Intune Suite.

**Important Notes:**
Several customers have recently reported upgrade failures resulting in the loss of their custom reports. Please do not forget to [backup before you upgrade](backup-custom-reports.md)!


## Below Are the Changes in Version 54.0


- **Bug fixes:**Error due to "**Device Timeline Event**" timeout. Only affects customers who have the Intune Suite.
**Semantic Model Changes:**
- N/A
**Product Enhancements:**
- Added a new parameter to the Semantic Model. "AzureAD Timeline Event Day(s)" to control how many days of event data to get from the device timeline.Default is 7 days.
- Max is 30 days.
- To disable set -1.
**Updates to Existing Pages:**
- N/A
