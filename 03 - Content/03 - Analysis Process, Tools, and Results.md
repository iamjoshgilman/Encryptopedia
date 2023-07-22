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

# [[03 - Analysis Process, Tools, and Results]]  
---

###### This section will be the largest part of your report and will cover the analysis you completed to assess the risk of any malicious artifacts such as attachments or URLs. You will include the tools you have used, and the results that they have provided. This can include visualization tools, reputation check results, as well as manual investigation methods such as detonating malware in a virtual sandbox.

# Example One: Malicious Artifact Analysis (URL) Report Example

URLs: https://maliciousdomainexample[.]com/index/2019/amazon/login.aspx
(The following analysis is not reflective of this URL, but is based on previous experience in investigating phishing emails and sites, and therefore reflects real investigations).

- WHOIS Analysis: Performing a WHOIS search shows that the domain was registered 3 days ago, with NameCheap as the domain registrar. There is no information about the site owner/domain registrant.

- VirusTotal Reputation: Searching for the full URL and the root domain on VirusTotal shows that it is currently not being flagged as malicious, likely the result of the domain being new, so security engines haven’t crawled it yet.

- URL2PNG Analysis: Using URL2PNG to view the link destination showed that the site was hosting a fake Amazon login portal, used to steal any credentials that are entered. Looking at the root domain "https://maliciousdomainexample[.]com" shows that the site doesn’t have a genuine homepage, a common sight when domains are used for purely malicious operations.

# Example Two: Malicious Artifact Analysis (Attachment) Report Example

Attachment Name: wallpaperHD.exe
Attachment MD5 Hash: 0c4374d72e166f15acdfe44e9398d026
Attachment SHA256 Hash: 240387329dee4f03f98a89a2feff9bf30dcba61fcf614cdac24129da54442762

- VirusTotal Upload: Uploading the file to VirusTotal shows that the file is extremely malicious and is detected by 61/71 engines. Link to VirusTotal page for this MD5 hash: [VirusTotal link](https://www.virustotal.com/gui/file/240387329dee4f03f98a89a2feff9bf30dcba61fcf614cdac24129da54442762/detection)

![[Pasted image 20230618170154.png]]

- Talos File Reputation: Uploading the SHA256 hash to Talos File Reputation (TFR) confirmed what VirusTotal stated about the file being extremely malicious.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 18th 2023 (04:56 pm) 
Last Modified Date: June 18th 2023 (04:56 pm)
