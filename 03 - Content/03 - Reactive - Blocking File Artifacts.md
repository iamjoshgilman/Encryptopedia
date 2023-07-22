---
creation date: June 18th 2023
last modified date: June 18th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Phishing Analysis]] | [[000 - Global Index]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Reactive - Blocking File Artifacts]]  
---

# Blocking Hashes

- Block the MD5, SHA1, or SHA256 hash of malicious files within the organization's endpoint detection and response (EDR) tool.
- When the hash is present on a protected endpoint, the software will recognize and delete it immediately, preventing its execution.
- Blocking the file hash defends against that specific email attachment, assuming the phishing attack does not use different files.
- Submit the hash to the organization's antivirus (AV) solution vendor if it is not initially flagged, to add it to their detection list.
- Commodity malware and advanced polymorphic malware can alter their file hashes, rendering hash blocks ineffective.
- Due to hash collisions, MD5 and SHA1 have been deprecated, and SHA256 is the current standard for file hashing.

# Blocking Names

- Blocking files based on their names is generally not recommended unless the file has an extremely unique name.
- Blocking files solely based on names may lead to the deletion of legitimate files used within the organization.
- Instead of blocking based on names, consider using file name blocks to generate watchlists of indicators of compromise (IOCs) for further investigation.
- Malicious files are typically blocked using file hashes as a more reliable and specific method.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 18th 2023 (04:07 pm) 
Last Modified Date: June 18th 2023 (04:07 pm)
