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

# [[03 - Automated Artifact Analysis]]  
---

# Artifact Analysis with PhishTool

PhishTool's analysis console allows for efficient artifact analysis by providing integrated features such as WHOIS checks, VirusTotal reputation checks for MD5 hashes and URLs, and URL visualization. Let's explore how to analyze artifacts within the PhishTool analysis console:

# File Artifact Analysis

PhishTool automatically retrieves the file name and MD5 hash from email attachments. To check the reputation of the attachment using VirusTotal:

- Locate the attachment in the PhishTool console.

![[Pasted image 20230618153649.png]]

- On the right-hand side, click the button specifically designed for submitting the MD5 hash for a reputation check.
- This action generates a VirusTotal search query for the MD5 file hash and opens it in a new browser window.
- The VirusTotal report provides information about the attachment's reputation based on the analysis of various security vendors.

![[Pasted image 20230618153727.png]]

# Web Artifact Analysis

PhishTool allows you to generate live screenshots of URLs found in submitted emails. To view the web capture of a URL:

1. Find the email within the PhishTool console that contains the URL you want to analyze.
2. Click on the URL to expand its details.
3. Select "Web Capture" to generate a screenshot of the webpage associated with the URL.
4. The web capture also provides information about the HTTP requests made and headers from the site.

This feature helps visualize the content and appearance of the webpages associated with the URLs, aiding in analysis and assessment of potential malicious activity.

# WHOIS Lookup

PhishTool enables WHOIS lookup, providing information about a domain's registration and ownership. Here's how to perform a WHOIS search within the PhishTool console:

1. Identify the domain you want to analyze.
2. Use the PhishTool console's sidebar, located on the right-hand side, to initiate a WHOIS lookup.
3. The WHOIS lookup will provide details such as the domain's hosting location, registrant information, domain age, and contact email addresses.

WHOIS lookup assists in gathering important information about domains, helping in the assessment of their legitimacy and potential risks associated with them.

PhishTool's integrated features streamline the analysis process by providing quick access to WHOIS data, VirusTotal reputation checks for file hashes and URLs, and web captures. This enables security teams to analyze artifacts efficiently within a single platform.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 18th 2023 (03:01 pm) 
Last Modified Date: June 18th 2023 (03:01 pm)
