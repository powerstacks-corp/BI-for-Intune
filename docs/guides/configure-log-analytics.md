---
title: "Configure Log Analytics"
---
# Configure Log Analytics
Log Analytics is a tool in the Azure portal to edit and run log queries. We are leveraging Log Analytics as an inexpensive storage medium for storing custom inventory data collected from Windows devices. This data is then synchronized to Power BI to be used in BI for Intune.

**Prerequisites:**

1. Prior to starting these steps, you should create a Log Analytics workspace as described by Microsoft in [this article](https://docs.microsoft.com/en-us/azure/azure-monitor/logs/quick-create-workspace).
1. If you are using [Windows Update for Business Reports](https://docs.microsoft.com/en-us/windows/deployment/update/update-compliance-get-started), you should use the same Log Analytics workspace.

### Step 1





1. In the **Azure portal** search for, and select, **Log Analytics workspaces**.
![](images/Search-for-LA-1024x266.png)
### Step 2





1. Select the **Log Analytics workspace** where you will store the **custom inventory data**.
![](images/Select-LA-Workspace-1024x267.png)
### Step 3





1. Select **Access control (IAM)**.
![](images/IAM-1024x606.png)
### Step 4





1. Select **Add**.
1. Select **Add role assignment**.
![](images/Add-Role-Assignment-1024x812.png)
### Step 5





1. Search for **Log Analytics Reader**.
1. Select **Log Analytics Reader**.
1. Select **Next**.
![](images/Log-Analytics-Reader-591x1024.png)
### Step 6





1. Select **Assign access** to: **User, group, or service principal**.
1. Select **+Select Members**.
1. Search for and select the name of the **Enterprise App Registration** that was created when you installed BI for Intune.
1. Select **Next**.
![](images/Select-Ent-App-1024x568.png)
### Step 7





1. Select **Review and assign**.
![](images/Review-and-Assign-742x1024.png)
### Step 8





1. Select **Agents management**.
1. Record the **Workspace ID** for later use.
1. Record the **Primary key**for later use.
![](images/Agents-Management-1024x352.png)
