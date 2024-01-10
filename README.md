<h1>Configure SIEM Security Operations Using Microsoft Sentinel</h1>

<h2>Overview</h2>
Project consists of a configuring a Security information and event management (SIEM) for Security Operations using Microsoft Sentinel, and involves provisioning a Log Analytics workspace and configuring the Microsoft Sentinel options. 
<br />


<h2>Use Case</h2>
You're a Security Operations Analyst working at a company that is currently evaluating the existing security posture of their corporate environment. They need your help in setting up a security information and event management (SIEM) solution to help identify future and ongoing cyber-attacks. To accomplish the goal, they're implementing Microsoft Sentinel. You're responsible for setting up and validating the Microsoft Sentinel environment.

<br />

<h2>To-Do </h2>
To accomplish this, we need to perform following:

1.	Configure Our Microsoft Sentinel Environment
2.	Connect Data to Microsoft Sentinel Using Data Connectors
3.	Configure Microsoft Sentinel Data Collection Rules
4.	Simulated Attack to Validate Analytic and Automation Rules

<h2>Phase 1: Configure Our Microsoft Sentinel Environment</h2>

Task 1 - Create A Log Analytics Workspace
1.	In the Azure portal, search for and select Microsoft Sentinel.
2.	Select + Create.
3.	Select Create a new workspace.
4.	Select RG2 as the Resource Group
5.	Enter a valid name for the Log Analytics workspace
6.	Select West US as the region for the workspace.
7.	Select Review + create to validate the new workspace.
8.	Select Create to deploy the workspace.

<p align="center">

<img src="https://i.ibb.co/jkKLjYn/9.png" height="80%" width="80%" alt="Configure SIEM Security Operations Using Microsoft Sentinel"/>
<br />
<br />

Task 2 - Deploy Microsoft Sentinel To A Workspace

1.	When the workspace deployment completes, select Refresh to display the new workspace.
2.	Select the workspace you want to add Sentinel to (created in Task 1).
3.	Select Add.

Task 3 - Assign A Microsoft Sentinel Role To A User
1.	Go to the Resource group RG2
2.	Select Access control (IAM).
3.	Select Add and Add role assignment.
4.	In the search bar, search for and select the Microsoft Sentinel Contributor role.
5.	Select Next.
6.	Select the option User, group, or service principal.
7.	Select + Select members.
8.	Search for the Operator1 assigned in your lab instructions
9.	Select the user icon.
10.	Select Select.
11.	Select “Review + assign”.
12.	Select “Review + assign”.

Task 4 - Configure Data Retention
1.	Go to the Log Analytics workspace created in Task 1 step 5.
2.	Select Usage and estimated costs.
3.	Select Data retention.
4.	Change data retention period to 180 days.
5.	Select OK.

<p align="center">

<img src="https://i.ibb.co/vzJSxFZ/12.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<h2>Phase 2: Connect Data to Microsoft Sentinel Using Data Connectors</h2>

Task 1 - Deploy A Microsoft Sentinel Content Hub Solution
1.	In Microsoft Sentinel, go to the Content management menu section and select Content Hub
2.	Search for and select Windows Security Events
3.	Select the link for View details
4.	Select Windows Security Events plan, and select Create
5.	Select the RG2 resource group that includes the Microsoft Sentinel workspace, and select the Workspace.
6.	Select Next to the Data Connectors tab (solution will deploy 2 data connectors)
7.	Select Next to the Workbooks tab (solution installs workbooks)
8.	Select Next to the Analytics tab (solutions installs analytics rules)
9.	Select Next to the Hunting queries tab (solution instals hunting queries)
10.	Select Review + create
11.	Select Create
12.	Repeat these steps for the Azure Activity and the Microsoft Defender for Cloud solutions.

Task 2 - Set Up The Data Connector For Azure Activity
1.	In Microsoft Sentinel, go to the Content management menu section and select Content Hub.
2.	In the Content hub, filter Status for Installed solutions.
3.	Select the Azure Activity solution and select Manage.
4.	Select the Azure Activity Data connector and select Open connector page.
5.	In the Configuration area under the Instructions tab, scroll down to 2. Connect your subscriptions... and select Launch Azure Policy Assignment Wizard>.
6.	In the Basics tab, select the ellipsis button (…) under Scope and select your subscription from the drop-down list and click Select.
7.	Select the Parameters tab, choose your workspace from the Primary Log Analytics workspace drop-down list.
8.	Select the Remediation tab and select the Create a remediation task checkbox.
9.	Select the Review + Create button to review the configuration.
10.	Select Create to finish.

<p align="center">

<img src="https://i.ibb.co/pj2GKmF/21.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

