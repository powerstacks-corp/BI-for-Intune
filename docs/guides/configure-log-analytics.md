---
title: "Configure Log Analytics"
---
# Configure Log Analytics
Log Analytics is a tool in the Azure portal to edit and run log queries. We leverage Log Analytics as an inexpensive storage medium for storing custom inventory data collected from Windows and macOS devices. This data is then synchronized to Power BI to be used in BI for Intune.

Custom inventory data is sent to Log Analytics using the **Azure Monitor Logs Ingestion API**. This requires deploying a set of Azure resources (Data Collection Endpoint, Data Collection Rule, and custom tables) which can be automated using our ARM template.

!!! info "Two App Registrations"
    This process uses **two separate App Registrations**:

    1. **Power BI App Registration** — The app registration created during the [BI for Intune installation](create-azure-ad-app-registration.md). This is used by Power BI to **read** data from the Log Analytics workspace.
    2. **Inventory App Registration** — A new app registration created in this guide. This is used by the Windows and macOS inventory scripts to **write** data to Log Analytics via the Logs Ingestion API.

**Prerequisites:**

1. The user performing these steps requires **Application Administrator** or **Global Administrator** rights in Microsoft Entra ID.
2. The user deploying the ARM template requires **Owner** or **Contributor + User Access Administrator** on the target Azure subscription or resource group.
3. If you are using [Windows Update for Business Reports](wufb-reports.md), you should use the same Log Analytics workspace for both WUfB Reports and custom inventory.

### Step 1: Create the Inventory App Registration



1. In the [Azure Portal](https://portal.azure.com), navigate to **Microsoft Entra ID** > **App registrations** > **New registration**.
1. Enter a **Name** for the application (e.g., `PowerStacks-EnhancedInventory`).
1. Specify who can use the application as **Accounts in this organizational directory only**.
1. Select **Register**.
1. From the App Registration overview, record the following values for later use:
    - **Application (Client) ID**
    - **Directory (Tenant) ID**
1. Navigate to **Certificates & secrets** > **New client secret**.
1. Enter a description and select an expiration period.
1. Select **Add** and record the **Value** (not the Secret ID). This value can only be displayed once.

!!! warning
    This is a **separate** app registration from the one used by Power BI. Do not reuse your existing BI for Intune app registration for the inventory scripts.

### Step 2: Get the Enterprise Application Object ID



1. In the Azure Portal, navigate to **Microsoft Entra ID** > **Enterprise applications**.
1. Search for the app you registered in Step 1 (e.g., `PowerStacks-EnhancedInventory`).
1. Select the application and record the **Object ID** from the Overview page.

!!! warning "Important"
    The Object ID shown on the **Enterprise Applications** page is different from the one shown on the **App Registrations** page. You need the **Enterprise Application Object ID** (the service principal Object ID), not the App Registration Object ID.

### Step 3: Deploy Azure Resources



1. Navigate to the [Enhanced Inventory Deploy](https://github.com/powerstacks-corp/EnhancedInventoryDeploy) repository on GitHub.
1. Click the **Deploy to Azure** button.
1. Select your target **Subscription** and **Resource group**.
1. Choose whether to **create a new** Log Analytics workspace or **use an existing** one.
    - If you are using [Windows Update for Business Reports](wufb-reports.md), select **Use an existing workspace** and point it to your WUfB Reports workspace.
1. When prompted for **Enterprise App Object Id**, paste the Object ID from Step 2. This allows the deployment to automatically assign the required permissions.
1. Select **Review + create** and then **Create**.

!!! tip
    If you leave the Enterprise App Object Id field blank, the deployment will still succeed but you will need to manually assign the **Monitoring Metrics Publisher** role to your inventory app registration on the Data Collection Rule after deployment.

The deployment creates the following resources:

- **Log Analytics Workspace** (new or uses existing)
- **Custom tables**: `PowerStacksDeviceInventory_CL`, `PowerStacksAppInventory_CL`, `PowerStacksDriverInventory_CL`
- **Data Collection Endpoint (DCE)**
- **Data Collection Rule (DCR)**
- **RBAC role assignment** (if Enterprise App Object Id was provided)

### Step 4: Record Deployment Outputs



1. After the deployment completes, navigate to your **Resource group**.
1. Select **Deployments** from the left menu.
1. Select the completed deployment.
1. Select the **Outputs** tab.
1. Record the following values for later use:
    - **DceURI** — the Data Collection Endpoint URI
    - **DcrImmutableId** — the immutable ID of the Data Collection Rule

### Step 5: Assign Log Analytics Reader to the Power BI App Registration



In this step you assign the **Log Analytics Reader** role to your **Power BI app registration** so that Power BI can read the custom inventory data from the workspace.

1. In the **Azure portal** search for, and select, **Log Analytics workspaces**.
![](../images/Search-for-LA-1024x266.png)
1. Select the **Log Analytics workspace** where you deployed the custom inventory resources.
![](../images/Select-LA-Workspace-1024x267.png)
1. Select **Access control (IAM)**.
![](../images/IAM-1024x606.png)
1. Select **Add** > **Add role assignment**.
![](../images/Add-Role-Assignment-1024x812.png)
1. Search for and select **Log Analytics Reader**, then select **Next**.
![](../images/Log-Analytics-Reader-591x1024.png)
1. Select **Assign access** to: **User, group, or service principal**.
1. Select **+Select Members**.
1. Search for and select the name of the **Power BI App Registration** (the one created when you installed BI for Intune — not the inventory app registration from Step 1).
1. Select **Next**, then **Review and assign**.
![](../images/Select-Ent-App-1024x568.png)

### Step 6: Record the Workspace ID



1. Open the **Log Analytics workspace** in the Azure portal.
1. On the **Overview** page (or **Properties**), locate and record the **Workspace ID**.
1. This value is needed for the [Power BI dataset parameters](dataset-settings-for-custom-inventory.md).

!!! note
    The Workspace Primary Key is no longer needed. The inventory scripts now authenticate using the Logs Ingestion API with the app registration credentials from Step 1.

### Summary

You should now have the following values recorded:

| Value | Source | Used In |
|-------|--------|---------|
| **Tenant ID** | Step 1 — App Registration | [Windows](windows-inventory-collection-script.md) / [macOS](macos-inventory-collection-script.md) inventory scripts |
| **Client ID** | Step 1 — App Registration | [Windows](windows-inventory-collection-script.md) / [macOS](macos-inventory-collection-script.md) inventory scripts |
| **Client Secret** | Step 1 — App Registration | [Windows](windows-inventory-collection-script.md) / [macOS](macos-inventory-collection-script.md) inventory scripts |
| **DceURI** | Step 4 — Deployment Outputs | [Windows](windows-inventory-collection-script.md) / [macOS](macos-inventory-collection-script.md) inventory scripts |
| **DcrImmutableId** | Step 4 — Deployment Outputs | [Windows](windows-inventory-collection-script.md) / [macOS](macos-inventory-collection-script.md) inventory scripts |
| **Workspace ID** | Step 6 — Log Analytics Workspace | [Power BI dataset parameters](dataset-settings-for-custom-inventory.md) |
