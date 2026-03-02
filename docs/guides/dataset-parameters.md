---
title: "Dataset Parameters"
---
# Dataset Parameters Explained
The BI for Intune dataset contains some parameters that must be configured in order to synchronize data from Intune to Power BI. Other parameters add additional functionality to BI for Intune. This article explains each of the parameters in detail.

### Step 1





1. To view or modify the dataset parameters select **Workspaces**.
1. Select the **BI for Intune** workspace.
![](images/intune_workspace_1.png)
### Step 2





1. Hover over the bi_for_intune **Sematic mode**l to reveal a **kebab menu** (three vertical dots).
1. Select the **kebab menu**.
1. Select **Settings**.
![intune model settings](images/intune_model_settings-1024x1013.png)
### Step 3





1. Expand **Parameters**.
![](images/dataset_parameters.png)
### Step 4
				AzureAD Sign-Ins Failure Only





1. Required configuration: None
1. Default value: TRUE
1. Determines whether or not successful sign-ins are available in the reports. By default, failed sign-in data are available in the reports. Getting successful sign-in data will result in slower synchronizations and possibly cause synchronization timeouts.
![](images/AzureAD-Sign-Ins-Failure-Only.png)
### Step 5
				AzureAD LogAnalytics Enable





1. Required configuration: Yes, only for our customer inventory solution and/or Windows Update for Business reports (formerly named Azure Update Compliance v2.)
1. Default value: FALSE
![](images/AzureAD-LogAnalytics-Enable.png)
### Step 6
				ApiKey





