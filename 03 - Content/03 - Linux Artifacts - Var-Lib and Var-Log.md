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

# [[03 - Linux Artifacts - Var-Lib and Var-Log]]  
---
# /var/lib and /var/log

## /var/lib

### Installed Software and Packaging
- The file **/var/lib/dpkg/status** on Debian-based systems contains a list of all installed software packages.
- It provides valuable information about the programs installed on the system.
- Examining this file can help forensic investigators or incident responders identify installed applications.
- Searching within the file or filtering specific details can be done using text editors or command-line tools like `grep`.

Example command to filter package names and save them to a text file:
```
cat status | grep Package > packages.txt
```

## /var/log

### Operating System Logs
- Key log files located in **/var/log** may vary depending on the Linux-based operating system being used.
- Important log files for cybersecurity professionals include:
  - **/var/log/auth.log**: Contains system authentication information, including user logins.
  - **/var/log/dpkg.log**: Logs information about package installation or removal using the 'dpkg' command.
  - **/var/log/btmp**: Contains information about failed login attempts.
  - **/var/log/cron**: Logs cron job information, useful for detecting potential abuse for persistence.
  - **/var/log/secure**: Contains information related to authentication and authorization privileges, including SSH login attempts.
  - **/var/log/faillog**: Logs user failed login attempts.

### Web Server Logs
- For Linux-based systems running web server frameworks like Apache, the log file **/var/log/apache2/access.log** is valuable.
- It provides information about requests made to the web server, including:
  - Client IP address
  - Resource being accessed
  - HTTP method (typically GET)
  - User-agent (browser or client information)
  - Timestamp of the request
- Analyzing access logs helps identify activities such as vulnerability scanning and exploitation.

Example Apache access log entry:
```
52.50.100.106 - SBTUser [27/Jul/2020:15:30:00 -0600] "GET /logo.png HTTP/1.1" 200 379
```
Key elements in the log entry:
- IP address: 52.50.100.106
- Userid: SBTUser (if applicable)
- Timestamp: [27/Jul/2020:15:30:00 -0600]
- Resource: "GET /logo.png HTTP/1.1"
- HTTP response code: 200 (OK)
- File size: 379 bytes
Analyzing these logs can reveal vulnerability scanning, exploitation attempts, and more.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 20th 2023 (01:04 pm) 
Last Modified Date: June 20th 2023 (01:04 pm)
