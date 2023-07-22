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

# [[03 - Persistence]]  
---

- Persistence is the third stage in the MITRE ATT&CK framework.
- Adversaries aim to maintain their foothold and regain access to compromised hosts using multiple methods.
- Currently, there are 18 high-level techniques for persistence.
- This lesson focuses on two techniques: Boot or Logon Autostart Execution and External Remote Services.

### Boot or Logon Autostart Execution (MITRE Technique T1547)

- Adversaries achieve persistence by adding a program to a start-up folder or referencing it with a registry run key.
- Mitigation is challenging as legitimate programs can also be assigned to execute during system startup.
- Detection of malicious executables at system launch can be done through:
    - Auditing the Windows Registry for suspicious entries.
    - Using tools like Sysinternals Autoruns to identify autostart configurations.
    - Monitoring autorun behavior to aid in investigations.

### External Remote Services (MITRE Technique T1133)

- Persistence can be maintained by re-connecting to a compromised system through internet-facing remote services like SSH, RDP, or VPNs.
- Valid credentials collected by adversaries are used to maintain access.
- Mitigations for persistence attempts using external remote services:
    - Disable or block unnecessary remote services open to the internet.
    - Limit remote service listening to connections from inside the network.
    - Deploy multi-factor authentication (MFA) to prevent password spraying or reuse.
    - Use VLANs and firewalls to segment and isolate the network.
- Detection can be done by collecting logs of login attempts, successes, and failures.
- Create rules to detect activity outside of standard office hours, which is likely malicious.

## Key Points and Practices

- Persistence involves maintaining access and regaining control of compromised systems.
- Mitigate persistence by monitoring autostart configurations, auditing the Windows Registry, and using tools like Sysinternals Autoruns.
- Secure external remote services by disabling/blocking unnecessary ones, limiting listening to internal connections, deploying MFA, and using VLANs and firewalls.
- Detect persistence attempts through log analysis, monitoring login activity, and setting rules for detecting abnormal activity.

## References

- [MITRE ATT&CK Framework](https://attack.mitre.org/)
- [Sysinternals - Autoruns](https://docs.microsoft.com/en-us/sysinternals/downloads/autoruns)


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 23rd 2023 (10:04 am) 
Last Modified Date: June 23rd 2023 (10:04 am)
