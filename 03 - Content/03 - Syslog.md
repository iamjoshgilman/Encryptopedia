---
creation date: June 20th 2023
last modified date: June 20th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Security Information and Event Management]] | [[000 - Global Index]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Syslog]]  
---

## Overview
- Syslog is a standard protocol used to convey event or system log notification messages to a designated server known as a Syslog server.
- It centralizes data collection from various devices for analysis, review, and intervention.
- The Syslog protocol is outlined by RFC 5424.
- It can be enabled on network equipment such as switches, routers, firewalls, and endpoint devices.
- Syslog is available on Unix, Linux-based systems, and many web servers.
- Windows systems use their own default logging system (Windows Event Manager) but can be forwarded to a central server using Syslog.
- Custom applications can also be developed to use Syslog for log transport.
- Syslog uses **UDP 514** by default; TCP **514** can be used for more reliability; however, certain stricter security standards require that logs are securely transferred, so **TCP 6514** is used as a de facto standard.
- Syslog does not offer built-in authentication or encryption, making it susceptible to attacks.

![[Pasted image 20230620205614.png]]

## Importance of Syslog in Network Monitoring
- Syslog is an important component of network monitoring as it ensures that events occurring without a dramatic effect are not overlooked.
- It is recommended to use software that combines multiple tools to have a comprehensive overview of network activities.

## Syslog Messages
A Syslog message consists of three components: Priority Value (PRI), Header, and Message.

### Priority Value (PRI)
- The Priority Value is derived from both the Facility Code and the Severity Level.
- The equation to calculate PRI is: `(facility code * 8) + Severity value = PRI`.
- Facility Code and Severity Level tables are used to determine the values for PRI.

![[Pasted image 20230620205519.png]]
![[Pasted image 20230620205542.png]]

### Header
- The Header contains identifying information, including Timestamp, Hostname, Application name, and Message ID.
- It helps in understanding the source of the system message.

### Message
- The Message can be simple readable text or only machine-readable.
- The content of the message is not defined by the protocol, only the format is.
- Each message sent to the Syslog server has two labels associated with it:
  - The first label describes the function (facility) of the application that generated it.
  - The second label specifies the severity level.
- After these labels, the action is specified, usually a filename in the `/var/log` directory tree where the messages will be stored.

Note: For more detailed information, refer to RFC 5424 for the Syslog protocol specifications.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 20th 2023 (08:11 pm) 
Last Modified Date: June 20th 2023 (08:11 pm)
