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

# [[03 - Impact]]  
---

- Impact is the twelfth stage in the MITRE ATT&CK framework.
- It involves actions taken by adversaries to disrupt availability or compromise integrity by manipulating business and operational processes, such as tampering with or destroying data.
- This lesson focuses on the following techniques: Account Access Removal (T1531), Defacement (T1491), and Data Encrypted for Impact (T1486).

### Account Access Removal (MITRE Technique T1531)

- Adversaries may remove access to user accounts as an anti-forensic technique or to disrupt business operations.
- Actions include deleting accounts, locking accounts, and changing passwords.
- Detection methods:
    - Monitor Windows event IDs related to account changes.
    - Analyze event volume and compare to baseline activity.

### Defacement (MITRE Technique T1491)

- Adversaries modify content internally or externally to disrupt operations and convey messages.
- Reasons for defacement include promoting socially or politically-motivated messages, intimidation, or claiming credit for an intrusion.
- Defacement can be internal (e.g., modifying desktop wallpapers) or external (e.g., modifying a company's website).
- Mitigation:
    - Revert to the latest backup to remove defacement.
    - Protect backups from being targeted by adversaries.
- Detection methods:
    - Monitor changes to websites.
    - Use a web application firewall (WAF) to protect web servers.
    - Monitor file changes on web servers.

### Data Encrypted for Impact (MITRE Technique T1486)

- Adversaries encrypt files and data, withholding the decryption key to cause impact.
- Encryption is typically used to demand ransom payments (ransomware).
- Procedure Examples: Ryuk, Shamoon, WannaCry ransomware strains.
- Mitigation:
    - Maintain regular backups and protect them from tampering.
- Detection methods:
    - Monitor specific command-line usages associated with data encryption.
    - Monitor for a large number of file modifications in a short timeframe.

## Key Points and Practices

- Impact refers to actions that disrupt availability or compromise integrity.
- Account access removal includes deleting, locking, or changing user account credentials.
- Defacement involves modifying content internally or externally.
- Data encryption is used to hold data hostage or cripple system functionality.
- Mitigate impact with backups, protect backups, and monitor for changes.
- Detect impact through event monitoring, anomaly detection, and file change analysis.

## References

- [MITRE ATT&CK Framework](https://attack.mitre.org/)


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 23rd 2023 (10:59 am) 
Last Modified Date: June 23rd 2023 (10:59 am)
