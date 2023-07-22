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

# [[03 - Reactive - Blocking Web Artifacts]]  
---

# Web Proxy

![[Pasted image 20230618164008.png]]

## URL Blocks

- URL blocks are specific to blocking a particular URL.
- They may become ineffective if attackers modify the URL or dynamically generate URLs for specific recipients.
- Consider blocking suspicious directories or ending the block at an obviously malicious directory.

## Domain Blocks

- Domain blocks prevent access to an entire domain.
- Blocking the domain renders future attacks using the same domain but new URLs ineffective.
- Use domain blocks when there is no business justification for employees to visit the site.

# DNS Blackholing

- DNS blackholing involves creating a fake DNS entry to redirect users attempting to access a malicious site to a safe landing page.
- It can serve as a protective and educational measure.
- Consider using DNS blackholing alongside domain blocks during large-scale campaigns.

# Firewall

- Firewalls can be used to block access to servers hosting multiple malicious sites on the same IP.
- Typically used for blocking IPs involved in scanning or attacking the organization.
- IP blocks can be easily countered by using new IPs, making them less effective.

# Making The Decision

- Determine if the domain is created for purely malicious activity or compromised.
- For purely malicious domains, justify domain blocks on the web proxy.
- For compromised domains, assess if employees need to access the site for business purposes.
- If no legitimate reason, domain block the site; if access is required, consider URL blocks at appropriate levels.

Feel free to adjust the formatting as needed for your Obsidian notes. Let me know if there's anything else I can assist you with!



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 18th 2023 (04:58 pm) 
Last Modified Date: June 18th 2023 (04:58 pm)
