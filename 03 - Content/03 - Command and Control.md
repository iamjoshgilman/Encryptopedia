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

# [[03 - Command and Control]]  
---

- Command and Control is the eleventh stage in the MITRE ATT&CK framework.
- Adversaries use various methods to communicate with compromised systems on a target network.
- Command and Control techniques aim to blend malicious traffic with normal traffic to avoid detection.
- This lesson focuses on the following techniques: Application Layer Protocol (T1071), Web Service (T1102), and Non-standard Port (T1571).

### Application Layer Protocol (MITRE Technique T1071)

- Adversaries use application layer protocols to avoid detection in command and control (C2) communications.
- Protocols like HTTP, HTTPS, DNS, and others associated with web browsing or email usage are commonly used.
- Examples include Cobalt Strike using SMB encapsulation for communication and Dragonfly 2.0 using SMB as a C2 method.
- Mitigations:
    - Use Network Intrusion Detection and Prevention Systems (NIDS/NIPS) to detect and block C2 activity.
    - Monitor for uncommon data flows, unusual processes accessing email servers or applications, and suspicious API calls.

### Web Service (MITRE Technique T1102)

- Adversaries use legitimate external web services as a means for C2 communications.
- Popular websites and social media platforms are used to blend in with normal traffic.
- Examples include FIN6 using Pastebin for hosting content, Gamaredon Group hosting malicious code on GitHub, and Inception utilizing multiple cloud service providers for C2 infrastructure.
- Mitigations:
    - Use NIDS/NIPS and web proxies to detect and filter malicious web traffic.
    - Monitor for uncommon data flows, unusual timestamps, and employee activities outside of normal working hours.

### Non-standard Port (MITRE Technique T1571)

- Adversaries communicate using non-standard ports to bypass filtering and obfuscate network data.
- Examples include APT33 using HTTP over ports 808 and 880, and BADCALL malware using ports 443 and 8000 with FakeTLS.
- Mitigations:
    - Use NIDS/NIPS to detect and block suspicious or malicious network traffic.
    - Implement proper segmentation using firewalls and VLANs.
    - Restrict outbound connections on perimeter firewalls and proxies to specific ports.

## Key Points and Practices

- Command and Control involves communication methods used by adversaries to control compromised systems.
- Application Layer Protocol techniques use common protocols to avoid detection.
- Web Service techniques utilize legitimate external services for C2.
- Non-standard Port techniques involve using atypical ports for C2 communications.
- Mitigate C2 through NIDS/NIPS, web proxies, and proper network segmentation.
- Detect C2 through monitoring, packet inspection, and analysis of network traffic.

## References

- [MITRE ATT&CK Framework](https://attack.mitre.org/)


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 23rd 2023 (10:50 am) 
Last Modified Date: June 23rd 2023 (10:50 am)
