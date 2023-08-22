---
creation date: June 16th 2023
last modified date: June 16th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Phishing Analysis]] | [[000 - Cybersecurity Materials]]
Search Tag: #📖  

# [[03 - How Email Works]]  
---

![[Pasted image 20230616210146.png]]

- In the above example, we can see that the mailbox (also known as the 'localpart') is named **"contact"** and the domain is **"securityblue.team"**.

![[Pasted image 20230616210408.png]]

## Email Protocols

 ### **Simple Mail Transfer Protocol (SMTP)**
- Simple Mail Transfer Protocol works on TCP port 25 by default, is a communication protocol for electronic mail transmission. Once an email is created it is sent to the organization's SMTP server, which transports the email to the next server, before it eventually reaches the SMTP server of the recipient organization.
	- However, the world is moving away from port 25 and the new standard is becoming TCP port 587.

### **Post Office Protocol 3 (POP3)**
- Post Office Protocol (POP) is an application-layer Internet standard protocol used by e-mail clients to retrieve e-mail from a mail server, with version 3 (POP3) being the most widely-used version on the internet.
	- POP works by contacting your email server and downloading all emails from it. Once they are downloaded onto your system, they are deleted from the email server.
	- This means that after the email is downloaded, it can only be accessed using the computer that downloaded the emails, and trying to access your emails from a different device will not work.

### **Internet Mail Access Protocol (IMAP)**
- IMAP allows you to access your email wherever you are, from any device. When you read an email message using IMAP you're reading it from the email server. As a result, you can check your email from different devices, such as a laptop, desktop, and mobile phone.
	- IMAP still allows for emails to be downloaded, but you must manually click to save the email locally. This method for accessing emails is a lot more common than using POP, as it allows for better accessibility.

![[Pasted image 20230616210854.png]]

1. John Smith writes the message in his email client, which is sent to the organization's outbound SMTP server. At this point, the server doesn't understand where "DicksonUnited.com" is.
2. The outbound SMTP server queries the DNS server to find the IP address that is associated with "DicksonUnited.com".
3. The result is sent back to the SMTP server so it now understands where to send the email to.
4. The message is sent across the internet and may pass through other SMTP servers on the way.
5. The email reaches the destination domain's outbound SMTP server.
6. The email is moved from the first server via SMTP to a different server running either POP3 or IMAP, which allows the recipient to log into a client and access the email that is stored on the mail server.

## Webmail
- While we can access emails via an email client such as the Outlook application or Mozilla's Thunderbird program, a more convenient method is to use webmail. These are web-based email accounts, such as those offered by Hotmail/Outlook, Gmail, and Yahoo Mail.
	- As with any web application, webmail's main advantage over the use of a desktop email client is the ability to send and receive email from anywhere via a web browser, such as your laptop, desktop, phone, or tablet. The main disadvantage is that email cannot be accessed without an internet connection, which can be done with an email client, where emails are downloaded and stored locally.





___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 16th 2023 (09:07 pm) 
Last Modified Date: June 16th 2023 (09:07 pm)
