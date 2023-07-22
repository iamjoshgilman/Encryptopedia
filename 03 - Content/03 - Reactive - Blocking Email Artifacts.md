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

# [[03 - Reactive - Blocking Email Artifacts]]  
---

- Block incoming and outgoing emails containing identified email artifacts.
- Important email artifacts to consider: Email Sender (mailbox@domain), Sender Domain (@domain), Sending Server IP, Subject Line.

# Email Sender

- Block malicious emails sent from the same sender to prevent them from reaching employee mailboxes.
- Consider implementing bi-directional blocking to prevent employees from replying to malicious emails.

# Sender Domain

- Block the entire sending domain when it is purely malicious or extensively used for sending malicious emails.
- Exercise caution when blocking domains like @Outlook or @Gmail to avoid blocking legitimate emails.

# Sending Server IP

- Apply this block sparingly and only when absolutely necessary.
- Block emails coming from specific IP addresses associated with compromised or malicious servers.

# Subject Line

- Phishing attacks often use a consistent subject line to avoid detection.
- Block emails with a specific subject line to catch multiple instances of the same phishing email.

Feel free to modify the formatting according to your preferences. Let me know if there's anything else I can assist you with!


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 18th 2023 (04:39 pm) 
Last Modified Date: June 18th 2023 (04:39 pm)
