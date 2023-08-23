---
creation date: August 22nd 2023
last modified date: August 22nd 2023
aliases: []
tags: #📖
---

Primary Categories: [[03 - Network Fundamentals]] | [[02 - Networking]] 
Secondary Categories: [[01 - Administration]] | [[000 - Cybersecurity Materials]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - DHCP]]  

___
# Overview
- **DHCP (Dynamic Host Configuration Protocol)**: A protocol that automates network configuration settings for devices joining a network.
- **Primary Purpose**: Assign IP addresses dynamically to ensure seamless network joining and to prevent IP conflicts.
## Key Features of DHCP
1. **Automatic IP Allocation**: Eliminates the need for manual IP configuration for each device.
2. **Avoidance of IP Conflicts**: The DHCP server tracks assigned IPs, ensuring no IP is assigned to more than one device.
3. **Single DHCP Server Per Network**: Multiple DHCP servers on the same network can cause conflicts, leading to IP overlap.
4. **Integrated in Home Routers**: Most home networks have a built-in DHCP server within their router, but businesses often use dedicated DHCP servers.
## Static vs. Dynamic IP Allocation
1. **Dynamic Allocation**: DHCP assigns an IP address dynamically from a pool every time a device connects.
2. **Static Allocation**: Specific devices are given a fixed IP address, ensuring they always have the same address when they connect. Useful for servers, printers, and other critical network devices.
## Security Implications
- **Potential Attack Vector**: If an attacker gains control over the DHCP server, they can dictate network configurations, potentially intercepting or rerouting traffic.
- **Mitigation**: Employing secure DHCP configurations, using VLANs, and continuously monitoring network traffic can help prevent DHCP-based attacks.
## Things to Remember:
1. **DHCP's Role**: Simplifies network management by automating IP allocations.
2. **Potential Risks**: If compromised, DHCP can become a tool for malicious activities.
3. **Static Allocation**: Used for specific devices that require consistent network addressing.
4. **One DHCP Server**: It's essential to have a single DHCP server per network to prevent potential conflicts.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 22nd 2023 (08:10 pm) 
Last Modified Date: August 22nd 2023 (08:10 pm)
