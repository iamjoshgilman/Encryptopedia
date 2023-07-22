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

# [[03 - Malicious File]]  
---

## Malicious Attachments

### Microsoft Office Macros
- MS Office documents such as Word and Excel offer the ability to include macros. These are a series of commands and instructions that can be run automatically once enabled. 
	- Macro malware was fairly common several years ago because macros ran automatically when a document was opened. However, in recent versions of Microsoft Office, macros are disabled by default. 
	- This means malware authors need to convince users to enable macros so their malware can execute. They do this by showing fake warnings when a malicious document is opened.
	![[Pasted image 20230618122611.png]]
#### Microsoft has published some good suggestions for defending against macro malware:
- Make sure macros are disabled in your Microsoft Office applications. In enterprises, IT admins set the default setting for macros: [Enable or disable macros](https://support.office.com/article/Enable-or-disable-macros-in-Office-documents-7b4fdd2e-174f-47e2-9611-9efe4f860b12) in Office documents
- Don’t open suspicious emails or suspicious attachments.
- Delete any emails from unknown people or with suspicious content. Spam emails are the main way macro malware spreads.
- Enterprises can prevent macro malware from running executable content using [ASR rules](https://docs.microsoft.com/en-us/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction).

## Hosted Malware
- The other primary delivery method of malware is by hosting it on websites, and convincing users to click on a hyperlink, download a file, and then run it.

### Malicious Domains
- Estimated 140,000 malicious domains created a day. Then all the attacker needs to do is host a malicious file on a URL, and include it in phishing emails.

![[Pasted image 20230618122856.png]]

### Compromised Domains
- Legitimate sites can be compromised by attackers, and then used to host malware. Often the legitimate site is left completely intact so that the site owner and visitors don't realize their site has been hacked and is being utilized for malicious purposes. A hyperlink to the malicious URL hosting the malware is then distributed in phishing emails.

![[Pasted image 20230618123009.png]]










___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 18th 2023 (12:30 pm) 
Last Modified Date: June 18th 2023 (12:30 pm)
