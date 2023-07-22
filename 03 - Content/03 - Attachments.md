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

# [[03 - Attachments]]  
---

Malware can be distributed through email attachments, such as Microsoft Office documents that are utilizing malicious macros to download malware to the target system. In phishing campaigns, we will typically see three categories of attachments:
- **Non-malicious files that are used for social engineering** (such as invoices, letters of appeal, and images)
- **Non-malicious files that have malicious hyperlinks** (such as PDFs that contain a link to a malicious site)
- **Malicious files** (such as malicious scripts, or more likely Microsoft Office documents with malicious macros, such as Word or Excel)

## Social Engineering Files
- If an attacker is posing as a member of the Human Resources department at the target organization, they could try to extract information from a legitimate employee by sending them a form as an attachment that they need to fill out to assist with a payroll system change or any other bogus pretext scenario.
	- This can work well with other tactics such as sender spoofing to make the sending address look like it’s actually coming from the HR department of the organization.

## Lure Documents
- Inserting hyperlinks into a malicious email is common, and can potentially be detected easily by email security tools that retrieve URLs and sandbox them to see if the destination is malicious or has a bad community reputation. 
	- A way to prevent this is by including the hyperlink in a document, such as a PDF or Microsoft Word file. 
	- This means that the attachment itself isn’t inherently malicious, but the hyperlink inside can be.

## [[03 - Malicious File]]
- The most common form of inherently malicious files is Microsoft Office documents that are utilizing macros to run malicious code on the system that opens the document. They can download additional malware to the system by reaching out to domains on the internet and retrieving files, then executing them.

___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 18th 2023 (01:07 pm) 
Last Modified Date: June 18th 2023 (01:07 pm)
