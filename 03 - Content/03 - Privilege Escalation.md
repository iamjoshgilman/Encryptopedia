---
creation date: June 23rd 2023
last modified date: June 23rd 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Incident Response]] | [[000 - Global Index]]] 
Secondary Categories: [[01 - Red Team]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Privilege Escalation]]  
---

- Privilege Escalation is the fourth stage in the MITRE ATT&CK framework.
- Adversaries attempt to gain higher privileges, such as moving from a standard user to an administrator or from an admin to a domain admin.
- Currently, there are 12 top-level techniques for privilege escalation.
- This lesson focuses on two techniques: Valid Accounts and Exploitation for Privilege Escalation.

### Valid Accounts (MITRE Technique T1078)

- Adversaries can immediately gain access to privileged accounts by obtaining credentials through methods like phishing with credential harvesters.
- Mitigations for preventing unauthorized access to privileged accounts:
    - Avoid using hardcoded credentials in applications or websites.
    - Change default credentials on applications/devices to prevent the use of known username/password pairs.
    - Conduct routine audits to identify accounts with excessive permissions and monitor permission changes.

### Exploitation for Privilege Escalation (MITRE Technique T1068)

- Adversaries exploit vulnerabilities in software or operating system functions to escalate privileges.
- Exploiting vulnerabilities can lead to executing code with higher privileges or gaining SYSTEM/root permissions.
- Examples of vulnerabilities used by advanced threats include CVE-2017-0263 and CVE-2016-7255.
- Mitigations for privilege escalation exploits:
    - Patch vulnerabilities to remove the risk.
    - Develop threat intelligence capabilities to track actively exploited CVEs.
    - Enable built-in security tools like Exploit Guard on Windows hosts.
    - Enforce deep logging with tools like Sysmon and use endpoint detection and response (EDR) solutions for detecting process modifications and exploitation activity.

## Key Points and Practices

- Privilege Escalation involves gaining higher privileges, such as admin or domain admin.
- Prevent unauthorized access to privileged accounts by avoiding hardcoded credentials, changing default credentials, and conducting routine audits.
- Mitigate privilege escalation exploits by patching vulnerabilities, tracking actively exploited CVEs, enabling security tools, and implementing deep logging and EDR solutions.
- Monitor process modifications and use threat intelligence for situational awareness.

## References

- [MITRE ATT&CK Framework](https://attack.mitre.org/)
- [Sysinternals - Sysmon](https://docs.microsoft.com/en-us/sysinternals/downloads/sysmon)


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 23rd 2023 (10:13 am) 
Last Modified Date: June 23rd 2023 (10:13 am)