Task 3 - Set Up The Defender For Cloud Data Connector
1.	In Microsoft Sentinel, go to the Content management menu section and select Content Hub.
2.	In the Content hub, filter Status for Installed solutions.
3.	Select the Microsoft Defender for Cloud solution and select Manage.
4.	Select the Subscription-based Microsoft Defender for Cloud (Legacy) Data connector and select Open connector page
5.	In the Configuration area under the Instructions tab, scroll down to your subscription and move the slider in the Status column to Connected.
6.	Make sure Bi-directional sync is Enabled.

<p align="center">

<img src="https://i.ibb.co/pxnTzVQ/22.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

Task 4 - Create An Analytics Rule
1.	In Microsoft Sentinel, go to the Configuration menu section and select Analytics.
2.	In the Rule templates tab, search for Suspicious number of resource creation or deployment activities.
3.	Select the Suspicious number of resource creation or deployment activities and select Create rule.
4.	Leave the defaults on the General tab and select Next: Set rule logic >.
5.	Leave the default Rule query and configure Query scheduling using the table:
6.	Select Next: Incident settings >.
7.	Leave the defaults and select Next: Automated response >.
8.	Leave the defaults and select Next: Review and create >.
9.	Select Save.

Task 5 - Ensure That The Azure Activity Workbook Is Available In My Workbooks
1.	In Microsoft Sentinel, go to the Content management menu section and select Content Hub.
2.	In the Content hub, filter Status for Installed solutions.
3.	Select the Azure Activity solution and select Manage.
4.	Select the Azure Activity workbook checkbox, and then select Configuration.
5.	Select the Azure Activity workbook and select Save.
6.	Choose the Azure Region for your Microsoft Sentinel workspace.




<h2>Phase 3: Configure Microsoft Sentinel Data Collection Rules</h2>

Task 1 - Configure Data Collection Rules (DCRs) In Microsoft Sentinel
1.	In Microsoft Sentinel, go to the Configuration menu section and select Data connectors
2.	Search for and select Windows Security Events via AMA
3.	Select Open connector page
4.	In the Configuration area, select +Create data collection rule
5.	On the Basics tab enter a Rule Name
6.	On the Resources tab expand your subscription and the RG1 resource group in the Scope column
7.	Select VM1, and then select Next: Collect >
8.	On the Collect tab leave the default of All Security Events
9.	Select Next: Review + create >, then select Create

<p align="center">

<img src="https://i.ibb.co/2FwCmjD/26.png" height="80%" width="80%" alt="Configure SIEM Security Operations Using Microsoft Sentinel"/>
<br />
<br />

Task 2 - Create A Near Real-Time (NRT) Query Detection
1.	In Microsoft Sentinel, go to the Configuration menu section and select Analytics
2.	Select + Create, and NRT query rule (Preview)
3.	Enter a Name for the rule and select Privilege Escalation from Tactics and techniques.
4.	Select Next: Set rule logic >
5.	Enter the KQL query into the Rule queryform
6.	Select Next: Incident settings >, and select Next: Automated response >
7.	Select Next: Review + Create
8.	When validation is complete select Save

<p align="center">

<img src="https://i.ibb.co/N2KxwpR/27.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

Task 3 - Configure Automation In Microsoft Sentinel
1.	In Microsoft Sentinel, go to the Configuration menu section and select Automation
2.	Select + Create, and Automation rule
3.	Enter an Automation rule name, and select Assign owner from Actions
4.	Assign Operator1 as the owner.
5.	Select Apply

<p align="center">

<img src="https://i.ibb.co/1nZMPHm/29.png" height="80%" width="80%" alt="Configure SIEM Security Operations Using Microsoft Sentinel"/>
<br />
<br />

<h2>Phase 4: Simulated Attack to Validate Analytic and Automation Rules</h2>

Task 1 - Perform A Simulated Privilege Escalation Attack
1.	Locate and select the vm1 virtual machine in Azure and scroll down the menu items to Operations and select Run command
2.	On the Run command pane, select RunPowerShellScript
3.	Copy the commands below to simulate the creation of an Admin account into the PowerShell Script form and select Run
4.	In the Output window you should see The command completed successfully three times

Task 2 - Verify An Incident Is Created From The Simulated Attack
1.	In Microsoft Sentinel, go to the Threat management menu section and select Incidents
2.	You should see an incident that matches the Severity and Title you configured in the NRT rule you created
3.	Select the Incident and the detail pane opens
4.	The Owner assignment should be Operator1, created from the Automation rule, and the Tactics and techniques should be Privilege Escalation (from the NRT rule)
5.	Select View full details to see all the Incident management capabilities and Incident actions



<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
