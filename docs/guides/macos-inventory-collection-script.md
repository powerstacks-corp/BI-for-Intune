---
title: "macOS Inventory Collection Script"
---
# macOS Inventory Script
Many customers have requested the ability to report on things that are either not collected or not accurately collected by Intune. In an effort to fill these gaps in we have implemented a custom solution to collect some of the most commonly requested items. It is highly likely that new features will be added to this script just as they have been added to its Windows counterpart. Keep an eye out for updates in upcoming releases. Currently the script collects:

1. Software installed on macOS devices.

This data is collected via a bash script, sent to a Log Analytics workspace, and then pulled into Power BI.

We created this script at the request of a customer. It collects the installed software from macOS and sends that to Log Analytics just like our PowerShell script does on Windows. You can deploy the script as a Shell script from Intune. Ideally the script should be run once per day on each device. This way any changes to the device get captured.

Below is the inventory script for macOS:
![github mark](images/github-mark-80x80.png)

### Step 1





1. Paste the **script** code into your favorite **script editor**.
1. On the line starting with **CustomerId =**enter your Log Analytics **Workspace ID** between the quotes.
1. On the line starting with **SharedKey =**enter your Log Analytics Workspace **Primary Key** between the quotes.
1. Save the edited script.
![intune macos script](images/intune_macos_script-1024x320.png)
### Step 2





1. Create a **Shell Script** in Intune.
1. Run script as signed-in user: **No**.
1. Script frequency: **Every 1 day**.
![intune shell script](images/intune_shell_script-907x1024.png)
