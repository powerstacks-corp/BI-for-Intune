---
title: "Configure the Dataset"
---
# Configure The Dataset Parameters
The BI for Intune dataset contains some parameters that must be configured in order to synchronize data from Intune to Power BI. Other parameters add additional functionality to BI for Intune. In this article we will only configure the parameters required for basic functionality. For a full list of dataset parameters please see the [Dataset Parameters Explained](dataset-parameters.md) document.

### Step 1





1. Select **Workspaces**.
1. Select the **BI for Intune** workspace.
![](images/BI-for-Intune-Dataset.png)
### Step 2





1. Select **Datasets + dataflows**.
1. Hover over the **bi_for_intune** dataset to reveal a **kebab menu** (three vertical dots).
1. Select the **kebab menu**.
1. Select **Settings**.
![](images/BI-for-Intune-Dataset-settings-1024x830.png)
### Step 3





1. Expand **Parameters**.
1. Enter the **API Key** that you received from us after completing the [**Request a Trail Key**](request-a-trial-license.md) form.
1. Enter your **Azure AD tenant ID**that you recorded during the configuration of the [**Azure AD App Registration**](create-azure-ad-app-registration.md).
1. Enter the **Azure AD Client ID** that you recorded during the configuration of the [**Azure AD App Registration**](create-azure-ad-app-registration.md)[.](create-azure-ad-app-registration.md)
1. Enter the **Azure AD Client Secret** that you recorded during the configuration of the [**Azure AD App Registration**](create-azure-ad-app-registration.md). As mentioned in the previous article the **Client Secret** **does not** have dashes (-) in it. The **Client Secret** **looks similar** to this: **aBcDE~fGh.I.JKlmnopqRsTuVwXyZ1234567890****NOTE**: The most common mistake made when installing BI for Intune is on this step! The client secret **does not** **look like** this: **2f51572d-24ac-43bb-a73a-d3c346b69a45** it **does look like** this: **aBcDE~fGh.I.JKlmnopqRsTuVwXyZ1234567890**.
Select **Apply**.
![all parameters](images/all_parameters-152x1024.png)
### Step 4





1. Expand **Data Source Credentials**.
![](images/Intune_data_source_credentials.png)
### Step 5





1. Select each occurrence of **Edit credentials** one by one and configure each as follows: (**Note**: Depending upon your configuration you may or may not have all of the referenced credentials)Select **Anonymous** as the **Authentication method** and **Organizational** as the **Privacy level**for all credentials.
1. Select **Skip test connection** ONLY where the URL is **https://api.loganlytics.io** and/or similar to **https://amsua0401repexpstorage.blob.core.windows.net**
Select **Sign in** on each of the credentials.
![](images/intune_migration_skip_test_1.png)
