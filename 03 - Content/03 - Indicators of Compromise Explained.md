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

# [[03 - Indicators of Compromise Explained]]  
---

## Indicators of Compromise (IOCs)

Critical components of threat intelligence, enabling the sharing of information on threats in various formats. They serve as valuable data points for powering intrusion detection and prevention systems, endpoint detection and response systems, firewalls, and other automated defense mechanisms. Security analysts can also leverage IOCs to conduct threat exposure checks in their environments, identifying early or late signs of a cyberattack.

### Examples of IOCs

Here are some common examples of IOCs that are shared among organizations and publicly:

- **Email Addresses**: Malicious mailboxes involved in activities like sending emails containing malicious URLs, attachments, or attempting to deceive recipients into divulging sensitive information.

- **IP Addresses**: IPs associated with malicious behavior, including unauthorized port or vulnerability scans, hosting malicious content or websites, or being linked to command-and-control (C2) servers. WHOIS lookups provide additional details such as ownership, location, hostname, and contact information.

- **Domain Names/URLs**: Websites or domains engaged in malicious activities like hosting malware, phishing sites, or other harmful content.

- **File Hashes/File Names**: Unique hash values (e.g., MD5, SHA256, SHA1) used to identify and share intelligence about malware or malicious files. Security teams can leverage these hashes to blacklist specific files, enabling detection and removal by security solutions such as endpoint detection and response (EDR) systems.

### IOC Formats

IOCs can be shared using various formats, with two common methods being **STIX** and **TAXII**.

### STIX (Structured Threat Information eXpression) 
- Is a standardized language developed by MITRE and the OASIS Cyber Threat Intelligence Technical Committee for sharing threat information. It allows for structured information sharing, going beyond mere lists of IOCs. STIX is often used in conjunction with **TAXII**.
	- Motivations
	- Abilities
	- Capabilities
	- Response

### TAXII (Trusted Automated eXchange of Intelligence Information) 
- Facilitates the exchange of cyber threat information through services and message exchanges. It is designed to handle STIX information and enables sharing within specified groups or through public "threat streams."

Both STIX and TAXII enhance the sharing of threat intelligence by providing standardized formats that capture not only IOCs but also details related to threat motivations, abilities, capabilities, and response. This allows for more comprehensive analysis and response to cyber threats.

For more information on STIX and TAXII, you can refer to the following resources:

- [STIX Documentation](https://oasis-open.github.io/cti-documentation/stix/intro.html)
- [STIX Indicator Examples](https://stix.mitre.org/language/version1.0.1/samples.html)
- [Medium Article on STIX and TAXII](https://medium.com/sekoia-io-blog/stix-and-taxii-c1f596866384)

By leveraging IOC formats like STIX and TAXII, organizations can enhance their threat intelligence capabilities, promote information sharing, and strengthen their overall cybersecurity defenses.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 19th 2023 (10:17 am) 
Last Modified Date: June 19th 2023 (10:17 am)
