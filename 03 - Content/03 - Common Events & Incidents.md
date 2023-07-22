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

# [[03 - Common Events & Incidents]]  
---

- **R2L – Remote to Local**
- **L2R – Local to Remote**
- **L2L – Local to Local**

![[Pasted image 20230622204004.png]]

## Remote to Local (R2L) Port Scanning

- R2L port scanning involves an external IP address scanning the public IP addresses owned by the organization to identify open ports.
- The purpose of R2L port scanning is to gather information about the organization's network and identify potential vulnerabilities.
- Detection can be performed by monitoring logs from perimeter firewalls and web application firewalls for multiple connections to different ports within a small timeframe.
- The impact of R2L port scanning is generally minimal, but intense scanning can consume bandwidth and potentially lead to a denial-of-service (DoS) situation.

![[Pasted image 20230622204032.png]]

## R2L Denial of Service (DoS) and Distributed Denial of Service (DDoS)

- R2L DoS involves an external IP address sending a high volume of requests or malformed packets to a target system with the intention of crashing it.
- R2L DDoS is similar to R2L DoS but involves multiple IP addresses coordinating the attack to overwhelm the target system.
- Detection can be based on establishing a baseline for normal traffic levels and generating alerts when the traffic exceeds the threshold.
- The impact of R2L DoS and DDoS attacks can be significant, causing the target system to crash and resulting in a denial of service for legitimate users.

![[Pasted image 20230622204108.png]]
*R2L denial of service attack, where one IP is attempting to send more packets to the target system than it can process*

![[Pasted image 20230622204136.png]]
*R2L distributed denial of service attack, where multiple IPs are attempting to crash or consume the target system’s resources*

## Local to Local (L2L) Scanning

- L2L scanning occurs when an internal private IP address scans other private IP addresses within the organization's network.
- L2L scanning is often performed by attackers who have compromised an internal system and are looking for other vulnerable systems.
- Detection can be achieved by monitoring for rapid connections between internal IP addresses, excluding internal vulnerability scanners from triggering alerts.
- L2L scanning indicates a potential compromise of an internal system and the attacker's attempt to perform lateral movement.

![[Pasted image 20230622204325.png]]

## Login Failures

- Login failures can occur due to various reasons, including users forgetting their passwords or malicious actors attempting unauthorized access.
- Monitoring Windows Security Log Event ID 4625 can provide valuable information about login failures in a Windows Active Directory environment.
- Detection involves setting thresholds for multiple login failures against the domain controller for the same username and investigating the status codes in the security log.
- Potential impacts of login failures include user productivity decline and the possibility of an attacker trying to gain access to internal accounts using password-related attacks.

![[Pasted image 20230622204349.png]]

#### Remember these key points:
- R2L port scanning involves external IP addresses scanning an organization's public IP addresses to identify open ports.
- R2L DoS/DDoS attacks aim to overwhelm a target system with a high volume of requests or packets, resulting in denial of service.
- L2L scanning occurs when internal IP addresses scan other internal IP addresses within the organization's network.
- Login failures can be caused by various factors, and monitoring login failure events helps detect potential unauthorized access attempts.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 22nd 2023 (12:54 pm) 
Last Modified Date: June 22nd 2023 (12:54 pm)
