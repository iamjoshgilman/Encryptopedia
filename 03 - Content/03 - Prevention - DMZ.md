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

# [[03 - Prevention - DMZ]]  
---

## What is a DMZ?

In computer networks, a DMZ (demilitarized zone) is a physical or logical subnet that separates an internet local area network (LAN) from other untrusted networks, usually the internet. It acts as an additional layer of security by keeping the internal LAN unreachable, restricting direct access to internal servers and data from the internet.

### Purpose of a DMZ

- Protect sensitive organizational systems and resources.
- Isolate and keep potential target systems separate from internal networks.
- Reduce and control access to systems outside the organization.

## DMZ Systems

Services and systems that are placed in a DMZ include:

- Web servers
- Proxy servers
- Email servers
- Domain Name System (DNS) servers
- File Transfer Protocol (FTP) servers
- Voice over IP (VoIP) servers

## Architecture

There are two major methods to construct a network with a DMZ: using a single firewall or dual firewalls.

### DMZ Architecture - Single Firewall

In this approach, a single firewall with a minimum of 3 network interfaces is used. The DMZ is placed inside this firewall. The tier of operations includes:

1. External network device: Connects to the ISP.
2. Internal (private) network device: Connects to the internal network.
3. DMZ network device: Handles connections within the DMZ.

![[Pasted image 20230622195508.png]]

### DMZ Architecture - Dual Firewall

A more secure approach involves using two firewalls to create a DMZ. The frontend firewall only allows traffic destined for the DMZ, while the backend firewall handles traffic from the DMZ to the internal (private) network. It is recommended to use firewalls from separate vendors to further increase protection and reduce vulnerabilities.

![[Pasted image 20230622195533.png]]

## Benefits of a DMZ

The primary benefits of a DMZ include:

1. **Access control for organizations**: A DMZ allows organizations to provide access to services outside their network perimeters through the public internet while maintaining network segmentation. It increases the obstacles an unauthorized user must overcome to gain access to the private network.
2. **Prevention of network reconnaissance**: The DMZ acts as a buffer, preventing attackers from scoping out potential targets within the network. Even if a system within the DMZ is compromised, the private network remains protected by the internal firewall.
3. **Protection against IP spoofing**: A DMZ can stall potential IP spoofers by verifying the legitimacy of IP addresses through another service on the network before granting access.

Remember these key points:
- DMZ stands for demilitarized zone, which separates the LAN from untrusted networks.
- DMZs protect sensitive systems, isolate target systems, and control access.
- Common services in a DMZ include web servers, proxy servers, and email servers.
- Two common DMZ architectures are single firewall and dual firewall.
- DMZs provide access control, prevent network reconnaissance, and protect against IP spoofing.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 22nd 2023 (12:09 pm) 
Last Modified Date: June 22nd 2023 (12:09 pm)
