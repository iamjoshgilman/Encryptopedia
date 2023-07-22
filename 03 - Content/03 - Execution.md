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

# [[03 - Execution]]  
---

- Execution is the second stage in the MITRE ATT&CK framework (TA0002).
- It involves techniques used by adversaries to execute malicious code for various purposes.
- Currently, there are 10 top-level techniques under Execution.
- This lesson focuses on two techniques: Windows Management Instrumentation and User Execution.

### Windows Management Instrumentation (MITRE Technique T1047)

- Windows Management Instrumentation (WMI) is an administration feature in Windows that allows the management of devices and applications in a network.
- WMI can be used for lateral movement and discovery.
- Mitigations for preventing malicious abuse of WMI:
    - Properly manage privileged accounts and limit their issuance to individuals who require them (principle of least privilege).
    - Be restrictive regarding who can use WMI to limit potential abuse if compromised.
- Organizations should monitor WMI usage, which can be done using Sysmon (System Monitoring) from Sysinternals.

### User Execution (MITRE Technique T1204)

- User Execution involves a user interacting with a malicious URL (sub-technique 1) or a malicious file (sub-technique 2).
- It is closely tied with Phishing as an Initial Access technique.
- Mitigations for User Execution:
    - Application whitelisting to prevent unapproved executables from running.
    - Network Intrusion Prevention Systems (NIPS) to identify and block requests to malicious web resources.
    - User awareness training to educate users on spotting phishing emails and not interacting with them.
- Detection recommendations for User Execution:
    - Monitor commands entered into CMD.exe and PowerShell.exe.
    - Monitor applications used to compress and extract payloads (e.g., 7Zip, WinRar).
    - Use up-to-date commercial antivirus solutions and consider an Endpoint Detection and Response (EDR) solution.

## Key Points and Practices

- Windows Management Instrumentation (WMI) can be abused for lateral movement and discovery.
- Mitigate WMI risks by managing privileged accounts and monitoring WMI usage.
- User Execution often involves phishing and interacting with malicious URLs or files.
- Mitigate User Execution risks through application whitelisting, NIPS, and user awareness training.
- Detect User Execution by monitoring command execution and using up-to-date antivirus and EDR solutions.

## References

- [MITRE ATT&CK Framework](https://attack.mitre.org/)
- [Sysinternals - Sysmon](https://docs.microsoft.com/en-us/sysinternals/downloads/sysmon)


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 23rd 2023 (10:42 am) 
Last Modified Date: June 23rd 2023 (10:42 am)
