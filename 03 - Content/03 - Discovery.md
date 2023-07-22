---
creation date: June 23rd 2023
last modified date: June 23rd 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Incident Response]] | [[000 - Global Index]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Discovery]]  
---

- Discovery is the seventh stage in the MITRE ATT&CK framework.
- Adversaries collect information about the network and other systems.
- Techniques include account discovery, network service scanning, and file and directory discovery.
- This lesson focuses on the following techniques: Account Discovery (T1087), Network Service Scanning (T1046), and File and Directory Discovery (T1083).

### Account Discovery (MITRE Technique T1087)

- Adversaries identify existing accounts for privilege escalation and lateral movement.
- Sub-techniques:
    - Local Accounts: Listing local accounts on the operating system.
    - Domain Accounts: Listing domain accounts in a Windows domain environment.
    - Email Accounts: Obtaining a list of email addresses and accounts.
    - Cloud Accounts: Identifying cloud accounts configured for an organization.
- Mitigation:
    - Disable the registry key to prevent the enumeration of administrator accounts.
- Detection suggestions:
    - Monitor for activity related to account listing commands and email address scraping.
    - Implement Group Policy Objects to disable the registry key across a domain.

### Network Service Scanning (MITRE Technique T1046)

- Adversaries scan the network to identify other systems and their running services.
- Mitigations:
    - Turn off unnecessary services that don't require remote connections.
    - Use Network Intrusion Prevention Systems (IPS) or Detection Systems (IDS).
    - Segregate networks to limit an attacker's lateral movement.
- Detection suggestions:
    - Monitor for port scanning activities and network traffic patterns.
    - Deploy IPS or IDS to inspect network traffic for suspicious or malicious patterns.

### File and Directory Discovery (MITRE Technique T1083)

- Adversaries search for valuable files on compromised systems.
- Mitigation: No specific mitigations listed.
- Detection suggestions:
    - Monitor command-level activities related to file system interaction.
    - Monitor API calls and processes rapidly checking the file system for files.

## Key Points and Practices

- Discovery involves collecting information about the network and systems.
- Account Discovery focuses on identifying local, domain, email, and cloud accounts.
- Network Service Scanning involves scanning the network for systems and their services.
- File and Directory Discovery involves searching for valuable files on compromised systems.
- Mitigate discovery by disabling unnecessary services, using IPS/IDS, and segregating networks.
- Detect discovery activities by monitoring account listing commands, network scanning, and file system interactions.

## References

- [MITRE ATT&CK Framework](https://attack.mitre.org/)


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 23rd 2023 (10:34 am) 
Last Modified Date: June 23rd 2023 (10:34 am)
