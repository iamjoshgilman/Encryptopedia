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

# [[03 - Incident Containment]]  
---

## Definition of Incident Containment
- Incident containment is a function that aims to limit and prevent further damage from occurring during an incident, while preserving forensic evidence for potential legal actions against attackers.
- It is an essential strategy within the incident response process.

## Containment Strategies
- Containment strategies should be defined based on the specific focus areas in the IT infrastructure, such as the perimeter, demilitarized zone, internal networks, or endpoints.
- Each organization's containment strategy will differ based on their systems and tools, requiring tailoring to the specific environment.

### Short-Term Containment
- Short-term containment focuses on preventing immediate further damage caused by the incident.
- Examples of short-term containment methods:
	- If an Active Directory (AD) account is compromised and is trying to log into every system it possibly can (**security incident**), and is successfully accessing some systems, then the account can be disabled in AD and the attacker can no longer use this user account (**containment**).
	- If an employee has accidentally downloaded malware to their corporate laptop (**security incident**), then we can use security tools to isolate the device and prevent any inbound or outbound connections, preventing it from connecting to other systems, exfiltrating data, or allowing the attacker to take remote control (**containment**).
	- If periodic connections are found from internal servers to a known command-and-control server IP address (**security incident**), the remote IP can be blocked on the perimeter firewalls to prevent any further communications going outbound or coming inbound from the C2 IP (**containment**).
	- If web attacks are being observed against the company's website (**security incident**), and all traffic shares a commonality (such as source IP or IP range, user-agent, headers), it can be blocked using a Web Application Firewall (WAF) on a device between the attack and the website server (**containment**).

### Long-Term Containment
- Long-term containment involves addressing the root causes of incidents to prevent their recurrence and improve overall security posture.
- Examples of long-term containment steps:
	- Patching vulnerabilities by updating software or firmware and making configuration changes.
	- Implementing new security tools such as email gateways, anti-virus solutions, or network intrusion detection systems.
	- Reviewing account permissions to ensure the Principle of Least Privilege is followed.

## Containment Measures

#### Perimeter Containment
- Block inbound and outbound traffic.
- Use IDS/IPS filters to identify and block malicious traffic.
- Configure Web Application Firewall (WAF) policies to detect and respond to web attacks.
- Implement null route DNS to prevent DNS resolutions, hindering connections to specific domains.

#### Network Containment
- Use switch-based VLAN isolation and router-based segment isolation to restrict network access.
- Apply port blocking to prevent connections on specific ports.
- Employ IP or MAC address blocking to restrict network access.
- Configure Access Control Lists (ACLs) to define network host permissions.

#### Endpoint Containment
- Disconnect infected systems from any network connections.
- Power off the infected system.
- Configure blocking rules in the local firewall.
- Implement Host Intrusion Prevention System (HIPS) actions, such as device isolation.

## Evaluating Containment Effectiveness
- After implementing containment measures, it is crucial to assess their effectiveness against the attack vector.
- Monitoring the attack vector, targeted victims, outbound traffic from victims, etc., provides important measures of effectiveness.
- An example of monitoring effectiveness is creating a rule in the Security Information and Event Management (SIEM) system to detect any outbound connections from a compromised system to non-internal systems.
- If such a connection is detected, it generates an alert indicating an ongoing incident and requires immediate escalation to the incident response team.

Remember: Incident containment aims to limit damage, preserve evidence, and prevent incidents from spreading. It involves both short-term measures to stop immediate damage and long-term actions to address root causes and improve overall security. Containment measures vary across different areas like the perimeter, network, and endpoints. Monitoring the effectiveness of containment measures is essential to ensure their success.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 23rd 2023 (10:13 am) 
Last Modified Date: June 23rd 2023 (10:13 am)
