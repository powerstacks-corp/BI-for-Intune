---
title: "Dataset Settings for Custom Inventory"
---
# Custom Inventory Dataset Parameters
The BI for Intune dataset contains some parameters that must be configured in order to synchronize data from Intune to Power BI. Other parameters, such as this one, add additional functionality to BI for Intune. In this article we configure the parameters required for our custom inventory functionality.

### Step 1





1. Select **Workspaces**.
1. Select the **BI for Intune** workspace.
![bi for intune workspace](images/bi_for_intune_workspace.png)
### Step 2





1. Hover over the bi_for_intune **Semantic model** to reveal a **kebab menu** (three vertical dots).
1. Select the **kebab menu**.
1. Select **Settings**.
![intune model settings](images/intune_model_settings-1024x1013.png)
### Step 3





1. Expand **Parameters**.
1. Locate the **AzureAD LogAnalytics Enable** field and change the value from FALSE to **TRUE**.
1. Locate the **AzureAD LogAnalytics WorkspaceID**field and enter the **Log Analytics Workspace ID**that you recorded during the [**Configuring Log Analytics  **](configure-log-analytics.md)step.
1. Select **Apply**.
![](images/Intune_Enable_Log_Analytics-538x1024.png)
### Step 4





1. Expand **Gateway source credentials**.
1. One of the four **Web**data sources should have an "**X**" next to it, select **Edit credentials** on that line.
![](images/intune-edit-credentials-2.png)
### Step 5





1. Confirm the **URL** is **https://api.loganalytics.io/**. If not, you have selected an incorrect **Edit credentials**. Go back to the previous step and ensure that you select the correct line.
1. Select **Anonymous** as the **Authentication method**.
1. Select **Organizational** as the **Privacy level setting for this data source**.
1. Check the box to **Skip test connection**.
1. Select **Sign in**.
![](images/Intune-LA-Signin.png)
