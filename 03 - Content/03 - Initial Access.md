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

# [[03 - Initial Access]]  
---

- The first stage in the MITRE ATT&CK framework is Initial Access (TA0001).
- It focuses on techniques used by adversaries to gain their initial foothold in a network.
- There are currently 9 techniques identified for Initial Access:
    1. Drive-by Compromise
    2. Exploit public-facing application
    3. External remote services
    4. Hardware additions
    5. Phishing
    6. Replication through removable media
    7. Supply chain compromise
    8. Trusted relationship
    9. Valid accounts

### Phishing (MITRE Technique T1566)

- Phishing is the most common initial access method.
- Phishing has three sub-techniques.
- Mitigations for reducing the risk from phishing emails:
    - User awareness training
    - Email filtering and authentication
    - Strong passwords and multi-factor authentication (MFA)
    - Security patches and updates
    - Web content filtering

### External Remote Services (MITRE Technique T1133)

- External remote services include VPNs, Remote Desktop Protocol (RDP), Secure Shell (SSH), Citrix, etc.
- Adversaries may use valid accounts obtained through techniques like phishing (T1566).
- Mitigations for reducing the risk from internet-facing remote services:
    - Disable unnecessary services
    - Implement two-factor authentication (2FA)
    - Regularly review and update access controls and permissions

### Removable Media (MITRE Technique T1091)

- Removable media, such as USB pens or Rubber Duckies, can be used to transport malware.
- This technique can be used to attack air-gapped systems that are not connected to other networks.
- Mitigations for protecting against removable media attacks:
    - Disable AutoRun feature
    - Implement policies against using USBs
    - Lock down systems to prevent USB registration

## Key Points and Practices

- Phishing is the most common initial access method.
- Mitigate phishing risks through user awareness training, email filtering, strong passwords with MFA, and security patching.
- External remote services can be exploited, necessitating the use of strong access controls, disabling unnecessary services, and implementing 2FA.
- Removable media can transport malware, and precautions like disabling AutoRun and restricting USB usage should be taken.

## References

- [MITRE ATT&CK Framework](https://attack.mitre.org/)
- [Tech Republic: How to monitor USB device usage with Windows Event logs](https://www.techrepublic.com/article/how-to-monitor-usb-device-usage-with-windows-event-logs/)


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 23rd 2023 (10:33 am) 
Last Modified Date: June 23rd 2023 (10:33 am)
