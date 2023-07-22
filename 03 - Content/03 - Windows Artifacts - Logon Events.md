---
creation date: June 20th 2023
last modified date: June 20th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Digital Forensics]] | [[000 - Global Index]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Windows Artifacts - Logon Events]]  
---

This lesson focuses on artifacts that can be gathered from Windows Event Logs related to user account logons and logoffs. These artifacts provide valuable information for digital forensic investigations and incident response. The specific event IDs covered in this lesson include:

- Event ID 4624 (Successful Logon)
- Event ID 4672 (Special Logon)
- Event ID 4625 (Failed Logon)
- Event ID 4634 (Logoff)

## Artifact Location

Windows Event Logs are stored in the following location: `C:\Windows\System32\winevt\Logs`. The logs of interest for this artifact are stored in the \Security folder within this location.

## Artifact Analysis

To analyze these artifacts, the following tools and methods can be used:

1. Windows Event Viewer: The default utility for reading Event logs. It allows the viewing of Windows Event Logs and exporting logs in CSV format.

2. SIEM (Security Information and Event Management): If the organization pulls these specific Event logs into a SIEM platform, it can be used to read and analyze the logs.

3. Microsoft Excel: Event logs exported from the Event Viewer can be opened and analyzed in Microsoft Excel.

|NETLOGON LOG ERROR CODE|DESCRIPTION|
|---|---|
|0xC0000064|The specified user does not exist|
|0xC000006A|The value provided as the current password is not correct|
|0xC000006C|Password policy not met|
|0xC000006D|The attempted logon is invalid due to a bad user name|
|0xC000006E|User account restriction has prevented successful login|
|0xC000006F|The user account has time restrictions and may not be logged onto at this time|
|0xC0000070|The user is restricted and may not log on from the source workstation|
|0xC0000071|The user account’s password has expired|
|0xC0000072|The user account is currently disabled|
|0xC000009A|Insufficient system resources|
|0xC0000193|The user’s account has expired|
|0xC0000224|User must change his password before he logs on the first time|
|0xC0000234|The user account has been automatically locked|


### 1. Event ID 4624 (Successful Logon)

- Event ID 4624 represents successful logons to the system.
- The Logon Type property is crucial, as it provides information about the type of logon (e.g., interactive, network, batch, service, etc.).
- The Logon Type values range from 2 to 9, each indicating a different type of logon.

### 2. Event ID 4672 (Special Logon)

- Event ID 4672 represents special logons, specifically when a user with administrative privileges logs into the system.
- The Subject information provides details about the account logging into the system, including the name, Security ID (SID), and Logon ID.
- The Logon ID can be used to associate a logon with its corresponding logoff event.

### 3. Event ID 4625 (Failed Logon)

- Event ID 4625 represents failed logon attempts.
- Failed Logon events are valuable for incident response as they provide error codes indicating why the logon attempt failed.
- Different error codes correspond to specific scenarios, such as non-existing user, incorrect password, account restrictions, expired accounts, and more.

### 4. Event ID 4634 (Logoff)

- Event ID 4634 represents logoff events, indicating the end of a user session.
- The Logon ID can be used to link logoff events with their corresponding logon or special logon events.
- Logoff events help determine the duration of a user session and provide valuable timestamps.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 20th 2023 (10:54 am) 
Last Modified Date: June 20th 2023 (10:54 am)
