---
creation date: June 18th 2023
last modified date: June 18th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Phishing Analysis]] [[000 - Global Index]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Recon]]  
---

## Recon Emails
- Recon emails are used to check if the destination mailbox is in use so that it can be targeted in future phishing attacks. Recon emails can vary in sophistication, there are three types we tend to see in the real world:
	- Recon spam emails that contain nothing except random letters in the body text such as "adjdfkaweasda".
	- Emails that use social-engineering techniques to try and get the recipient to respond.
	- More complex emails use tracking pixels to see if the email has been viewed in an email client.

## Tactics Used

### Spam Recon Emails
- These emails do not use any tactics, and are simply looking to see if an email error code is sent back to the attacker, such as "undeliverable". This allows the attacker to determine whether the mailbox is in use (no error email sent back means the mailbox is in use, and the email was delivered).

### Social Engineering Recon Emails
- These emails will use social engineering techniques, such as posing as a person that the recipient may know or have regular communications with in order to get a response. 
- Other tactics may include creating a sense of urgency, such as _"I am about to meet with some important stakeholders, have you read the meeting notes yet?"_.
- These emails are also known as impersonation email attacks, or business email compromise attacks (BEC).

### Tracking Pixel Recon Emails
- These emails will typically follow the format of either a spam recon email, or a social engineering email, but are combined with an invisible tracking pixel, which allows the attacker to see if the email has been viewed by an email client. 
- Whilst the other email types can determine if a mailbox is being used, using a tracking pixel can help the attacker understand how **active** the mailbox is. 
- Monitoring the time it takes between sending the email and having it opened, can help the attacker avoid sending emails to unmonitored mailboxes which would have no impact but increase the risk of detection.
	![[Pasted image 20230618115216.png]]
- The malicious actor will add the tracking pixel using HTML code in the email body. This code contains an external link to a pixel server. If the email recipient opens the email, the client or webmail provider will load the HTML code, sending a message back to the server.
- **The following data can potentially be acquired and analyzed using a tracking pixel.**
	- The operating system used (gives information on the use of mobile devices).
	- Type of website or email used, for example on mobile or desktop.
	- Type of client used, for example, a browser (webmail) or mail program (email client).
	- Client’s screen resolution.
	- Date and time the email was read.
	- IP address (gives information on the Internet Service Provider and location).


















___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 18th 2023 (11:23 am) 
Last Modified Date: June 18th 2023 (11:23 am)
