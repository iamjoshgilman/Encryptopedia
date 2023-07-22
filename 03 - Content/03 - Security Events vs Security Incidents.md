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

# [[03 - Security Events vs Security Incidents]]  
---

In the field of cybersecurity, it's crucial to understand the distinction between security events and security incidents. This lesson will explain the key differences between the two and highlight the measures taken to address them. By the end of this lesson, you will be able to explain the difference and provide examples of each category. Remember, all security incidents are security events, but not all events become incidents.

## Security Events

A **security event** refers to any occurrence that could have security implications, potentially causing damage or disruption. Here are some examples:

1. **Spam emails**: Emails that may contain hyperlinks to malicious websites like credential harvesters or malware downloads.
2. **Vulnerability scan**: Malicious actors scanning for vulnerabilities that can later be exploited.
3. **Reconnaissance scans**: Malicious actors gathering information about an organization's systems to identify vulnerabilities and weaknesses.
4. **Explained anomaly**: Unusual circumstances with a known cause, often caused by misconfigurations, which disrupt the network.
5. **User downloading software**: Downloading software from the internet onto a company-owned device, posing risks of unintentionally downloading malicious software or legitimate software bundled with malware.
6. **Brute-force attack**: Malicious actors attempting to gain unauthorized access to a web server's login portal.

Security events occur frequently and are typically managed by automated security controls or logged for future reference in case they escalate into security incidents.

## Security Incidents

**Security incidents** are security events that have resulted in actual damage to the organization. Let's revisit the examples of security events and understand how they can turn into incidents:

1. **Spam email**: If the email contains a malicious URL that downloads ransomware, encrypting the organization's files, it becomes a security incident. The email delivery is the security event, and the file encryption is the damage.
2. **Vulnerability scan**: If the scan reveals easily exploitable vulnerabilities, which are subsequently exploited by a malicious actor, leading to data exfiltration, it becomes a security incident. The vulnerability scan is the security event, and the data breach is the damage.
3. **Unexplained anomaly**: An unusual circumstance where the root cause is unknown. Until it is properly investigated, it is considered an incident due to the potential for malicious activity.
4. **User downloading software**: If the downloaded software turns out to be malware, infecting the system and exfiltrating data, it becomes a security incident. The user's software download is the security event, and the data exfiltration is the damage.
5. **Brute-force attack**: If a brute-force attack on a web server's login portal is successful, allowing unauthorized access and compromising private information, it becomes a security incident. The brute-force attack is the security event, and the intrusion and access to private information are the damage.

## Events vs Incidents

In practice, **security events** are typically managed by security analysts, often within a Security Operations Center (SOC). On the other hand, **security incidents** are often handled by specialized incident responders. The size of the organization and security team may determine whether incidents are handled internally or by an external Computer Security Incident Response Team (CSIRT). Advanced analysis and investigation are performed to understand the incident's nature, contain it, and formulate an appropriate response.

It's essential to note that not every Security Information and Event Management (SIEM) or Intrusion Detection System (IDS) alert is an incident. Many alerts represent manageable events, such as an IP scanning the organization's public IP range, or they may even be false positives where no malicious activity has occurred. Each alert generated should be thoroughly investigated, leveraging knowledge and experience to determine its significance and appropriate response.

Remember to constantly evaluate


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 22nd 2023 (10:21 am) 
Last Modified Date: June 22nd 2023 (10:21 am)
