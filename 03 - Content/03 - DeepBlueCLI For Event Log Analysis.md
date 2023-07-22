---
creation date: June 22nd 2023
last modified date: June 22nd 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Incident Response]] | [[000 - Global Index]] 
Secondary Categories: [[02 - DeepBlueCLI]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - DeepBlueCLI For Event Log Analysis]]  
---

DeepBlueCLI is a PowerShell script that was created by SANS to aid with the investigation and triage of Windows Event logs. This tool can be provided with exported .evtx log files, or can be run on a live system to analyze the local log files.

This tool is able to identify a range of attacks (provided we have the relevant Windows Event logs, or Sysmon logs) such as:

- User creation
- Users being added to groups
- Password guessing
- Password spraying
- Bloodhound offensive tool usage
- Obfuscated commands
- PowerShell used to download remote files
- Suspicious service creation
- Mimikatz used to dump LSASS.exe for credential collection


---

# Using DeepBlueCLI

In our Downloads folder, we have the DeepBlueCLI folder downloaded from Github and 2 log files that we're going to analyze.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/files/470a8fc4d722ac80ca083301834ead5c008f3c326ca3446c0f4cd74f9d83b16eaed9eff2d2fb349d976bd54ce9b8.PNG)

Inside the folder are all the files related to the tool, including the core PowerShell script “DeepBlue” (DeepBlue.ps1).

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/files/583ae113be540e8fda803013dfdf8be017fcdcdebdec2f486c596338e9e3926fa1954d94df5dd29d19568d00722c.PNG)

To run the tool we're going to open an administrator-level PowerShell window by searching for ‘PowerShell’, right-clicking the result, and selecting ‘Open as Administrator’. We then need to navigate to the Downloads folder of our user, and into the DeepBlue folder.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/files/e55072a72cb5f30b00297b57637eb2ab4aaaa687ef06fade63262b26fb73faad3ae4eb54e46cf0f7a73ee94a5c03.PNG)

When running it for the first time, we notice there is an error, but this is expected. As the PowerShell script is not digitally signed, Windows is blocking it from executing to try and protect us.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/files/f514098291467832e865e57414c77fe8a8bbf6d8dacc786f8af2c69475b505d01140ba848876a50cb3d27e0fce81.PNG)

We can disable this by changing the Execution Policy applied to our user. The command to achieve this is **`Set-ExecutionPolicy Bypass -Scope CurrentUser`**.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/files/230efefa16c3b48358f48112699fb1172a5c67d3f00717a59e5bdd217ef87fd0181af0af06e2186a26ce564af27c.PNG)

Let's run the command again to process Log1.evtx:  
**`./DeepBlue.ps1 ../Log1.evtx`**  
(Execute PowerShell script, go up a directory into Downloads, target Log1.evtx)

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/files/ffdff52ab77d7ececb43c2db99b63eec94c5396c8fd3cd51042ff54685165a1b1538482ee4629fa235658548336e.PNG)

In the above screenshot we can see that within this log file, on 4/30/2019 DeepBlue has detected a password spray attack against local user accounts. We get a lot of useful information from this output, such as:

- A list of targetted user account names
- Count of user accounts targeted
- The username of the account conducting the activity
- The hostname of the system conducting the activity
- The Event ID that shows this activity

Let's go through another example using Log2.evtx. We'll run the same command as before, but change the target file.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/files/64e52ea4282275693b371cd9276485b4ac74de64d4ebfeb207c41087e475bc712cefad6d69c8aaeed96230d84b38.PNG)

In the above screenshot we can see what DeepBlue has recognised as ‘Suspicious Command Line’ activity which includes a number of long encoded PowerShell commands that have been executed on this system. Based on these results we can further analyze the commands presented and understand what they actually do.

Up until now we have been targeting the tool at specific .evtx files. If we are trying to analyze the system we are currently on, we can tell DeepBlue to point at the local system's Security or System event logs directly. The process is the same as above, however we will use the following commands:

**`./DeepBlue.ps1 -log security`**

**`./DeepBlue.ps1 -log system`**


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 22nd 2023 (12:20 pm) 
Last Modified Date: June 22nd 2023 (12:20 pm)
