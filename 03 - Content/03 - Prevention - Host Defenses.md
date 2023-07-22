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

# [[03 - Prevention - Host Defenses]]  
---

## Host Intrusion Detection and Prevention (HIDS/HIPS)

- **[[03 - Endpoint Security#^block1|Host Intrusion Detection System (HIDS)]]** are software installed on an endpoint to detect suspicious or malicious activity using predefined rules. They generate alerts for further investigation.
- **[[03 - Endpoint Security#^block2|Host Intrusion Prevention Systems (HIPS)]]** work similarly to HIDS but can autonomously take actions to defend systems once malicious activity is detected. Rules in HIPS contain actions such as terminating connections or deleting malicious files.

## Anti-Virus Software

- Anti-virus (AV) software detects and removes known malware on endpoints.
- Two types of AV solutions:
  - **Signature-based:** Uses specific patterns (signatures) to identify known malware. It can remove or quarantine malware and generate alerts. However, it may miss new or unknown malware.
  - **Behavior-based:** Identifies suspicious behavior by comparing activity against a baseline of "normal" behavior. Deviations or anomalies are flagged as potentially malicious.

## Centralized Logging

- Endpoints can be configured to send logs to a centralized location or a Security Information and Event Management (SIEM) platform.
- SIEM platforms aggregate, normalize, and match logs against rules to detect and flag suspicious or unusual activity for investigation by security analysts.

## Endpoint Detection & Response (EDR)

- EDR agents silently sit on endpoints and provide logging, monitoring, and reactive capabilities.
- EDR agents report activity to a platform similar to a SIEM, where analysts can investigate alerts and analyze suspicious activity.
- EDR platforms can also monitor for insider threats and provide in-depth investigations into user activities.

## Local Firewall

- Local firewalls or web application firewalls on endpoints provide additional security by applying rules to the system they run on.
- Administrators can control what ports should be open and allow or deny connections coming in or going out of the system.

## Windows Group Policies (GPOs)

- GPOs are collections of settings created by system administrators using the Microsoft Management Console (MMC) Group Policy Editor.
- GPOs can be associated with Active Directory containers like sites, domains, or organizational units (OUs).
- GPOs are applied in a predictable order: Local policies, Site policies, Domain policies, and OU policies.
- GPOs can enforce various security measures, such as disabling local administrator rights globally, implementing least-privileged models, enforcing password policies, and managing folder redirections.

Remember these key points:
- HIDS and HIPS are host-based security controls for detecting and preventing malicious activity.
- Anti-virus software detects and removes known malware, either through signatures or behavior analysis.
- Centralized logging and SIEM platforms help detect and investigate suspicious activity.
- EDR agents provide logging, monitoring, and reactive capabilities on endpoints.
- Local firewalls and GPOs enhance security and control on individual systems.
- GPOs in Windows domains allow administrators to enforce security settings and streamline management.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 22nd 2023 (12:15 pm) 
Last Modified Date: June 22nd 2023 (12:15 pm)
