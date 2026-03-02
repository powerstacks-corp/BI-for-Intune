---
title: "Azure AD App Permissions"
---
# Azure AD Application Required Permissions
Below are all of the permissions required to be configured on the Azure AD App Registration. Some are optional depending upon the features of BI for Intune that you intend to enable. See [Create Azure AD App Registration](create-azure-ad-app-registration.md) for more information.

**Prerequisites:**The user configuring these permissions requires Global Admin and Subscription Admin rights.





### 1




								**Required for basic functionality:**




- **API:**
  Microsoft Graph
- **Permission Type:**
  Application
- **Permissions:**
  AuditLog.Read.All
  DeviceManagementApps.Read.All
  DeviceManagementConfiguration.Read.All
  DeviceManagementManagedDevice.Read.All
  DeviceManagementRBAC.Read.All
  DeviceManagementServiceConfig.Read.All
  Directory.Read.All
  Policy.Read.All
  Reports.Read.All
  CloudPC.Read.All

**Required for custom inventory and Windows Update for Business Reports**




- **API:**
  Log Analytics API
- **Permission Type:**
  Application
- **Permissions:**
  Data.Read
![intune app permissions](images/intune_app_permissions-1-1024x714.png)
