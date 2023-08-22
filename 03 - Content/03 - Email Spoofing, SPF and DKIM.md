---
creation date: August 22nd 2023
last modified date: August 22nd 2023
aliases: []
tags: #📖
---

Primary Categories: [[03 - Network Fundamentals]] | [[01 - Administration]] 
Secondary Categories: [[02 - Networking]] | [[000 - Cybersecurity Materials]]
Links: [[]] 
Search Tag: #📖  

# [[03 - Email Spoofing, SPF and DKIM]]  

___
# Overview

Email security is paramount due to the potential threat of email spoofing. Modern solutions like SPF and DKIM have been developed to counter these threats.
## Email Spoofing
- **What is it?** Email spoofing is the act of sending emails with a fake or "spoofed" FROM address.
- **Problem**: SMTP, being an older protocol, lacks native mechanisms to prevent this.
  
  🔑 **Key Point**: SMTP authentication only controls access to the SMTP server. Once authenticated, the sender can set any FROM address.
## SPF (Sender Policy Framework)
- **Function**: Lists valid IP addresses allowed to send emails from a domain. 
- **Mechanism**: A receiving mail server will check the SPF record of a domain when an email claims to be from that domain.
    1. If the sending IP address matches an IP in the SPF record, the email is legitimate.
    2. If not, the email is likely spoofed.
- **Limitation**: Outsourcing email to third parties (like Google) can undermine SPF because anyone using that third party might be seen as legitimate.

🔑 **Key Point**: SPF is effective but can be bypassed if attackers use a trusted third-party mail server listed in the SPF record.
## DKIM (DomainKeys Identified Mail)
- **Function**: Ensures that received emails are unmodified and actually come from the claimed sender/domain.
- **Mechanism**: Uses asymmetric cryptography.
    1. **Private Key**: The sending server signs the email.
    2. **Public Key**: Listed in the DNS settings of the domain, used by the receiving server to verify the email's signature.
- **Outcome**: 
    1. If the signature matches, the email is legitimate.
    2. If there’s no signature or if the signature doesn't match, the email is a forgery.
- **Advantage over SPF**: Email hosts can maintain separate private keys for every domain, ensuring individual domain security.

🔑 **Key Point**: DKIM offers more security than SPF as it validates the legitimacy of an email through cryptographic signatures.
## Things to Remember:
1. **Email Spoofing**: A major security concern where attackers can fake the 'FROM' address.
2. **SPF**: Uses a list of valid IP addresses to verify the sender. Good but can be bypassed.
3. **DKIM**: Cryptographic signatures ensure the integrity and source of an email. More secure than SPF.
4. **Best Practice**: Using both SPF and DKIM together is recommended for enhanced email security.

In a world where email-based attacks are common, understanding and implementing SPF and DKIM can significantly boost email security for any domain.

___
# How SPF Works

## SPF (Sender Policy Framework)

- **Purpose**: Validates whether a mail server is authorized to send emails for a specific domain.
- **Mechanism**: Uses DNS to check SPF records set up by the domain owner.
## Process of SPF Validation

1. **Initial Connection**:
   - A server with IP X.Y.Z.A from domain abc.test attempts to send an email.

2. **DNS Query**:
   - The receiving server queries the TXT records for `abc.test` in the global DNS infrastructure to find the SPF record.

3. **Check SPF Record**:
   - The SPF record lists allowed sender IP ranges or specific servers.
   - The receiving server checks if IP X.Y.Z.A is within these allowed ranges or list.

4. **Determine Legitimacy**:
   - If IP matches the allowed range: The email is seen as legitimate.
   - If IP doesn't match: The sender is potentially spoofing the domain. Such activity is deemed suspicious.

5. **Policy-Based Action**:
   - Based on the receiving server's policy, emails from unauthorized IPs can be:
     - Blocked.
     - Marked as suspicious.
     - Allowed but logged for monitoring.
## Points to Note:

- **Configuration is Key**: SPF relies on correct domain record configurations. Mistakes can lead to false positives or negatives.
- **Security Concerns**: If an attacker gains access to domain records, they can bypass or undermine SPF checks.

🔑 **Key Takeaways**:
1. SPF verifies the authenticity of an email based on the sender's IP and the domain's DNS records.
2. Proper configuration of SPF records is vital.
3. SPF acts as a first line of defense against email spoofing.
4. Always ensure your domain's DNS settings are secure to maximize SPF's effectiveness.

___
# How DKIM Works

## DKIM (DomainKeys Identified Mail)

- **Purpose**: Authenticates the identity of an email sender and ensures the integrity of the email content during transmission.
## The DKIM Signing Process

1. **Signing the Email**:
   - The sending server signs the email using a private key.
   - A hash is generated for the email header and a portion (or all) of the email body.
   
2. **Header Inclusions**:
   - **d**: Domain signing the message. (e.g., sans.org)
   - **b**: Unique signature of the email, produced using the sending server's private key.
   - **bh**: A hash of the email for validation.
## The DKIM Verification Process

1. **Email Arrival**:
   - The email arrives at the recipient server.
   - The server extracts headers for verification.

2. **DNS Query for Public Key**:
   - The recipient server queries DNS to obtain the public key to verify the signature.
   - The domain key selector (specified in the DKIM header) allows multiple DKIM entries for a domain (e.g., SES, own mail server, O365).
   - The query is made to `selector._domainkey.domain`.

3. **Retrieve Public Key**:
   - The DNS query returns a TXT record containing a 'p' value, which is the public key used for validation.

4. **Validation**:
   - Using the obtained public key, the recipient server validates the email's DKIM signature.
   - Successful validation confirms the authenticity of the sender and the integrity of the email's content.
## Points to Note:

- **Out-of-band Verification**: The verification process occurs independently of the email transmission itself, adding an extra layer of security.
  
- **Potential Vulnerabilities**: 
   - If an attacker compromises the sending server, they can manipulate DKIM values.
   - If an attacker gains control over the domain's DNS, they can inject their own DKIM records.
## Integrated Email Security:

- **SPF + DKIM + DMARC**: Integrating DKIM with SPF and DMARC frameworks drastically reduces email spoofing risks, enhancing the overall email security ecosystem.

🔑 **Key Takeaways**:
1. DKIM uses cryptographic methods to validate the sender and email content.
2. Verification involves retrieving the sender's public key from DNS and matching it with the email's signature.
3. Proper DKIM configuration is crucial to prevent vulnerabilities.
4. An integrated approach using SPF, DKIM, and DMARC offers robust protection against email spoofing.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 22nd 2023 (07:41 pm) 
Last Modified Date: August 22nd 2023 (07:41 pm)
