---
creation date: June 23rd 2023
last modified date: June 23rd 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Incident Response]] | [[000 - Global Index]] 
Secondary Categories: [[01 - Red Team]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Lateral Movement]]  
---

- Lateral Movement is the eighth stage in the MITRE ATT&CK framework.
- Adversaries exploit multiple machines within a network to reach their primary objective.
- Lateral Movement techniques involve the movement between hosts within the network.
- This lesson focuses on the following techniques: Remote Services (T1021) and Internal Spearphishing (T1534).

### Internal Remote Services (MITRE Technique T1021)

- Adversaries use legitimate accounts to log into remote services.
- Sub-techniques:
    - Remote Desktop Protocol (RDP)
    - SMB/Windows Admin Shares
    - Distributed Component Object Model
    - SSH
    - VNC
    - Windows Remote Management (WINRM)
- Mitigations:
    - Enforce multi-factor authentication (MFA) on remote services.
    - Routinely audit user accounts with remote server access.
- Detection suggestions:
    - Correlate timeline and logon activity to services.
    - Investigate the activity surrounding logon events and new accounts.

### Internal Spearphishing (MITRE Technique T1534)

- Adversaries send internal spearphishing emails from compromised email accounts.
- These emails are more effective due to their legitimacy and context.
- Mitigation: Scan URLs and attachments passing through the Exchange server.
- Detection suggestions:
    - Scan and analyze URLs and attachments for malicious content.
    - Detect the execution of downloaded payloads during the exploitation stage.

## Key Points and Practices

- Lateral Movement involves moving between hosts within a network.
- Internal Remote Services leverage legitimate accounts for remote access.
- Internal Spearphishing involves sending spearphishing emails from compromised accounts.
- Mitigate lateral movement by enforcing MFA and auditing remote server access.
- Detect lateral movement through timeline analysis and correlation of logon activity.
- Scan and analyze URLs and attachments to detect internal spearphishing attempts.

## References

- [MITRE ATT&CK Framework](https://attack.mitre.org/)


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 23rd 2023 (10:40 am) 
Last Modified Date: June 23rd 2023 (10:40 am)
