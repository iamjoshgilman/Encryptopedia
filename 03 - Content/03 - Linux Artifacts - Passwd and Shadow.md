---
creation date: June 20th 2023
last modified date: June 20th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Digital Forensics]] | [[000 - Global Index]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Linux Artifacts - Passwd and Shadow]]  
---

## /etc/passwd
The **/etc/passwd** file is traditionally used to track registered users with access to a system. Key points about /etc/passwd include:

- It contains information about every user on the system.
- All users have read access to the file, but only superusers can write to it.
- It is useful for forensic investigations and incident response to identify user accounts, including potential hidden or disguised accounts.
- The file provides details such as usernames, user IDs, group IDs, home directories, and login shells.

## /etc/shadow
The **/etc/shadow** file contains encrypted passwords and additional account information. Key points about /etc/shadow include:

- It is readable only by the root account to prevent unauthorized access and password cracking attempts.
- The file stores encrypted passwords, account expiration values, and other information.
- It enhances security by separating password storage from the /etc/passwd file.
- Encrypted passwords in /etc/shadow prevent standard users from easily accessing plaintext passwords.

## Reading the Contents
To read the contents of these files:

- Use the command `sudo cat /etc/passwd` to view the content of /etc/passwd. It displays user account information, including encrypted passwords represented by 'X'.
- Use the command `sudo cat /etc/shadow` to view the content of /etc/shadow. It shows encrypted password values and other account information.
- /etc/shadow can only be read by the root account, providing an additional layer of security.

Understanding the information stored in these files is crucial for identifying user accounts, tracking modifications, and assessing the level of privileges assigned to each user.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 20th 2023 (01:32 pm) 
Last Modified Date: June 20th 2023 (01:32 pm)
