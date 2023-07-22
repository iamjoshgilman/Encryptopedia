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

# [[03 - Sender Spoofing]]  
---

- Sender spoofing is the process of making the sending address in an email look the same as a legitimate email to make the recipients believe it is coming from a genuine sender. This is typically used with credential harvesters where the attacker wants the recipient to believe the email has actually come from the impersonated company so they will be more likely to enter in valid credentials.

### How Does Spoofing Work
- In a spoofing attack, the malicious actor sends an email with a "From:" address that appears to be from a source the recipient trusts, such as a well-known brand, work colleague, or family member. There is no verification done at this point, so SMTP emails can use any FROM address they want. Want to send an email that looks like it comes from contact@securityblue.team?

**Detecting *FROM* Spoofing attack:** Although the FROM address will look completely legitimate, we can look at the sending server IP (X-Originating-IP) and perform a WHOis or IP lookup search to determine whether this server actually belongs to the organization the email claims to be from. We will cover email security technology that can prevent these emails, such as SPF, DKIM, and DMARC, which are elaborated on in **PA6) Taking Defensive Actions**.

**Detecting *FROM w/ REPLY-TO* Spoofing attack:** We can look at the Reply-to address and see where replies would be sent. We can then block this address on the email gateway to prevent emails from going outbound to this address. We will cover email security technology that can prevent these emails, such as SPF, DKIM, and DMARC, which are elaborated on in **PA6) Taking Defensive Actions**.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 18th 2023 (12:01 pm) 
Last Modified Date: June 18th 2023 (12:01 pm)
