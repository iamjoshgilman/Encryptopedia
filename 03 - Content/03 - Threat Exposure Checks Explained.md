---
creation date: June 19th 2023
last modified date: June 19th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Threat Intelligence]] | [[000 - Global Index]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Threat Exposure Checks Explained]]  
---

During a threat exposure check, analysts utilize various tools such as SIEM (Security Information and Event Management) and EDR (Endpoint Detection and Response) to investigate the presence of indicators of compromise obtained from intelligence vendors, information sharing partners, government alerts, or OSINT sources. This tactical task requires a deep technical understanding to analyze the results and identify any potential exposure, which can then be passed to security analysts for further investigation.

Let's walk through an example scenario to illustrate how threat exposure checks are conducted:

1. The threat intelligence team receives an email alert from US-CERT (United States Computer Emergency Readiness Team) notifying them of increased exploitation activity targeting "Vulnerability X" across the internet. The alert includes a list of IP addresses observed scanning for vulnerable devices.

2. The threat intelligence team retrieves the list of indicators of compromise and searches for them in their SIEM platform, where logs from perimeter firewalls are collected. This allows them to query all the indicators at once.

3. An assigned analyst performs a search in the SIEM platform specifically for the provided source IP addresses, focusing on the past 7 days of historical data. This search aims to identify if any of the mentioned scanning IPs have targeted the organization's public IP range during that timeframe.

4. If there is evidence of the malicious IPs conducting scanning or enumeration activity within the organization's network, appropriate actions can be taken. Depending on the nature of the IPs, IP blocks can be implemented. Additionally, alerts can be set up to trigger notifications if these IPs resume scanning, allowing defenders to closely monitor their activities.

5. In organizations with a dedicated vulnerability management team, close collaboration between the threat intelligence team and vulnerability management team is crucial. Context around vulnerabilities is important in determining the severity of the situation. A highly rated vulnerability may not be actively exploited, while a medium-rated vulnerability could be targeted on a larger scale. If malicious actors are actively exploiting a vulnerability, it serves as justification for immediate patching or mitigation measures.

By conducting threat exposure checks and promptly responding to identified risks, organizations can enhance their security posture and mitigate potential threats before they result in successful attacks.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 19th 2023 (10:35 am) 
Last Modified Date: June 19th 2023 (10:35 am)
