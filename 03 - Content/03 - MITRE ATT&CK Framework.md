---
creation date: May 31st 2023
last modified date: May 31st 2023
aliases: []
tags: #📕
---

Primary Categories: [[01 - Administration]] 
Search Tag: #📕  

# [[03 - MITRE ATT&CK Framework]]  
___

1. Initial Access
2. Execution
3. Persistence
4. Privilege Escalation
5. Defense Evasion
6. Credential Access
7. Discovery
8. Lateral Movement
9. Collection
10. Command and Control (C2)
11. Exfiltration
12. Impact

## Initial Access
* Initial access is the first phase where the attacker attempts to gain entry to the target network or system.

|Common Initial Access Techniques| Description|
|----|----|
|Phishing|Attackers send fraudulent emails to trick recipients into revealing sensitive information or installing malware.|
|Drive-by Compromise|Exploiting vulnerabilities in a web browser to execute a malicious script.|

## Execution
* This phase involves the attacker executing a malicious payload on a compromised system.

|Common Execution Techniques| Description|
|----|----|
|Scripting|Attackers use scripts (like PowerShell) to automate their tasks and avoid detection.|
|User Execution|Tricking users into running a malicious program.|

## Persistence
* Attackers establish a persistent presence in the victim's network to survive reboot and other interruptions.

|Common Persistence Techniques| Description|
|----|----|
|Registry Modification|Changes to the registry to start the malware during system boot.|
|Scheduled Task/Job|Scheduling tasks or jobs that execute the malicious program at regular intervals.|

## Privilege Escalation
* Attackers seek to gain higher-level permissions on the system.

|Common Privilege Escalation Techniques| Description|
|----|----|
|Bypassing User Account Control|Tricking the Windows User Account Control (UAC) to grant admin privileges.|
|Exploitation for Privilege Escalation|Exploiting a software vulnerability to gain elevated access.|

## Defense Evasion
* Techniques used to avoid detection.

|Common Defense Evasion Techniques| Description|
|----|----|
|Deobfuscate/Decode Files or Information|Attackers often obfuscate their code to evade detection.|
|Disabling Security Tools|Disabling firewalls, antivirus, or other security tools on the system.|

## Credential Access
* Attackers steal account names and passwords.

|Common Credential Access Techniques| Description|
|----|----|
|Input Capture|Using keyloggers or similar tools to capture user inputs.|
|Credential Dumping|Attacker obtains user credentials by reading system memory.|

## Discovery
* Attackers gather information about the system and internal network.

|Common Discovery Techniques| Description|
|----|----|
|System Network Configuration Discovery|Learning about the network configuration.|
|System Information Discovery|Collecting system details like OS, hostname, etc.|

## Lateral Movement
* Moving through a network, accessing other systems.

|Common Lateral Movement Techniques| Description|
|----|----|
|Remote Desktop Protocol (RDP)|Using RDP to move between systems in a network.|
|SSH Hijacking|Hijacking an existing SSH session to gain control.|

## Collection
* Gathering valuable data.

|Common Collection Techniques| Description|
|----|----|
|Data Staged|Collecting data in a central location before exfiltration.|
|Data from Information Repositories|Extracting data from databases or other repositories.|

## Command and Control
* Attacker controls compromised systems via a network connection.

|Common Command and Control Techniques| Description|
|----|----|
|Commonly Used Port|Using commonly used network ports to hide malicious traffic.|
|Web Service|Using a web service for C2, often to blend in with normal traffic.|

## Exfiltration
* Extracting the valuable data out of the network.

|Common Exfiltration Techniques| Description|
|----|----|
|Data Compressed|Compressing data to facilitate transfer.|
|Scheduled Transfer|Setting up automated data transfer out of the network.| 

## Impact
* The objective of the attack, typically resulting in disruption to systems and data.

|Common Impact Techniques| Description|
|----|----|
|Data Destruction|Destroying or deleting data from the victim's system.|
|Inhibit System Recovery|Disabling system recovery features or backup systems to make remediation more difficult.|
|Denial of Service|Flooding a network or system with traffic or requests to render it inaccessible to its intended users.|






___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: May 31st 2023 (02:06 pm) 
Last Modified Date: May 31st 2023 (02:06 pm)
