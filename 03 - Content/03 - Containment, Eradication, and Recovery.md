---
creation date: May 31st 2023
last modified date: May 31st 2023
aliases: []
tags: #📕
---

Primary Categories: [[03 - NIST Incident Response Process]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📕  

# [[03 - Containment, Eradication, and Recovery]]  
___
**NIST Incident Response Framework: Containment, Eradication, and Recovery**

## **Containment:**

1. Primary stage in incident response; prevents incident spread.
2. Predetermined strategies for different incidents (e.g., DOS attack vs. malware).
3. Considerations: potential damage, evidence preservation, service availability, strategy implementation time, effectiveness, and solution duration.
4. Dangers of containment delay: attackers can escalate privileges or compromise systems.
5. Redirect attackers to sandbox environment for monitoring while minimizing damage.
6. Caution: even disconnected compromised hosts may cause damage.

## **Evidence Gathering and Handling:**

1. Evidence should be admissible in court; requires documentation of acquisition and preservation.
2. Detailed logs including location, hostname, MAC, IP addresses, names, titles, contact numbers of individuals involved, timestamps, and storage location.
3. Evidence storage location should be distinct from the location of identifying information.

## **Identifying the Attacking Hosts:**

1. Can detract from containment, eradication, and recovery; time-consuming and not always possible.
2. Common activities include validating the attacker's IP address, researching via open-source intelligence and domain intel, using incident databases, and monitoring possible attacker communication channels.

## **Eradication and Recovery:**

1. Eradication: Eliminating incident components (malicious files, breached accounts, exploited vulnerabilities). Not always necessary and can be part of the recovery process.
2. Recovery: Restoring operations to 'normal', ensuring functionality, patching vulnerabilities, restoring from backups, rebuilding systems, changing passwords, strengthening network security.
3. Use a phased approach to prioritize high-security changes first and large-scale infrastructure changes later.
4. Temporary infrastructure changes may be implemented but focus initially on critical security issues.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: May 31st 2023 (12:22 pm) 
Last Modified Date: May 31st 2023 (12:22 pm)
