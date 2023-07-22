---
creation date: June 22nd 2023
last modified date: June 22nd 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Incident Response]] | [[000 - Global Index]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Prevention - Network Defenses]]  
---

## Network Intrusion Detection (NIDS)

- Network Intrusion Detection Systems (NIDS) monitor network traffic to detect suspicious or malicious activity and generate alerts for human analysts to investigate.
- NIDS can be positioned inline (becoming a Network Intrusion Prevention System - NIPS), connected through a network tap, or operate passively using a SPAN port to capture network activity.

## Network Intrusion Prevention (NIPS)

- Network Intrusion Prevention Systems (NIPS) are similar to NIDS but can automatically take defensive actions once malicious activity is detected.
- NIPS can block communications, reset connections, or take other actions to defend against identified threats.

## Firewalls

- Firewalls separate network segments and restrict traffic flow to create private zones.
- Traditional firewalls use rules based on source/destination IP, port, and protocol to allow or deny traffic.
- Next-Generation Firewalls (NGFWs) inspect packets at multiple OSI layers and can control specific applications' usage.
- Web Application Firewalls (WAFs) act as proxies between applications and external users, protecting against malicious activity.

## Event Monitoring

- Network devices generate logs that can be sent to a Security Information and Event Management (SIEM) platform.
- SIEM platforms provide a dashboard for security analysts to monitor and respond to alerts generated from logs.
- Examples of valuable logs include web proxy logs for site visitations and perimeter firewall logs for detecting scanning or DDoS attacks.

## Network Access Control (NAC)

- NAC can prevent unauthorized or non-compliant devices from connecting to a private network.
- Pre-admission NAC ensures devices meet policy requirements (e.g., patches, security updates) before granting network access.
- Post-admission NAC enforces restrictions and defines device interactions using Role-Based Access Control (RBAC).

## Web Proxy

- Web proxies act as intermediaries between clients and the internet, filtering and controlling access to resources.
- Proxies can reject requests, block access to malicious sites, and prevent users from retrieving potentially harmful resources.
- Web proxies are commonly used for security purposes and can be preconfigured to block known malicious URLs.

![[Pasted image 20230622201738.png]]

![[Pasted image 20230622201806.png]]

### Remember these key points:
- NIDS monitors network traffic and generates alerts for investigation, while NIPS can take autonomous defensive actions.
- Firewalls restrict traffic flow and can be traditional, NGFWs, or WAFs.
- Event monitoring uses SIEM platforms to analyze logs and detect suspicious activity.
- NAC controls network access based on device compliance and can enforce restrictions post-admission.
- Web proxies act as intermediaries, filtering and controlling access to resources from the internet.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 22nd 2023 (12:21 pm) 
Last Modified Date: June 22nd 2023 (12:21 pm)
