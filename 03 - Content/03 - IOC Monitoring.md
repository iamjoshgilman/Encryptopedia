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

# [[03 - IOC Monitoring]]  
---

IOC monitoring plays a critical role in security operations, enabling security analysts to detect and respond to malicious activity by continuously monitoring for indicators of compromise (IOCs) or precursors across the environment. Watchlists, created in SIEM or EDR platforms, are used to track these IOCs and trigger alerts when any malicious indicators are observed.

To illustrate the practical application of IOC monitoring, let's consider an example within a Security Operations Center (SOC):

1. A Threat Intelligence Analyst receives a list of known malicious IP addresses that have been associated with various malicious activities such as command-and-control, scanning, or hosting malware.

2. The Analyst decides to create a watchlist within the organization's SIEM platform. This watchlist is configured to generate an alert whenever any of the identified malicious IP addresses appear as either the source or destination IP in network traffic.

3. Suppose an employee falls victim to a phishing email and unknowingly clicks on a malicious link. The link leads them to a web server hosted on one of the monitored IP addresses, which is used to distribute malware.

4. As soon as the employee accesses the malicious website, the SIEM platform detects the connection and triggers an alert based on the watchlist. The alert is then forwarded to a Security Analyst for investigation.

5. The Security Analyst opens the alert, which provides details about the detected activity, including the specific IP address involved. With this information, the analyst can quickly determine the nature of the incident and take appropriate actions to protect the affected user and mitigate any potential damage. This may include isolating the affected system, blocking the malicious IP address, initiating incident response procedures, and providing guidance to the user on remediation steps.

By utilizing IOC monitoring and watchlists, security operations teams can proactively identify and respond to malicious activity across their environment. Automated threat exposure checks based on watchlists enable continuous monitoring without the need for constant manual searches, allowing threat intelligence analysts to focus on higher-level tasks. This helps enhance the organization's overall security posture and timely response to potential threats.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 19th 2023 (10:30 am) 
Last Modified Date: June 19th 2023 (10:30 am)
