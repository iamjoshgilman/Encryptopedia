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

# [[03 - Pyramid of Pain]]  
---

The Pyramid of Pain is a conceptual model that illustrates the level of difficulty and effectiveness in denying indicators to malicious actors. It represents the hierarchy of indicators that can be targeted to disrupt the operations of attackers. The model highlights the importance of focusing on higher-level indicators that are harder for adversaries to change, as it forces them to modify their entire attack methodology.

![[Pasted image 20230619105113.png]]

The layers of the Pyramid of Pain are as follows:

1. **Hash Values**: Hash values, such as those generated from malware samples, can provide strong indicators of compromise. However, they are relatively easy for attackers to modify by making small changes to the file, thereby circumventing hash-based detection methods.

2. **IP Address**: IP addresses are a step up in difficulty for attackers to change. While they can use techniques like VPNs, TOR browsing, or open proxies to switch IP addresses, it still requires additional effort.

3. **Domain Names**: Domain names used in attacks require registration and hosting. Although changing domain names is not as straightforward as changing IP addresses, it can still be done with some effort and a longer wait time.

4. **Network/Host Artifacts**: Network and host artifacts, such as directories, registry values, and specific files, provide more difficulty for attackers to modify. Implementing defenses against these artifacts can frustrate attackers as they need to find ways to work around the defenses.

5. **Tools**: Tools used by attackers, such as specific malware or exploit kits, are harder to change. By identifying and blocking these tools, defenders can severely disrupt the attackers' operations, forcing them to retool or develop new methods.

6. **Tactics, Techniques, and Procedures (TTPs)**: TTPs represent the behavior patterns and methodologies of attackers. Changing TTPs requires significant effort and reworking of their entire attack methodology. By understanding and profiling these patterns, defenders can better respond and defend against the attackers.

The purpose of the Pyramid of Pain is to emphasize the importance of targeting higher-level indicators that cause more frustration and hurdles for attackers. By focusing on these indicators, organizations can strengthen their defenses, identify weaknesses, and better detect and respond to indicators of compromise. The model aims to make the lives of adversaries harder and increase the effectiveness of defensive measures.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 19th 2023 (10:26 am) 
Last Modified Date: June 19th 2023 (10:26 am)
