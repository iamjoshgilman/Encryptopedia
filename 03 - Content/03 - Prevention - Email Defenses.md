---
creation date: June 22nd 2023
last modified date: June 22nd 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Incident Response]] | [[000 - Global Index]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Prevention - Email Defenses]]  
---

## SPF, DKIM, DMARC

- **Sender Policy Framework (SPF):** A DNS TXT record that specifies the authorized IP addresses or domains allowed to send emails on behalf of a custom domain. It helps prevent email address forgery and spoofing.
- **DomainKeys Identified Mail (DKIM):** An email authentication method that verifies the integrity of emails by adding a DKIM signature to the email header. The signature is generated using a private key and can be verified using the corresponding public key in the domain's DNS records.
- **Domain-based Message Authentication, Reporting & Conformance (DMARC):** An email authentication, policy, and reporting protocol that builds upon SPF and DKIM. It allows domain owners to specify actions when emails fail SPF and DKIM checks, such as none, quarantine, or reject.

## Marking External Emails

- Organizations can append subject lines or add messages in the email body to indicate that an email is coming from an external source.
- Adding a message like "[EXTERNAL]" or "[EXT]" helps raise awareness among employees and prompts them to be cautious when interacting with external emails.

## Spam Filter

- Spam filters are used to detect and block unsolicited or malicious emails.
- There are three main types of spam filters:
  - **Gateway Spam Filters:** Sit behind on-premises firewalls and filter emails at the network gateway.
  - **Hosted Spam Filters:** Cloud-based filters that update quickly and provide spam filtering services.
  - **Desktop Spam Filters:** User-installed filters, typically used in small office/home office (SOHO) scenarios.

## Data Loss Prevention (DLP)

- DLP controls aim to prevent sensitive information from leaving the organization via email or notify when potential data leaks occur.
- DLP solutions can flag emails based on keywords and phrases (e.g., confidential, proprietary) to identify potential data leaks, whether intentional or accidental.

## Sandboxing

- Sandboxing involves extracting and analyzing email attachments in a controlled virtual environment.
- Attachments are detonated (run) in the sandbox, monitoring their behavior for any malicious indicators.
- If malicious activity is detected, the email is classified as malicious, and the attachment is blocked from being delivered.

## Attachment Restrictions

- Instead of blocking attachments outright, organizations can consider restricting specific file types commonly used for malicious purposes.
- By assessing the file types used within the organization and the potential impact on business operations, appropriate restrictions can be applied.
- File types like .exe, .vbs, .js, .iso, .bat, .ps/.ps1, .htm/.html are commonly associated with malicious activity.

## Security Awareness Training

- Routine security awareness training should be conducted to educate employees on their role in protecting the organization.
- Training should cover policies, phishing awareness, email identification, and response to suspicious emails.
- Simulated phishing campaigns can be used to gather metrics and identify areas for improvement in employee awareness and response to phishing attacks.
- Additional training and support should be provided to employees who fall victim to phishing attacks to enhance their ability to recognize and respond to future attacks.

### Remember these key points:
- SPF, DKIM, and DMARC are domain records used to strengthen email security and prevent email spoofing.
- Marking external emails with indicators like "[EXTERNAL]" raises awareness among employees.
- Spam filters detect and block unsolicited or malicious emails using different types: gateway, hosted, and desktop filters.
- DLP controls help prevent data loss by flagging emails containing sensitive information.
- Sandboxing analyzes email attachments in a controlled environment to detect malicious behavior.
- Restricting certain attachment file types reduces the risk of malicious payloads.
- Security awareness training educates employees on email security, phishing, and incident response.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 22nd 2023 (12:27 pm) 
Last Modified Date: June 22nd 2023 (12:27 pm)
