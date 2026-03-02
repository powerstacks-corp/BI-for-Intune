---
title: "Windows Inventory Collection Script"
---
# Windows Inventory Collection Script
Many customers have requested the ability to report on things that are either not collected or not accurately collected by Intune. In an effort to fill these gaps in we have implemented a custom solution to collect some of the most commonly requested items. Currently this list includes:

1. Software installed on Windows 10 devices.
1. Software installation date.
1. Monitors (LCD's) connected to Windows 10 devices.
1. Disk health.
1. Last Reboot time.
1. Additional CPU details.
1. OS Install date.
1. Additional RAM details.
1. Battery health.
1. Friendly model names for Lenovo computers.
1. Warranty information for Dell, Lenovo, HP, and Getac computers.
1. M365 update installation and compliance details.
1. Windows driver inventory.

This data is collected via PowerShell, sent to a Log Analytics workspace, and then pulled into Power BI. Most customers leverage a Proactive Remediation detection to run the PowerShell script on a defined schedule. In this document we describe how to configure the script and deploy it using a Proactive Remediation however there are many ways that you might run a script on a schedule.

**Prerequisites:**

1. Appropriate licenses to use remediation scripts in Intune.
1. Dell requires an API token, which you can request by applying at [https://techdirect.dell.com/Portal/APIs.aspx](https://techdirect.dell.com/Portal/APIs.aspx).
1. Lenovo requires a client token. Unlike Dell, this process is less straightforward—you’ll need to contact your Lenovo account representative to request the token on your behalf.
1. HP requires both an API key and a secret. Note that the secret expires frequently. During our testing, the HP API was often unreliable; however, their support team was responsive, and it’s encouraging to see HP making the API available to customers again. You can initiate access by contacting your HP representative or by signing up at [https://developers.hp.com/](https://developers.hp.com/).

You can copy the PowerShell script from our [GitHub](https://github.com/PowerStacks-BI/Windows-Custom-Inventory) repository.
![github mark](images/github-mark-80x80.png)

### Step 1





1. Paste the **PowerShell** code into your favorite **script editor**.
1. On the line starting with **$CustomerId =**enter your Log Analytics **Workspace ID** between the quotes.
1. On the line starting with **$SharedKey =**enter your Log Analytics Workspace **Primary Key** between the quotes.
1. Save the script as a **.ps1** file. For example **CollectInventory.ps1**.
![](images/Inventory-Script-1024x372.png)
### Step 2





1. If you plan to collect warranty data set **$CollectWarranty** = **$true**.
1. Warranty data is cached locally on each device so that we do not make a call to the manufacturer API for each device each day. The cache is refreshed every 180 days by default. This is configurable using **$WarrantyMaxCacheAgeDays**. The cache can be force refreshed using **$WarrantyForceRefresh**.
![warranty enable](images/warranty_enable-1024x514.png)
### Step 3





1. If applicable enter the **Dell Client ID** and **Client Secret** values. When you retrieve this info from TechDirect it will be in a format similar to **xxxxxxxxxx (yyyyyyyyy)**. The part before the opening parenthesis is the Client ID, the part inside the parenthesis is the Client Secret. (**Note**: Do not enter the parenthesis themselves in the script)
1. If applicable enter the **Lenovo Client ID** provided to you by your Lenovo account rep.
1. If applicable enter the **HP Client ID** and **Client Secret** provided to you by your HP account rep. (**Note**: HP expires their secrets very frequently so you will have to update these regularly.)
![warranty keys](images/warranty_keys-1024x361.png)
### Step 4





1. In the **Intune** console select **Devices**
1. Select **Scripts and remediations**.
![script and remediations](images/script-and-remediations-896x1024.png)
### Step 5





1. Select R**emediations**.
1. Select **Create**.
![create remediation](images/create-remediation-1024x807.png)
### Step 6





1. Enter a **Name**.
1. Enter a **Description**.
1. Select **Next**.
![](images/Proactive-Remediation-Name-805x1024.png)
### Step 7





1. For the **Detection script file**, browse to and select the **Inventory.ps1** file.
1. Select **Yes** to **run script in 64-bit PowerShell**.
1. Select **Next**.
![](images/Select-Script-696x1024.png)
### Step 8





1. Optionally add **Scope tags**.
1. Select **Next**.
![](images/Scope-Tags-646x1024.png)
### Step 9





1. Select the **devices** from which you want to collect inventory.
1. Adjust the **schedule** per your requirements.
1. Select **Next**.
![](images/Assignment-620x1024.png)
### Step 10





1. Confirm all of the settings are correct.
1. Select **Create**.
![](images/Create-700x1024.png)
