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

# [[03 - Preventative - Email Security Technology]]  
---

# Email Security Technologies: SPF, DKIM, and DMARC

To enhance email security and prevent email spoofing and phishing attacks, organizations can implement three essential email security technologies: SPF, DKIM, and DMARC. These technologies work together to protect custom domain names and verify the authenticity of incoming emails. Let's explore each technology:

# Sender Policy Framework (SPF) Records

Sender Policy Framework (SPF) is a DNS (TXT) record that helps prevent email address forgery by specifying the hostnames or IP addresses allowed to send emails for a specific domain. The SPF record includes the record type declaration, the authorized IP addresses and external domains, and an enforcement rule. When properly configured, SPF prevents malicious actors from spoofing a domain. An example SPF record syntax is:

```
v=spf1 <IP> <enforcement rule>
```

For example:

```
v=spf1 a: include:mailgun.org protection.outlook.com -all
```

This record allows mail to be sent from mailgun.org and protection.outlook.com, and the "-all" specifies a hard fail if the domain is spoofed by an unauthorized sender.

# DomainKeys Identified Mail (DKIM) Records

DomainKeys Identified Mail (DKIM) is an email authentication method that cryptographically verifies the authenticity of an email and checks for tampering during transmission. DKIM works by generating an encrypted hash of the email contents using a private key and adding it to the email header as a DKIM signature. The receiving server then verifies the integrity of the email by looking up the corresponding public key in the domain's DNS records. This ensures that the email has not been tampered with during transit. The basic DKIM record syntax is:

```
v=DKIM1 <key type> <public key>
```

# Domain-based Message Authentication, Reporting & Conformance (DMARC) Records

Domain-based Message Authentication, Reporting & Conformance (DMARC) is an email authentication, policy, and reporting protocol that builds upon SPF and DKIM. DMARC allows domain owners to specify actions for emails that fail both SPF and DKIM checks. The options include "none" (no specific action), "quarantine" (send emails to the spam folder), and "reject" (block the email). The DMARC record syntax is:

```
v=DMARC1 <action> <report address>
```

For example:

```
v=DMARC1; p=quarantine; rua=mailto:contact@securityblue.team
```

This DMARC record sets emails to go to the quarantine/spam folder when failing both SPF and DKIM checks, and aggregate reports are sent to contact@securityblue.team for failed DMARC emails.

When properly implemented, SPF, DKIM, and DMARC provide a robust defense against phishing attacks and domain impersonation, enhancing email security and ensuring the integrity of incoming emails.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 18th 2023 (04:25 pm) 
Last Modified Date: June 18th 2023 (04:25 pm)
