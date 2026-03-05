---
title: "Create Inventory App Registration"
---
# Create Inventory App Registration

The inventory collection scripts for Windows and macOS use a dedicated App Registration to authenticate and write data to Log Analytics via the Azure Monitor Logs Ingestion API.

!!! warning
    This is a **separate** app registration from the one used by Power BI. Do not reuse your existing BI for Intune app registration for the inventory scripts.

!!! info "Two App Registrations"
    BI for Intune uses **two separate App Registrations**:

    1. **Power BI App Registration** — The app registration created during the [BI for Intune installation](create-azure-ad-app-registration.md). This is used by Power BI to **read** data from the Log Analytics workspace.
    2. **Inventory App Registration** — Created in this guide. This is used by the Windows and macOS inventory scripts to **write** data to Log Analytics via the Logs Ingestion API.

**Prerequisites:**

- The user performing these steps requires **Application Administrator** or **Global Administrator** rights in Microsoft Entra ID.

### Step 1: Register the Application



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

### Step 2: Get the Enterprise Application Object ID



1. In the Azure Portal, navigate to **Microsoft Entra ID** > **Enterprise applications**.
1. Search for the app you registered in Step 1 (e.g., `PowerStacks-EnhancedInventory`).
1. Select the application and record the **Object ID** from the Overview page.

!!! warning "Important"
    The Object ID shown on the **Enterprise Applications** page is different from the one shown on the **App Registrations** page. You need the **Enterprise Application Object ID** (the service principal Object ID), not the App Registration Object ID.

### Values to Record

You should now have the following values ready:

| Value | Where to Find It | Used In |
|-------|-------------------|---------|
| **Tenant ID** | App Registration overview | [Windows](windows-inventory-collection-script.md) / [macOS](macos-inventory-collection-script.md) inventory scripts |
| **Client ID** | App Registration overview | [Windows](windows-inventory-collection-script.md) / [macOS](macos-inventory-collection-script.md) inventory scripts |
| **Client Secret** | Certificates & secrets | [Windows](windows-inventory-collection-script.md) / [macOS](macos-inventory-collection-script.md) inventory scripts |
| **Enterprise App Object ID** | Enterprise applications overview | [Deploy Custom Inventory Resources](configure-log-analytics.md) ARM template deployment |

### Next Step

Proceed to [Deploy Custom Inventory Resources](configure-log-analytics.md) to deploy the Azure resources.