1. Required configuration: Yes
1. Default value: Blank
1. This should be the API Key that you received from us after completing the [**Request a Trial Key**](http://ec2-44-233-222-61.us-west-2.compute.amazonaws.com/wordpress/index.html%3Fp=7938.html) form.
![](images/api_key.png)
### Step 7
				AzureAD TenantID





1. Required configuration: Yes
1. Default value: Blank
1. This should be your Azure AD tenant ID.
1. Note: An easy way to get this is to go to [https://www.whatismytenantid.com/](https://www.whatismytenantid.com/)
![](images/AzureAD-TenantID.png)
### Step 8
				AzureAD ClientID





1. Required configuration: Yes
1. Default value: blank
1. The **Application (client) ID** from the [**Azure AD App Registration**](create-azure-ad-app-registration.md).
![](images/client_id.png)
### Step 9
				AzureAD ClientSecret





1. Required configuration: Yes
1. Default value: Blank
1. **The Azure AD Client Secret is the most common mistake that customers make when installing BI for Intune**.  It is shown as the "Value" when adding the client secret to the [**Azure AD App Registration**](create-azure-ad-app-registration.md). The **Client Secret** **does not** have dashes (-) in it. The **Client Secret** **looks similar** to this: aBcDE~fGh.I.JKlmnopqRsTuVwXyZ1234567890
![](images/client_secret-1.png)
### Step 10
				AzureAD Sign-Ins Day(s)





1. Required configuration: None
1. Default value: 1
1. By default, only sign-in data from the last 1 day are available in the reports. Getting more days of sign-in data will result in slower synchronizations and possibly cause synchronization timeouts. The max value is 7.
1. Note, sign-in data can be completely disabled by setting this value to -1.
![](images/AzureAD-Sign-Ins-Days.png)
### Step 11
				AzureAD PageSize API





1. Required configuration: None
1. Default value: 10000
1. Determines the page size for MS Graph queries. Do not change this value unless instructed to do so by PowerStacks support.
![](images/AzureAD-PageSize-API.png)
### Step 12
				AzureAD LogAnalytics WorkspaceID





1. Required configuration: Yes, only for our custom inventory solution and/or Windows Update for Business reports (formerly named Azure Update Compliance v2.)
1. Default value: Blank
1. This is the workspace ID of the Log Analytics workspace where the custom inventory and/or Windows Update for Business Reports data is stored.
1. When using our custom inventory solution and Windows Update for Business Reports both must store data in the same Log Analytics workspace.
![](images/AzureAD-LogAnalytics-WorkspaceID.png)
### Step 13
				AzureAD LogAnalytics Day(s)





1. Required configuration: None
1. Default value: 30
1. Allows you to configure the number of days of data to pull from Log Analytics.
![](images/AzureAD-LogAnalytics-Days-1.png)
### Step 14
				AzureAD LogAnalytics PageSize API





1. Required configuration: None
1. Default value: 10000
1. Determines the page size of Log Analytics queries. Do not change this value unless instructed to do so by PowerStacks support.
![](images/AzureAD-LogAnalytics-PageSize-API.png)
### Step 15
				AzureAD Export URL Enable





1. Required configuration: Yes, only if the AzureAD Export URL has been populated.
1. Default value: FALSE
1. Determines if the URL from the AzureAD Export URL is used or if the URL is found automatically by the app.
1. Setting this parameter to TRUE will create a new data source credential that must be configured. Authentication method: Anonymous
1. Privacy Level: Organizational
1. Check "Skip test connection"
![](images/AzureAD-Export-URL-Enable.png)
### Step 16
				AzureAD Export URL





1. Required configuration: None
1. Default value: Blank
1. The export URL varies from one Azure tenant to another. If this value is not populated our code will find the correct URL that your Intune environment uses to export data, however, to avoid redirection and improve security it is recommended to set this parameter.
1. Be sure to also set AzureAD Export URL Enable = TRUE when using this parameter.
1. To learn more please see our [Configure Intune Export API](export-api-parameter.md) documentation.
![](images/AzureAD-Export-URL.png)
### Step 17
				AzureAD Export URL Timeout (s)





1. Required configuration: None
1. Default value: 3600
1. Determines the amount of time the sync process waits for each Intune export job before it times out. Do not change this value unless instructed to do so by PowerStacks support.
![](images/AzureAD-Export-URL-Timeout-s.png)
### Step 18
				AzureAD Export URL Wait (s)





1. Required configuration: None
1. Default value: 1
1. Determines the amount of time the sync process waits for each Intune export job to report a status and then loops until a status is received. Do not change this value unless instructed to do so by PowerStacks support.
![](images/Wait_URL_Seconds.png)
### Step 19
				AzureAD Compliance Policy Setting State Enable





1. Required configuration: None
1. Default value: TRUE
1. This parameter disables the synchronization of Configuration Profiles of the Settings Catalog type. It is TRUE, meaning that the results of those profiles are sync'd to Power BI. This was parameter was added due to periodic issues in a small number of Azure data centers that caused synchronization failures. Leave at the default value unless instructed otherwise by PowerStacks support.
![](images/compliance_policy_settings.png)
### Step 20
				AzureAD Group Dynamic Members Only





1. Required configuration: None
1. Default value: TRUE
1. When set to TRUE only members of dynamic groups will be available in the reports. Changing this to FALSE will make members of assigned groups available in the reports. However, getting the members of assigned groups is a more intensive process and might cause synchronization timeouts.
![](images/AzureAD-Group-Dynamic-Members-Only.png)
### Step 21
				AzureAD Group Members Enable





1. Required configuration: None
1. Default value: TRUE
1. Determines whether or not the members of Azure AD groups are available in the reports. Depending upon the number of Azure AD groups this could cause synchronization failures.
1. By default, group members of dynamic groups are available in the reports however this can be modified by the AzureAD Group Dynamic Members Only parameter.
![](images/AzureAD-Group-Members-Enable.png)
### Step 22
				AzureAD Pace API (s)





1. Required configuration: None
1. Default value: 0
1. Determines the amount of time the sync process waits for a response from the Pace API's and then it loops until a response is received. Do not change this value unless instructed to do so by PowerStacks support.
![](images/AzureAD-Pace-API-s.png)
### Step 23
				AzureAD Disk Max Wear





1. Required configuration: None
1. Default value: 90
1. Used to calculate disk health. Default value is based upon the Microsoft [MSFT_StorageReliabilityCounter](https://learn.microsoft.com/en-us/windows-hardware/drivers/storage/msft-storagereliabilitycounter) class documentation.
![](images/AzureAD-Disk-Max-Wear.png)
### Step 24
				AzureAD Disk Max Read Errors





1. Required configuration: None
1. Default value: 100
1. Used to calculate disk health. Default value is based upon the Microsoft [MSFT_StorageReliabilityCounter](https://learn.microsoft.com/en-us/windows-hardware/drivers/storage/msft-storagereliabilitycounter) class documentation.
![](images/AzureAD-Disk-Max-Read-Errors.png)
### Step 25
				AzureAD Disk Max Write Errors





1. Required configuration: None
1. Default value: 100
1. Used to calculate disk health. Default value is based upon the Microsoft [MSFT_StorageReliabilityCounter](https://learn.microsoft.com/en-us/windows-hardware/drivers/storage/msft-storagereliabilitycounter) class documentation.
![](images/AzureAD-Disk-Max-Write-Errors.png)
### Step 26
				AzureAD Export URL Batch





1. Required configuration:
1. Default value:
1.
![azuread export url batch](images/azuread-export-url-batch.png)
### Step 27
				AzureAD Application State Enable





1. Required configuration:
1. Default value:
1. This parameter
![azuread script state enable](images/azuread-script-state-enable.png)
### Step 28
				AzureAD LogAnalytics App Inventory PageSize API





1. Required configuration:
1. Default value:
1. Used to .
![azuread loganalytics app inventory pagesize api](images/azuread-loganalytics-app-inventory-pagesize-api.png)
### Step 29
				AzureAD Script State Enable





1. Required configuration: None
1. Default value: TRUE
1. This parameter disables the synchronization of Configuration Profiles of the Settings Catalog type. It is TRUE, meaning that the results of those profiles are sync'd to Power BI. This was parameter was added due to periodic issues in a small number of Azure data centers that caused synchronization failures. Leave at the default value unless instructed otherwise by PowerStacks support.
![azuread script state enable](images/azuread-script-state-enable.png)
### Step 30
				AzureAD Export URL CloudPC





1. Required configuration: None
1. Default value: https://graph.microsoft.com
1. This parameter only needs to be configured in environments using Windows 365 (Cloud PC) and also have configured the AzureAD Export URL.
![azuread export url cloudpc](images/azuread-export-url-cloudpc.png)
### Step 31
				AzureAD Driver Updates Enable





1. Required configuration: None
1. Default value: TRUE
1. This parameter disables the synchronization of driver information from Windows Driver update management in Microsoft Intune. Default value is TRUE, meaning that the Windows Driver Updates information is sync'd to Power BI. This was parameter was added because the driver data has caused timeout issues for several customers. For best results be selective about the drivers which you approve and keep them to a minimum.
![azuread driver updates enable](images/azuread-driver-updates-enable.png)
### Step 32
				AzureAD Login URL





1. Required configuration: None
1. Default value: [https://api.loganalytics.io](https://login.microsoftonline.com)
1. This parameter is only used in multi-cloud environments. For example, if you have some things in the Gov cloud and other things in the public cloud.
![azuread login url](images/azuread-login-url.png)
### Step 33
				AzureAD Graph URL





1. Required configuration: None
1. Default value: https://graph.microsoft.com
1. This parameter is only used in multi-cloud environments. For example, if you have some things in the Gov cloud and other things in the public cloud.
![azuread graph url](images/azuread-graph-url.png)
### Step 34
				AzureAD LogAnalytics URL





1. Required configuration: None
1. Default value: https://api.loganalytics.io
1. This parameter is only used in multi-cloud environments. For example, if you have some things in the Gov cloud and other things in the public cloud.
![azuread loganalytics url](images/azuread-loganalytics-url.png)
### Step 35
				AzureAD Timeline Event Day(s)





1. Required configuration: No
1. Default value: 7 days
1. Max value: 30
1. -1 disables this feature.
1. Only valid for customers with the "Microsoft Intune Suite add-on" license.
1. Defines the number of days data is pulled from the [device timeline in Endpoint Analytics](https://learn.microsoft.com/en-us/mem/analytics/enhanced-device-timeline).
![azuread timeline event day(s)](images/azuread-timeline-event-days.png)
### Step 36
				AzureAD Group Members Filter Starts With





1. Required configuration: None
1. Default value: % (filter is disabled)
1. This parameter allows for defining a group name prefix to limit group sync to only get members of groups beginning with the prefix.
![azuread group members filter starts with](images/azuread-group-members-filter-starts-with.png)
### Step 37
				AzureAD Group Members Nested Crawler Enable





1. Required configuration: None
1. Default value: FALSE
1. Changes to this parameter only apply if a group members prefix is assigned. By default, when AzureAD group members filter starts with is set to '%' we get all transitive group members. If you define a prefix you need to also define True or False here to determine whether or not we get transitive group members.
![azuread group members nested crawler enable](images/azuread-group-members-nested-crawler-enable.png)
