---
creation date: June 9th 2023
last modified date: June 9th 2023
aliases: []
tags: #📕
---

Primary Categories: [[02 - Active Directory]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📕  

# LLMNR Poisoning
___
LLMNR (Link-Local Multicast Name Resolution) poisoning is a network attack that exploits the LLMNR protocol to redirect network traffic and intercept sensitive information.

## What is LLMNR?
- LLMNR is a name resolution protocol used in modern Windows operating systems.
- It allows computers to resolve the names of neighboring network devices even when the DNS (Domain Name System) server is not available.

## LLMNR Poisoning:
- LLMNR poisoning involves an attacker responding to LLMNR name resolution requests with false information.
- By responding faster than legitimate network devices, the attacker can redirect traffic to their malicious machine.

## Potential Risks:
- Credential theft: Attackers can redirect authentication requests to their machine and capture usernames, passwords, or other sensitive information.
- Man-in-the-Middle (MitM) attacks: LLMNR poisoning enables attackers to intercept network traffic, manipulate data, or launch further attacks.
- Network reconnaissance: Attackers can gain insight into the network infrastructure, hostnames, or other valuable information through intercepted LLMNR requests.

## Techniques Used:
- Spoofing: Attackers send fake LLMNR responses to trick legitimate devices into connecting to their machine. [[04 - Responder|Responder]] tool is used for this MITM attack.
- ARP (Address Resolution Protocol) poisoning: Combined with LLMNR poisoning, ARP poisoning allows attackers to redirect traffic to their machine by poisoning the ARP cache of network devices.

## Mitigation Strategies:
- Disable LLMNR: If not required, disabling LLMNR protocol can prevent potential attacks. This can be done through group policies or directly on individual machines.
- Use DNS instead: Ensure DNS is the primary name resolution mechanism, and disable LLMNR on all devices.
- Implement secure network configurations: Utilize VLANs (Virtual Local Area Networks) or subnet isolation to limit the impact of LLMNR poisoning attacks.
- Network monitoring: Employ network monitoring tools to detect and alert on suspicious LLMNR traffic patterns or unauthorized device responses.
- Endpoint protection: Install and regularly update antivirus software, firewalls, and intrusion detection systems to detect and prevent LLMNR poisoning attempts.
- Regular security awareness training: Educate network users about the risks of LLMNR poisoning, phishing attacks, and the importance of not entering credentials on suspicious websites.




---
## Tools
---
[[04 - Responder]]








___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 9th 2023 (08:17 pm) 
Last Modified Date: June 9th 2023 (08:17 pm)
