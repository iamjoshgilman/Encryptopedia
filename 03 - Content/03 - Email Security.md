---
creation date: June 15th 2023
last modified date: June 15th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Security Fundamentals]] [[000 - Global Index]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Email Security]]  
---

### Spam Filtering
- Scans can either be non-credentialed or credentialed, meaning that the scanner is able to log in to systems with high privileges and collect a lot more information about configurations, program versions, and more. However, a non-credentialed scan can give a better view of what an attacker would see, and can help to prioritize what vulnerabilities have a higher likelihood of being exploited, so they can be remediated first.

### Data Loss Prevention (DLP)
- Also known as data leak prevention is a security control that works to prevent sensitive business or personal information from leaving the organization in an unauthorized manner. This data can be categorized as files, banking information, account credentials, or PII (personal identifiable information). Depending on the DLP solution in use, it can monitor outgoing emails at different levels, such as:
	- Email body content
	- Email headers
	- Email attachments of various types

- If the DLP solution deems important information is about to be sent out of the organization, these emails will not make it past the email gateway and will not be sent. Emails can be scanned for specific keywords or use regex queries to flag messages containing certain content. If a disgruntled employee wants to send business-critical information to a rival organization before they are fired, they could attempt to send documents outside the organization by email - DLP would detect this, alert the security team, and prevent the email from being sent.

### Email Scanning
- Typically phishing emails will contain either a malicious URL or a malicious attachment (or both), and specially designed scanners will read the email header and body, and work to identify malicious indicators such as:
	- Using patterns or signatures
	- Blacklists
		- Email senders
		- File Hashes
		- Domain names

- When a suspicious email has been detected it can be quarantined so it's not delivered to an employee mailbox, and an alert is generated to inform the security team to investigate.

### Security Awareness Training
- Security awareness training should be a mandatory program that new employees must complete, as well as be completed routinely by all employees, with time frames often dictated under different ==compliance frameworks==. While this will focus on all different areas of security, ==phishing should play a large role in this.== Employees need to be told clearly how to spot suspicious or malicious indicators, and what steps the organization wants them to take, such as messaging or ringing the security team to alert them, or forwarding emails to a specific mailbox.







___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 15th 2023 (11:48 am) 
Last Modified Date: June 15th 2023 (11:48 am)
