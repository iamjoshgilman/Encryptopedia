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

# [[03 - URL Reputation Tools]]  
---

# Reputation Checks for Potentially Malicious URLs

Performing reputation checks on URLs can help determine if they are malicious or not. While there are several free online reputation tools available, we will focus on VirusTotal and URLScan.io as they are comprehensive and user-friendly. Here's how you can use these tools to assess the reputation of URLs:

## Important Note
It's crucial to remember that if a URL is not identified as malicious by online reputation tools, it does not guarantee its safety. Adopt the mindset of "innocent until proven guilty" for suspicious sites. Always assume that suspicious URLs are malicious until proven otherwise through further analysis.

Reputation sites are a good resource, but they are not foolproof. Unique and targeted attacks may not have been analyzed by other security professionals, leading to URLs with no negative comments that can still be extremely malicious. Additional analysis is always necessary.

# VirusTotal

1. Visit VirusTotal and click on the URL tab.
2. Enter the URL you want to check for reputation.
3. VirusTotal will provide you with a reputation score and information from various vendors.
4. Pay attention to the vendors that flag the URL as malicious, indicating potential threats. Vendors like Kaspersky, ESET, and Fortinet in the example screenshot.

# URLScan

1. URLScan is a service that offers detailed information about a URL.
2. Enter the URL you want to analyze, similar to the one checked on VirusTotal.
3. URLScan will provide extensive information such as reputation score, screenshot, web technologies used, domain and IP details.
4. While all the information can be useful during high-profile investigations, utilizing URL2PNG for visualization purposes will generally suffice.

# Threat Feeds

Public threat feeds offer valuable intelligence for security teams to combat phishing attacks and identify malicious artifacts. Here are two examples:
- [URLhaus Database](https://urlhaus.abuse.ch/browse/)Database: 
	- A vast collection of malicious URLs reported by researchers. It provides information such as the date the URL was added, the malicious URL itself, status (availability), tags indicating the type of malware, and the user who reported the URLs.
- [PhishTank](https://www.phishtank.com/): 
	- Similar to URLhaus, it allows users to submit phishing artifacts verified by the community.

These threat feeds can be used to generate blacklists of known malicious URLs, which can proactively block users from accessing these sites.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 18th 2023 (03:22 pm) 
Last Modified Date: June 18th 2023 (03:22 pm)
