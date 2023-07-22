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

# [[03 - Email Header, Artifacts, and Body Content]]  
---

- The first things we gather from a malicious or suspect email are artifacts (also referred to as IOCs). We use this information to try to link attacks together into campaigns, identify malicious actors behind the attacks, generate metrics, and perform trend analysis, allowing us to predict what will happen in the near future.
	- We need to include these in our report in a clear and concise way, so they can be found quickly, and other analysts can copy and paste them into different tools or services if needed (such as IOC reputation lookups, internal tools for searching, or sharing with other colleagues).

## Email Header and Artifacts

- Email Header:
  - Sending Email Address (Ex: J0hnSm1th@gmail.com)
  - Reply-to Address (Ex: F4keacc0unt2421@gmail.com)
  - Date Sent (Ex: 20th October 2019, 9:34 AM)
  - Sending Server IP (Ex: 40.92.10.10)
  - Reverse DNS of Sending Server IP (Ex: mail-oln040092010100.outbound.protection.outlook.com)
  - Recipient(s) (Ex: jason.s@domain.com, kirsty.p@domain.com, brian.b@domain.com)
  - Subject Line (Ex: Payroll Update – URGENT!)

- Email with URLs:
  - Any relevant URLs (Sanitized) (Ex: hxxps://Healthcare-United[.]com/wp/index/2020/PAYPAL/lure.php?)

- Emails with Attachments:
  - File Name(s) + Extension (Ex: PayrollDecember_UK.exe)
  - MD5 Hash(es)

## Email Body Content

- Attach the email file directly to the case in either .eml or .msg format, if possible.
- Include a brief description of the email and a screenshot in the case notes to provide context to other analysts.
- The appearance of the email can help identify trends, targeted attacks, and generate metrics.
- Write 1-2 sentences describing the email's appearance and its purpose to the recipient.

### Example One

![[Pasted image 20230618165833.png]]

Artifacts Retrieved:
Sender: bobtom112233@gmail.com
Reply-to: None
Date: Monday 16th September 2019 17:33
Sending Server IP: 209.85.167.42
Reverse DNS: mail-lf1-f42.google.com
Recipients: contact@dicksonunited.co.uk
Subject: Hello
URL: None
Attachments: None

Email Description:
This email contains no malicious URLs or attachments and is attempting to get the recipient to respond, either to engage in a social engineering attack or to see if the recipient mailbox is in use so it can be targeted in future attacks. Email classed as Recon.

### Example Two

![[Pasted image 20230618165854.png]]

Artifacts Retrieved:
Sender: amazonsupp0rt@outlook.com
Reply-to: no-reply@amazon.co.uk
Date: Monday 16th September 2019 19:25
Sending Server IP: 209.85.167.91
Reverse DNS: mail-lf1-f91.google.com
Recipients: claire.shelley@dicksonunited.co.uk
Subject: Suspicious Amazon Order Alert
URL: hxxp://maliciousdomainexample[.]com/
Attachments: None

Email Description:
This email from an Outlook mailbox is posing as Amazon using effective styling and asks the user to click a link to reset their password claiming that the user’s account has been hacked and used to purchase an order of £329.99. Using a sense of urgency is a common social engineer tactic, used to make the user rush and not think about what’s actually happening. The email contains a malicious URL, as it is not pointing to an Amazon-owned domain. Email classed as malicious / credential harvester.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 18th 2023 (04:10 pm) 
Last Modified Date: June 18th 2023 (04:10 pm)
