---
title: "WUfB Reports"
---
# Windows Update for Business Reports
Microsoft recommends that customers using Intune should onboard devices to [Windows Update for Business reports](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/public-preview-of-azure-workbooks-for-update-compliance/ba-p/3601310) (formerly named "Azure Update Compliance") to monitor Windows Updates and patch compliance. We have made this data available in BI for Intune and have included Update Compliance Quality Updates and Update Compliance Feature Updates reports right out of the box. In order to populate the data for those reports you must onboard your devices to the new Windows Update for Business reports service.

Below are the high-level steps required to onboard devices to the service. I won't go into great details here because Microsoft has good documentation on this, but it is easy to overlook some of the steps so I will point them out here. **Please note that if you are using our custom inventory solution be sure to use the same Log Analytics workspace for both the custom inventory and Enable Windows Update for Business reports.**

### Step 1





1. Follow the [guide by Microsoft](https://learn.microsoft.com/en-us/windows/deployment/update/wufb-reports-enable) to Add Windows Update for Business reports to your Azure subscription. Be sure to use the same Log Analytics workspace for our custom inventory solution as well as the Windows Update for Business reports.
![](images/intune_update_compliance_v2-1024x884.png)

### Step 2





1. Follow the Microsoft documentation to create a [Configuration Profile in Intune](https://learn.microsoft.com/en-us/windows/deployment/update/wufb-reports-configuration-intune) and deploy to Windows computers.
![](images/uc_config_profile.png)

### Step 3





1. If you previously configured our [custom inventory collection](configure-log-analytics.md), you can take the rest of the day off work. If not, you must perform the steps described in our [Configuring Log Analytics](configure-log-analytics.md), [Dataset Settings for Custom Inventory](dataset-settings-for-custom-inventory.md), and [Edit AD App Registration](edit-azure-ad-app-registration.md) documentation.
1. According to Microsoft you will start seeing data in about 24 hours however, we've had customers report that it took much longer.
![](images/relax.png)

### Step 4





1. Once the initial data Windows Update for Business Reports data processing has completed you will see data in our "UC Quality Updates" and "UC Feature Updates" pages.
![Intune Windows Update for Business Reports](images/intune_uc_quality_updates-1024x582.png)
