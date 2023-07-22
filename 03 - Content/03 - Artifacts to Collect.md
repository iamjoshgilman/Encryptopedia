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

# [[03 - Artifacts to Collect]]  
---

- Artifacts are specific pieces of information we need to retrieve from emails that allow us to conduct further searches, share intelligence with other organizations, and take defensive measures.

# Email Artifacts

### Sending Email Address
- Document the apparent sender's email address.
- Even if seemingly spoofed, it's important for tracking emails in email gateway security systems.

### Subject Line
- Useful as a search term to find associated emails.
- Can be used to block incoming emails from the same attack.

### Recipient Email Addresses
- Identify which mailboxes received the phishing email to warn the recipients.
- Typically, you'll need to check your email gateway, searching for emails from the sender with the same subject line.

### Sending Server IP & Reverse DNS
- Record the server IP that sent the email to identify possible spoofing.
- Use tools like MXToolbox for reverse DNS searches to learn more about the server.

### Reply-To Address
- Record the email address that would receive any replies to the original email.
- In cases of spoofing, this address may differ from the sending address and could belong to the attacker.

### Date & Time
- Document the time an email was sent to identify other potential emails from the same attack.
- This metric can help track when your organization is most vulnerable to malicious emails.

# File Artifacts

### Attachment Name
- Document the attachment's name, including the file extension.
- Depending on its uniqueness, the name can be used as an indicator of compromise and potentially blocked using an Endpoint Detection and Response (EDR) platform.

### SHA256 Hash Value
- Record the unique hash value of the file, which represents the file in its entirety.
- Useful for reputation checks with tools like VirusTotal and Talos File Reputation.
- Avoid using MD5 and SHA1 due to known hash collisions; SHA256 is the current security standard for file hashing.

# Web Artifacts

### Full URLs
- Always copy URLs directly from the phishing email; avoid writing out by hand to prevent errors.
- Copy the URL either directly from the email client by right-clicking the hyperlink and selecting "Copy Link Destination" or from a text editor.

### Root Domain
- While not always necessary if you have the full URL, the root domain can be an important artifact.
- It helps determine if the site was created for malicious activity or if it's a legitimate site that has been compromised.








___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 18th 2023 (01:50 pm) 
Last Modified Date: June 18th 2023 (01:50 pm)
