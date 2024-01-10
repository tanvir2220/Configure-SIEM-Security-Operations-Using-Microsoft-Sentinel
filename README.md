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

<img src="https://i.ibb.co/jkKLjYn/9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
