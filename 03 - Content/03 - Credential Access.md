---
creation date: June 23rd 2023
last modified date: June 23rd 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Incident Response]] | [[000 - Global Index]]  
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Credential Access]]  
---

- Credential Access is the sixth stage in the MITRE ATT&CK framework.
- Adversaries aim to steal credentials (e.g., passwords, usernames) from compromised systems.
- Techniques include credential dumping and brute force attacks.
- This lesson focuses on two techniques: OS Credential Dumping (T1003) and Brute Force (T1110).

### OS Credential Dumping (MITRE Technique T1003)

- Adversaries retrieve passwords from the operating system and running applications.
- Sub-techniques:
    - LSASS Memory: Retrieving credentials from the LSASS process memory on Windows systems.
    - /etc/passwd and /etc/shadow: Dumping password and username information on Linux systems.
- Mitigations:
    - Use unique and complex passwords for local administrator accounts.
    - Implement Privileged Account Management (PAM) to secure and manage high-privilege accounts.
    - Provide user training to prevent password reuse attacks.
- Detection suggestions:
    - Monitor for activity related to LSASS memory, indicating potential credential dumping.
    - Utilize AuditD on Linux systems to detect processes accessing maps files.

### Brute Force (MITRE Technique T1110)

- Attackers attempt to guess valid username and password combinations or crack hashed passwords.
- Attackers may use password lists, iterate through possible combinations, or employ offline tools like Hashcat.
- Mitigations:
    - Implement account lockout policies to prevent continued brute force attempts.
    - Enable multi-factor authentication (MFA) to add an additional layer of security.
    - Follow NIST guidelines for password policies to increase resistance to brute force attacks.
    - Monitor for data breaches and issue password resets for compromised accounts.
- Detection suggestions:
    - Monitor logs for failed login attempts, especially Windows Security Log Event ID 4625.

## Key Points and Practices

- Credential Access involves stealing passwords and usernames.
- OS Credential Dumping retrieves credentials from the operating system and running applications.
- Brute Force involves guessing or cracking passwords.
- Mitigate credential access by using unique passwords, implementing PAM, and providing user training.
- Detect credential access by monitoring LSASS memory, auditing Linux systems, and analyzing logs for failed login attempts.

## References

- [MITRE ATT&CK Framework](https://attack.mitre.org/)
- [NIST Guidelines for Password Policies](https://pages.nist.gov/800-63-3/sp800-63b.html)


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 23rd 2023 (10:30 am) 
Last Modified Date: June 23rd 2023 (10:30 am)
