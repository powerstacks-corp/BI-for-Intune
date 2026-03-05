---
title: "FAQ"
---
# Frequently Asked Questions

### How often should I refresh my dataset?

We recommend configuring your dataset to refresh **up to 8 times per day** using the Power BI scheduled refresh feature. See [Configure Data Sync](configure-data-sync.md) for setup instructions.

### My custom inventory data is not showing up in the reports. What should I check?

1. Confirm that the **AzureAD LogAnalytics Enable** parameter is set to **TRUE** in the Power BI dataset settings. See [Dataset Settings for Log Analytics](dataset-settings-for-custom-inventory.md).
2. Verify that the **Workspace ID** is correct in the dataset parameters.
3. Ensure the **Log Analytics Reader** role has been assigned to the Power BI app registration on the Log Analytics workspace. See [Deploy Custom Inventory Resources](configure-log-analytics.md) Step 3.
4. Check that the inventory script is running successfully on devices by reviewing the script logs on a test device.
5. Confirm the gateway source credentials for `https://api.loganalytics.io/` are configured with **Anonymous** authentication. See [Dataset Settings for Log Analytics](dataset-settings-for-custom-inventory.md) Step 5.

### How long does it take for WUfB Reports data to appear?

According to Microsoft, data should appear within approximately **24 hours** after onboarding devices. However, some customers have reported that it can take longer. See [WUfB Reports](wufb-reports.md) for setup details.

### What permissions does the app registration need?

BI for Intune uses **two separate app registrations**:

- **Power BI App Registration** — Requires Microsoft Graph permissions (DeviceManagement, Directory.Read.All, AuditLog.Read.All, etc.) and Log Analytics API Data.Read. See [Azure AD App Permissions](azure-ad-app-permissions.md) for the full list.
- **Inventory App Registration** — Used by the inventory scripts to write data via the Logs Ingestion API. Requires the **Monitoring Metrics Publisher** role on the Data Collection Rule. See [Create Inventory App Registration](create-inventory-app-registration.md) for setup.

### Where do I find the Export API URL?

The Export API URL is unique to your tenant and must be captured from the browser developer tools. Open the **Intune admin center**, navigate to a report page, open the browser **Network** tab, and look for a request to a blob storage URL. See [Export API Parameter](export-api-parameter.md) for detailed steps.

### How do I fix broken visuals after an upgrade?

When we rename fields in a new version, any visualization containing a renamed field will appear broken (showing an exclamation point on the affected columns). To fix this:

1. Open the page containing the broken visual in **Edit** mode.
1. Select the broken visualization.
1. On the **Visualizations pane**, find the columns with an exclamation point ("!").
1. Select the "**X**" to remove the old column from the visualization.
1. On the **Data pane**, search for the new field name (check the [Release Notes](../release-notes/index.md) for the renamed fields).
1. Add the new field by placing a checkmark next to it.
1. Rearrange the field order if needed by dragging it in the Visualizations pane.
1. **Save** the changes.

!!! tip
    Always review the [Release Notes](../release-notes/index.md) before upgrading and [back up your custom reports](backup-custom-reports.md) first.
