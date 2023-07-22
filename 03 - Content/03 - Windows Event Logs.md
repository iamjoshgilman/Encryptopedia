---
creation date: June 20th 2023
last modified date: June 20th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Security Information and Event Management]] | [[000 - Global Index]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Windows Event Logs]]  
---

“Windows Event logs” or “Event Logs” are files in binary format (with .evtx extension) stored locally in the Windows directory of a computer with that operating system:

### Windows 2000 to WinXP/Windows Server 2003:
    `%WinDir%\system32\Config*.evt`

### Windows Server 2008 to 2019, and Windows Vista to Win10:  
    `%WinDir%\system32\WinEVT\Logs*.evtx`

- Event Logs record various events that occur on the system, such as hardware events, user logins, program execution, and installations.
- These logs help system administrators track system activities, diagnose issues, and anticipate potential problems.
- Event Logs are categorized into different types, including:
	- **Application:** Events logged by an application (Execution, Deployment error, etc.)
	- **System:** Events logged by the Operating System (Device loading, startup errors, etc.)
	- **Security:** Events that are relevant to the security of the system (Logins and logouts, file deletion, granting of administration permissions, etc.)
	- **Directory Service:** This is a record available only to Domain Controllers, it stores Active Directory (AD) events.
	- **DNS Server:** It is a record available only to DNS servers; logs of DNS service are stored.
	- **File Replication Service:** Is a record available only for Domain Controllers, it stores Domain Controller Replication events.

## Security Event Logs
- Security Event Logs store events related to Windows Security audit policies.
- These policies help in monitoring and evaluating system security incidents.
- Some elements covered by security event logs include:
	 - Account logon events (valid and invalid sign-ons and sign-offs).
	 - Account management (creation, modification, interaction, and deletion of user accounts).
	 - Privilege use.
	 - Resource usage (file creation, modification, interaction, and deletion).

![[Pasted image 20230620210432.png]]

## Event Viewer
- The Event Viewer is a program available on Windows 10 for viewing Windows Events.
- It provides access to different types of logs, with a focus on security-related events.
	- When opening Event Viewer, a summary of administrative events is displayed, showing an overview of event types in the past 7 days.
- The Windows Logs section in the left-hand pane is divided into five sections:
	 - Application
	 - Security
	 - Setup
	 - System
	 - Forwarded Events
- By clicking on the Security section, the middle pane displays Security Events.
- Clicking on a specific event allows viewing additional information, such as event details, time of logging, generating computer, and audit status.

## Logon Events
- Logon events are important to monitor for security teams.
- Unusual logon activity, such as logins at odd hours, can indicate account compromise or insider threats.
- Accounts with administrative privileges should be closely monitored to detect compromised accounts or insider misuse.
- Event IDs 4624 (Logon) and 4672 (Special Logon) are commonly observed in logon-related events.

## Custom Views
- Event Viewer allows the creation of custom search profiles called "Custom Views" to retrieve specific event IDs and filter out unnecessary noise.
- Custom Views can be created based on various properties:
	- Logged: Specify the date range for retrieving logs.
	- Event Level: Select event levels for filtering.
	- By Log: Choose specific logs for filtering.
	- By Source: Filter logs based on specific sources.
	- Includes/Excludes Event IDs: Define the event IDs to capture.
	- Keywords: Search for specific keywords within events.
	- User and Computers: Focus on specific users or systems.
- Custom Views can be useful for monitoring specific activities, such as user logins and logoffs.

## **Custom Views Example: Login Monitoring**

Just so that you fully understand how Custom Views can be used, let’s go through an example where we want to monitor employee login and logoff times. The following are events we need to consider for our View:

- **User Logon Successful –** 4624
- **Special Logon –** 4672
- **User Initiated Logoff –** 4647
- **User Logoff –** 4634

In the below screenshot you can see the settings we have set. We want to view all events associated with users logging in and out, over the past 24 hours.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/73c25d8717f1645071b7e1cf7a48e2361031b41d8e716b3c9be1dba69c2993825bf178ef827effbd3cf2c498dc31.png)

Next we’ll be prompted to provide a name, description, and where we want to save the View.

  
![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/4fffaa5be1d6d8e6dbf8127e26e99a5b42d9d144caa604d165328dd1a938941bcbdd3770286734bd0ed9881e72f5.png)

Now the filter will show us only the event IDs we have defined. It’s worked! We can now see events related to user accounts logging in and out!

  
![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/bde7b3cdbec0d4e79ac9e1db069b07123ace74a4290f6d425948006da13cef3bdd9e994ac80f0f57514ab4a4f492.png)


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 20th 2023 (08:22 pm) 
Last Modified Date: June 20th 2023 (08:22 pm)
