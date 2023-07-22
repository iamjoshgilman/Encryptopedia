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

# [[03 - Manual Collection - Email Artifacts]]  
---

# Email Artifact List

The following artifacts can be easily retrieved from an email:
- **Sending Address**: The email address of the sender.
- **Subject Line**: The subject line of the email.
- **Recipients**: The recipients of the email (except those in BCC).
- **Date + Time**: The date and time when the email was sent.

# Email Client Extraction

Using an email client like Outlook, you can quickly retrieve the following artifacts:
- **Subject Line**: e.g., "Hello"
- **Sending Address**: e.g., "bobtom112233@gmail.com"
- **Date + Time**: e.g., "Monday 16th September 2019 at 17:33"
- **Recipient(s)**: e.g., "contact@dicksonunited.co.uk"

![[Pasted image 20230618140217.png]]

# Text Editor Extraction

Additional information can be obtained using a text editor, such as Sublime Text 2, by downloading the email as a .eml or .msg file and opening it. 

![[Pasted image 20230618140326.png]]

1. To extract the **Sending Server IP** (X-Sender-IP), use the Find feature (CTRL+F) and search for "IP." The first string found should be the X-Sender-IP.

![[Pasted image 20230618140344.png]]

2. Convert the IP address into a **hostname** by performing a reverse DNS lookup. Use a free online service like [Domain Tools](https://whois.domaintools.com/) to retrieve information about the server.

![[Pasted image 20230618140428.png]]

3. Retrieve the **Reply-To address** by using the search function in the text editor to find the string "reply" or "Reply-To." Identify the address that would receive any replies to the email.

![[Pasted image 20230618140443.png]]

# Conclusion

By analyzing a suspicious email, you can extract the following artifacts:
- **Sending Address**
- **Subject Line**
- **Recipient(s)**
- **Date and Time**
- **Sending Server IP**
- **Reverse DNS of Sending Server IP**
- **Reply-To** (if present)



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 18th 2023 (02:42 pm) 
Last Modified Date: June 18th 2023 (02:42 pm)
