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

# [[03 - What Are APTs]]  
---

# APTs (Advanced Persistent Threats) 
are highly skilled attackers with state backing or extensive resources. They are known for delivering long-lasting, targeted attacks using previously unseen malware, exploits, and tailored software. Here are some real-world examples and what sets APTs apart:

## APT28 (Fancy Bear, Sofacy, Pawn Storm):
A Russian-based nation-state hacking group known for cyber espionage with political motives. They target militaries, security organizations, and governments, particularly in Eastern Europe and Georgia. Notably, they were involved in the attack against the Hillary Clinton campaign during the US presidential election.

## Cobalt Group (Gold Kingswood):
A financially motivated group targeting ATMs, payment systems, and banks. They employ spear-phishing attacks and exploits to target banks in Eastern Europe and Russia. The group has caused significant financial losses, surpassing a billion Euros across more than 40 countries.

## APT32:
Active since at least 2014, this threat group focuses on Southeast Asian countries like Vietnam, the Philippines, Laos, and Cambodia. APT32 has targeted private sector industries, foreign governments, dissidents, and journalists. They extensively use strategic web compromises to compromise victims.

# What makes APTs special?

1. **Funding and resources:** APTs receive significant funding and resources, often from nation-states, surpassing those available to individual hackers or small groups.
2. **Targeted motives:** APTs focus on financial, political, or military targets, distinguishing them from threat actors with various goals or hacktivist motivations.
3. **Sophisticated tools and methodologies:** APTs possess advanced tools, attack frameworks, tailored malware, zero-day exploits, and methodologies for network access and persistence.
4. **Persistent access:** APTs aim to acquire and maintain persistent access to target systems for espionage, surveillance, and other purposes, setting them apart from conventional hackers.

# Case Study: Cobalt Group

The Cobalt Group's attacks showcase an "exploitation chain" that escalates from a malicious email to a backdoor payload:

1. **Phase 0:** Spear-phishing emails are sent with malicious attachments or links, triggering the exploit chain.
2. **Phase 1:** Users download the attachment and are led to a Word document containing malicious code.
3. **Phase 2:** Cobalt Group utilizes an exploit kit called Threadkit to exploit critical vulnerabilities in Microsoft Office or Internet Explorer.
4. **Phase 3:** Legitimate Microsoft applications allowed by AppLocker, such as CMSTP, are employed to execute scripts or remote code.
5. **Phase 4:** PowerShell or CMSTP launches a DLL dropper, ultimately downloading and launching an encrypted Cobalt Strike beacon payload.
6. **Phase 5:** The Cobalt Strike beacon enables backdoor access, system compromise, and potential pivoting into other systems.

This case study highlights the orchestrated sequence of exploits, scripts, and payloads that APTs employ to bypass defenses and cause significant damage.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 19th 2023 (09:55 am) 
Last Modified Date: June 19th 2023 (09:55 am)
