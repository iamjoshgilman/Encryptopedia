---
creation date: June 15th 2023
last modified date: June 15th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Security Fundamentals]] [[000 - Global Index]]
Secondary Categories: [[02 - Networking]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Network Security]]  
---

### Network Intrusion Detection (NIDS)
 can come in the form of software or physical devices that tap monitor network traffic in order to generate alerts for human analysts to investigate. NIDS can be positioned in the following positions:
 - **Inline**
	 - The system running the NIDS software is sitting directly in the path of network traffic, meaning all traffic will pass through the NIDS. In this case, the system will actually by definition become a Network Intrusion Prevention system, as it is able to perform defensive measures such as blocking or resetting connections.
- **Network Tap**
	- The NIDS will be connected to the network by tapping into a physical connection, such as a cable.
- **Passive**
	- The NIDS is connected to a SPAN port on a network device. This physical port allows all traffic passing through the device to be mirrored to the SPAN port, so the NIDS will get a copy of all network activity.

### Network Intrusion Prevention (NIPS)
- Network intrusion prevention systems are able to ==automatically take defensive actions== based on the activity that has been identified. So a NIDS can detect activity and generate an alert, but NIPS can detect activity and take actions to defend against it. As an example, if an internal system begins scanning other systems, which would be classed as unusual activity in most networks, we can pre-program the NIPS to block any communications that originate from the suspicious system, and generate an alert so human analysts can investigate further.

### Firewalls
- Firewalls are used to separate parts of a network to ==create private zones by restricting the traffic that can come in or go out==. The most obvious example is having a physical firewall between the internet and your network, ==only allowing common protocols== in such as HTTP, HTTPS, and DNS. This prevents random hosts from connecting to your systems, which could allow them to be exploited and compromised. There are different types of firewalls, with the three main being;
- Standard firewalls 
	- run on dedicated hardware and sit at key points of the network.
- Local firewalls in software form 
	- run on endpoints (such as Windows firewall).
- Web application firewalls in software form 
	- sit on internet-facing web servers that host websites or web applications.

### Log Monitoring
- Network devices can generate logs, and these logs can be sent to a SIEM platform. By having logs come from systems across the environment, the SIEM is able to provide a dashboard that analysts can utilize to monitor activity and respond to alerts that are generated when suspicious or malicious traffic is detected. Network devices can provide very valuable information, let's take a look at a couple of examples:
- **Web Proxy Logs**
	- This device processes web-based requests to the internet, and will contain a list of sites visited by employees. This can be combined with a blacklist to generate SIEM alerts when an employee tries to visit a malicious website or explicit website.
- **Perimeter Firewalls**
	- If a malicious actor starts port scanning the organization, the perimeter firewalls will pick this activity up first as they get smashed with requests from the scanning IP(s). By sending this to a SIEM an alert can be generated when a port or vulnerability scanning is being conducted, or when distributed denial-of-service attacks (DDoS) start.

### Network Access Control (NAC)
- works to ==prevent rogue or non-compliant devices from connecting to a private network==. Security teams could ==require that any devices connecting to the network need the latest patches and security updates, and must be running anti-virus. NAC is able to enforce this==, and not let devices connect to the network until they have met all of the requirements. This is typically used for ==Bring Your Own Device (BYOD) or guest networks==, where non-corporate devices will be connecting such as employee mobile phones and personal laptops, which may potentially be infected as they aren't protected by company security tools.
- Ever been to a restaurant or shopping center that offers free Wi-Fi, but you need to sign up? That's NAC in action, allowing the network administrators to restrict access and manage sessions, such as networks that have time limits, like public transport and commercial flights.

 





___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 15th 2023 (08:23 pm) 
Last Modified Date: June 15th 2023 (08:23 pm)
