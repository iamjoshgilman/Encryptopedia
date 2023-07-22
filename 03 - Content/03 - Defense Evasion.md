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

# [[03 - Defense Evasion]]  
---

- Defense Evasion is the fifth stage in the MITRE ATT&CK framework.
- Adversaries employ techniques to evade or disable security defenses and hinder detection and analysis.
- Currently, there are 38 top-level techniques under Defense Evasion.
- This lesson focuses on two techniques: Impair Defenses (T1562) and Indicator Removal on Host (T1070).

### Impair Defenses (MITRE Technique T1562)

- Adversaries disrupt the normal operation of security tools to evade detection.
- Sub-techniques of Impair Defenses:
    - Disable or Modify Tools
    - Disable Windows Event Logging
    - HISTCONTROL
    - Disable or Modify System Firewall
    - Indicator Blocking
    - Disable or Modify Cloud Firewall
- Detection suggestions:
    - Enable logging for processes and command-line activity.
    - Adapt detection based on registry keys or core files created by security tools.
    - Monitor for processes being killed.

### Indicator Removal on Host (MITRE Technique T1070)

- Adversaries remove artifacts from a system to cover their tracks and prevent discovery.
- Sub-techniques of Indicator Removal:
    - Clear Windows Event Logs
    - Clear Linux/Unix System Logs
    - Clear Mac OS System Logs
    - Delete or Modify Registry Entries
    - File Deletion
    - Timestomp
- Mitigations:
    - Secure and hide logs to prevent tampering.
    - Minimize the time between log generation and forwarding to an aggregation point (SIEM).
    - Store logs in a secure location to prevent modification or deletion by adversaries.

## Key Points and Practices

- Defense Evasion involves techniques to evade or disable security defenses.
- Impair Defenses disrupts security tools, firewalls, event logging, and more.
- Indicator Removal covers clearing logs, deleting files, modifying registry entries, and timestomping.
- Detect impairments by monitoring process and command-line activity and adapting detection based on registry keys and core files.
- Mitigate indicator removal by securing logs, minimizing log forwarding time, and storing logs securely.

## References

- [MITRE ATT&CK Framework](https://attack.mitre.org/)
- [Sysinternals - Sysmon](https://docs.microsoft.com/en-us/sysinternals/downloads/sysmon)


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 23rd 2023 (10:25 am) 
Last Modified Date: June 23rd 2023 (10:25 am)
