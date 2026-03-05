---
title: "WUfB Reports"
---
# Windows Update for Business Reports
Microsoft recommends that customers using Intune should onboard devices to [Windows Update for Business reports](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/public-preview-of-azure-workbooks-for-update-compliance/ba-p/3601310) (formerly named "Azure Update Compliance") to monitor Windows Updates and patch compliance. We have made this data available in BI for Intune and have included Update Compliance Quality Updates and Update Compliance Feature Updates reports right out of the box. In order to populate the data for those reports you must onboard your devices to the new Windows Update for Business reports service.

Below are the high-level steps required to onboard devices to the service. I won't go into great details here because Microsoft has good documentation on this, but it is easy to overlook some of the steps so I will point them out here.

!!! warning "Important"
    The custom inventory data and WUfB Reports data **must be in the same Log Analytics workspace**. If you have already deployed our custom inventory solution using the [Configure Log Analytics](configure-log-analytics.md) guide, select **Use an existing workspace** when enabling WUfB Reports and point it to the same workspace. If you are setting up WUfB Reports first, deploy the custom inventory ARM template later using the **Use an existing workspace** option and point it to the WUfB Reports workspace.

### Step 1: Enable WUfB reports in Azure



1. Follow the [guide by Microsoft](https://learn.microsoft.com/en-us/windows/deployment/update/wufb-reports-enable) to Add Windows Update for Business reports to your Azure subscription. Be sure to use the same Log Analytics workspace as our custom inventory solution.
![](../images/intune_update_compliance_v2-1024x884.png)

### Step 2: Deploy the configuration profile



1. Follow the Microsoft documentation to create a [Configuration Profile in Intune](https://learn.microsoft.com/en-us/windows/deployment/update/wufb-reports-configuration-intune) and deploy to Windows computers.
![](../images/uc_config_profile.png)

### Step 3: Configure Log Analytics integration



1. If you have already completed the [Configure Log Analytics](configure-log-analytics.md) guide for our custom inventory solution, no additional configuration is needed for WUfB Reports data to flow into Power BI. If not, you must complete the following steps:
    - [Configure Log Analytics](configure-log-analytics.md) — Deploy the ARM template and set up the inventory app registration
    - [Dataset Settings for Custom Inventory](dataset-settings-for-custom-inventory.md) — Enable Log Analytics in the Power BI dataset
    - [Edit App Registration for Log Analytics](edit-azure-ad-app-registration.md) — Add the Log Analytics API Data.Read permission to the Power BI app registration
1. According to Microsoft you will start seeing data in about 24 hours however, we've had customers report that it took much longer.
![](../images/relax.png)

### Step 4: View the WUfB reports data



1. Once the initial data Windows Update for Business Reports data processing has completed you will see data in our "UC Quality Updates" and "UC Feature Updates" pages.
![Intune Windows Update for Business Reports](../images/intune_uc_quality_updates-1024x582.png)
