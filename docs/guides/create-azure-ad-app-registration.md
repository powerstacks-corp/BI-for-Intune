---
title: "Create Azure AD App Registration"
---
# Create Azure App Registration
Synchronizing data from Intune, Azure AD, Log Analytics, and other cloud data sources is done using application permissions. Here we are configuring the permissions required for Power BI to connect to the data sources to get the data.


**Prerequisites:**The user performing this step requires Global Admin and Subscription Admin rights.

### Step 1





1. Login to **portal.azure.com**or **entra.microsoft.com** using a global administrator account.
1. Search for and select **App registrations**.
1. Select **New registration**.
![](images/New_Registration-1024x491.png)
### Step 2





1. Enter a **Name** for the application. (This will not be seen by anyone other than admins.)
1. Specify who can use the application as **Accounts in this organizational directory** only.
1. Select **Register**.
![](images/Register_App-788x1024.png)
### Step 3





1. On the Enterprise App page select **API Permissions**.
![](images/API_Permissions-1024x530.png)
### Step 4





1. Remove the **User.Read** permission.
![](images/Remove_User_Read-1024x277.png)
### Step 5





1. When prompted to remove the permission, select **Yes, remove**.
![](images/yes_remove-1024x185.png)
### Step 6





1. Select **Add a permission**.
![](images/add_permission-1024x425.png)
### Step 7





1. Select **Microsoft Graph**.
![](images/MS_graph-1024x434.png)
### Step 8





1. Select **Application permissions**.
![](images/application_permissions-1024x403.png)
### Step 9





1. Search for **DeviceManagement**.
1. Select the following permissions:**DeviceManagementApps.Read.All**
1. **DeviceManagementConfiguration.Read.All**
1. **DeviceManagementManagedDevices.Read.All**
1. **DeviceManagementRBAC.Read.All**
1. **DeviceManagementServiceConfig.Read.All**
**Do not select the Add permissions button until told to do so in a later step within this document.**
![](images/Device-Management-Permissions-692x1024.png)
### Step 10





1. Search for **Directory**.
1. Select the following permissions:**Directory.Read.All**
**Do not select the Add permissions button until told to do so in a later step within this document.**
![](images/Directory-Permissions-1024x715.png)
### Step 11





1. Search for **AuditLog**.
1. Select the following permissions:**AuditLog.Read.All**
**Do not select the Add permissions button until told to do so in a later step within this document.**
![](images/Audit-Log-Permissions-1024x615.png)
### Step 12





1. Search for **Policy**.
1. Select the following permissions:**Policy.Read.All**
**Do not select the Add permissions button until told to do so in a later step within this document.**
![](images/Policy-with-CAP-1024x883.png)
### Step 13
				Only Required for Windows 365 (Cloud PC)





1. Search for **CloudPC**.
1. Select the following permissions:**CloudPC.Read.All**
**Do not select the Add permissions button until told to do so in a later step within this document.**
![cloudpc readall](images/cloudpc_readall-1024x774.png)
### Step 14





1. Search for **Reports**.
1. Select the following permissions:**Reports.Read.All**
Select the **Add permissions**button.
![](images/Reports-Permissions-plus-add-693x1024.png)
### Step 15
				Skip Directly to Step 19 if You Do Not Plan to Use Our Custom Inventory Solution





1. Select **Add a permission**.
![](images/Add-Another-Permission-1024x566.png)
### Step 16
				Only Required for Custom Inventory for Windows





1. Select **APIs my organization uses**.
![](images/API-for-My-Org-1024x626.png)
### Step 17
				Only Required for Custom Inventory for Windows





1. Search for **Log Analytics**.
1. Select **Log Analytics API**.
![](images/Log-Analytics-API-1024x429.png)
### Step 18
				Only Required for Custom Inventory for Windows





1. Select **Application Permissions**.
![](images/Log-Analytics-Applicattion-Permissions-1024x359.png)
### Step 19
				Only Required for Custom Inventory for Windows





1. Select **Data.Read**.
1. Select **Add permissions**.
![](images/Log-Analytics-Data.Read_-692x1024.png)
### Step 20





1. Select **Grant admin consent for **.
![](images/Grant-Admin-Consent-1024x667.png)
### Step 21





1. Select **Yes**at the prompt.
![](images/Admin-Consent-Yes-1024x108.png)
### Step 22





1. Select **Certificates & secrets**.
1. Select **New client secret**.
![](images/Certificates-and-Secrets-1024x569.png)
### Step 23





1. Enter a **Description**.
1. Select a value for **Expires**.
1. Select **Add**.
![](images/Add-a-client-secret-479x1024.png)
### Step 24





1. Record the **Value** data as the **Azure AD Client Secret**. This will be used later in the installation process. The value can only be displayed once, if you fail to record it here you will have to create a new one.
![](images/Client-Secret-Value-1024x203.png)
### Step 25





1. Select **Overview**.
1. Record the **Application (client) ID** as the **Azure AD Client ID**. This will be used later in the installation process.
1. Record the **Directory (tenant) ID** as the **Azure AD Tenant ID**. This will be used later in the installation process.
1. The **Azure AD Application registration** is now **complete**.
![](images/Overview-1024x228.png)
