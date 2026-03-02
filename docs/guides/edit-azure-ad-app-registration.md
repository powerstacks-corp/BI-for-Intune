---
title: "Edit Azure AD App Registration"
---
# Edit the Azure AD Application Registration
Before you can collect custom inventory data from Windows 10 devices you must add the permissions required to read Log Analytics data to the Azure AD application registration.

These steps might have been performed when originally creating the Azure AD App Registration. If so you can skip this step when configuring the Windows 10 custom inventory steps.


**Prerequisites:**The user performing this step requires Global Admin and Subscription Admin rights.

### Step 1





1. Login to **portal.azure.com**or **entra.microsoft.com**  using a global administrator account.
1. Search for and select **App registrations**.
1. Select your BI for Intune **App** **registration**. (**Note:** The name of your may vary from what is in this doc.)
![](images/Edit-App-Registration-1024x421.png)
### Step 2





1. On the Enterprise App page select **API Permissions**.
![](images/API_Permissions-1024x530.png)
### Step 3





1. Select **Add a permission**.
![](images/Add-Another-Permission-1024x566.png)
### Step 4





1. Select **APIs my organization uses**.
![](images/API-for-My-Org-1024x626.png)
### Step 5





1. Search for **Log Analytics**.
1. Select **Log Analytics API**.
![](images/Log-Analytics-API-1024x429.png)
### Step 6





1. Select **Application Permissions**.
![](images/Log-Analytics-Applicattion-Permissions-1024x359.png)
### Step 7





1. Select **Data.Read**.
1. Select **Add permissions**.
![](images/Log-Analytics-Data.Read_-692x1024.png)
### Step 8





1. Select **Grant admin consent for **.
![](images/Grant-Admin-Consent-1024x667.png)
### Step 9





1. Select **Yes**at the prompt.
1. You have now completed the steps required.
![](images/Admin-Consent-Yes-1024x108.png)
