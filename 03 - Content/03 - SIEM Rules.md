---
creation date: June 21st 2023
last modified date: June 21st 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Security Information and Event Management]] | [[000 - Global Index]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - SIEM Rules]]  
---

# Notes on SIEM Rules

## SIEM Rules Overview
- SIEM rules come in two forms: provided by the SIEM provider for generic attack detection and suspicious patterns, and human-written rules by defenders of the organization.
- SIEM rules are search queries that look for specific activity within imported or real-time data fed into the SIEM solution.
- When a rule query matches a piece of data, various actions can be triggered, such as generating an alert, sending an email, or recording the activity in a separate location.
- SIEM rules can run continuously in real-time or be scheduled to run at specific times, such as daily or weekly.

## Examples of SIEM Rule Functionality
- Authentication/Account Activity:
  - Failed logon attempts
  - Successful (or failed) login attempts to disabled accounts
  - Use of specific accounts (local administrator, administrator, domain administrator)
  - SID (Security Identifier) changes to an account (potential indicator of privilege escalation)

- Process Execution:
  - Execution from unusual locations (e.g., temporary directories or browser caches, indicating malware execution or persistence mechanisms)
  - Suspicious process relationships (e.g., Microsoft Word spawning a child process of CMD or PowerShell window, potentially indicating a malicious macro executing code)
  - Known bad hashes (MD5, SHA1, SHA256 hashes generated from confirmed malicious files)

- Network Activity:
  - Port scans
  - Service enumeration
  - Host discovery

## False Positive Reduction and Tuning
- False positives are alerts generated that do not represent a malicious event.
- Thresholds can be set to control the generation of alerts based on search results from aggregated data.
- Example: Setting a rule threshold to generate an alert if an account fails to log in 10 times within 10 minutes, indicating a potential brute-force or dictionary attack.
- Rule tuning may involve specifying values to be ignored, such as excluding a source IP from triggering alerts in specific cases where the activity is known to be legitimate.

## Writing Search Queries and Alerts
- The process of writing search queries and setting up alerts will be covered in the next section of the course, where you'll set up your own local version of Splunk SIEM.
- You can apply your knowledge of writing search queries to create custom alerts tailored to your specific monitoring needs.
- It is recommended to read the guide on creating detection rules in the ELK stack (an open-source SIEM alternative) to gain insights into the logic behind rules. The guide can be found at: [Creating Detection Rules in the ELK Stack](https://www.elastic.co/guide/en/security/current/rules-ui-create.html)


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 21st 2023 (11:32 am) 
Last Modified Date: June 21st 2023 (11:32 am)
