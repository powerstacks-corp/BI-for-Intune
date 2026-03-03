---
title: "Create Backup Workspace"
---
# Create a Backup Workspace
We strongly advise customers to always backup their custom reports before performing any in-place upgrades. Failure to do so could result in the loss of your custom reports!

Our backup process consists of creating a new workspace by installing a second instance of BI for Intune. There is no need to configure this instance, it's just a placeholder to which our script, documented in our "[Backup Custom Reports](backup-custom-reports.md)" document, copies all of your custom reports in case something goes wrong during the upgrade. In the unlikely event that the upgrade fails it may be necessary to configure the backup workspace and move it to production.

**Prerequisites:**The user executing these steps should be an administrator of the BI for Intune workspace.

### Step 1: Open Power BI AppSource





1. Login to **Power BI**.
1. Select **Apps**.
1. Select **Get apps**.
![](../images/Get-App-1024x211.png)
### Step 2: Find the BI for Intune template





1. Select **Template apps**.
1. Search for **BI for Intune**.
1. Select **BI for Intune**.
![](../images/intune-select-template-app-1024x664.png)
### Step 3: Get the template app





1. Select **Get It Now**.
![](../images/intune-get-it-now-1024x661.png)
### Step 4: Accept the Microsoft agreement





1. Accept the **Microsoft agreement**.
1. Select **Continue**.
![](../images/intune-ms-agreement.png)
### Step 5: Install into a new workspace





1. Select I**nstall another copy of the app into a new workspace**.
1. Enter a name for the new workspace.
1. Select **Install**.
![](../images/New_Backup_Workspace.png)
### Step 6: Confirm installation completed





1. Watch for the **update completed** notification in your browser.
1. There's no need to configure the dataset in this workspace, it's just a placeholder for the backup of your custom reports. Do not forget to run the backup script to copy your reports to the backup workspace.
![](../images/Update-Complete.png)
