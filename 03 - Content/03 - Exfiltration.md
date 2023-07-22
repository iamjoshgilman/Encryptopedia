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

# [[03 - Exfiltration]]  
---

- Exfiltration is the tenth stage in the MITRE ATT&CK framework.
- It refers to techniques used by adversaries to steal data from compromised networks and systems while avoiding detection.
- Exfiltration involves the compression, encryption, or encoding of files during removal from the network, and typically uses a command-and-control (C2) communication channel.
- This lesson focuses on the following techniques: Exfiltration Over C2 Channel (T1041) and Scheduled Transfer (T1029).

### Exfiltration Over C2 Channel (MITRE Technique T1041)

- Adversaries use existing C2 channels to exfiltrate data from a network.
- Data is extracted during beacons calling out to C2 servers.
- Detection methods:
    - Look for clients sending a significant amount of data to a server.
    - Utilize Network Intrusion Detection Systems (NIDS) with rules to detect specific file types being transferred.
    - Detect the C2 server itself by analyzing beacon frequency and intervals.

### Scheduled Transfer (MITRE Technique T1029)

- Adversaries schedule data exfiltration to occur at specific times to evade detection.
- ADVSTORESHELL malware collects, compresses, encrypts, and uploads data to the C2 server every 10 minutes.
- Cobalt Strike can set beacon payloads to use random intervals and break large files into smaller chunks for subtle transfer.
- ComRAT and Dipsind operate during standard business hours to blend in with normal traffic.
- Mitigation:
    - Use NIDS to detect and respond to suspicious or malicious activity over the network.
- Detection methods:
    - Monitor for unusual processes accessing files and making network connections.
    - Look for network connections with large packets indicating file uploads.

## Key Points and Practices

- Exfiltration involves stealing data from compromised networks and systems.
- Exfiltration over C2 channels utilizes existing communication channels for data extraction.
- Scheduled transfer involves timing data exfiltration to evade detection.
- Mitigate exfiltration with NIDS and detection rules.
- Detect exfiltration through monitoring network traffic, file access, and abnormal behavior.

## References

- [MITRE ATT&CK Framework](https://attack.mitre.org/)


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 23rd 2023 (10:54 am) 
Last Modified Date: June 23rd 2023 (10:54 am)
