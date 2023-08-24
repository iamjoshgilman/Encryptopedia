---
creation date: June 16th 2023
last modified date: June 16th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Security Fundamentals]] [[000 - Global Index]]
Secondary Categories: [[02 - Networking]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Ports and Protocols]]  
---

In computer networking, a port is a communication endpoint. At the software level, a port identifies a specific process or a type of network service. The port numbers are divided into three ranges; well-known ports, registered ports, and private ports.

- **Well-known ports** range from 0 to 1023. This is where some of the most common ports are, such as FTP, SSH, DNS, and HTTPS. We will cover more of these below.
- **Registered ports** range from 1024 to 49151.
- **Private ports** range from 49152 to 65535. These are typically used for "ephemeral" ports, which is the name given to the source port used by a client in a server-client communication. For example, if we're connecting to a web server on port 443 HTTPS (destination port) then our source port would be a random port between 49152 to 65535.

| Port | Description | How to connect/use |
| --- | --- | --- |
| `21` | FTP (File Transfer Protocol) | FTP client such as lftp or ftp |
| `22` | SSH (Secure Shell) | SSH client such as OpenSSH or PuTTY |
| `23` | Telnet protocol | Telnet client such as Netcat or Telnet command |
| `25` | SMTP (Simple Mail Transfer Protocol) | Command line mail client such as mailx or mutt |
| `53` | DNS (Domain Name System) | DNS client such as dig or nslookup |
| `80` | HTTP (Hypertext Transfer Protocol) | Command line web client such as curl or wget |
| `110` | POP3 (Post Office Protocol 3) | Command line mail client such as mailx or mutt |
| `119` | NNTP (Network News Transfer Protocol) | NNTP client such as Newsx or nntpcat |
| `123` | NTP (Network Time Protocol) | NTP client such as ntpdate or chronyc |
| `139` | NetBIOS Session Service | Netcat or smbclient |
| `143` | IMAP (Internet Message Access Protocol) | Command line mail client such as mailx or mutt |
| `161` | SNMP (Simple Network Management Protocol) | SNMP client such as snmpwalk or snmpget |
| `389` | LDAP (Lightweight Directory Access Protocol) | ldapsearch or ldapwhoami |
| `443` | HTTPS (Hypertext Transfer Protocol Secure) | Command line web client such as curl or wget |
| `445` | SMB (Server Message Block) | Netcat or smbclient |
| `1433` | Microsoft SQL Server | tsql or sqlcmd |
| `3306` | MySQL database system | mysql or mysqldump |
| `3389` | RDP (Remote Desktop Protocol) | rdesktop or FreeRDP |

## **Port 20, 21 - File Transfer Protocol (FTP)**

This protocol is used to transfer files between systems, where users can connect to an FTP product and can view, upload, or download them. An example of usage would be a company using a server for file storage, where employees can connect in via FTP and retrieve files. FTP is extremely insecure as the communication is in clear text, including the username and password used, which can easily be captured by attackers that are listening to network traffic.

## **Port 22 - Secure Shell (SSH)**

SSH allows users to connect to a remote host, such as a server if they have SSH open. This channel is encrypted, so any data moved between two connected systems will not be clearly visible. An example of usage would be an IT technician using SSH to connect to a server from their desktop to carry out maintenance.

## **Port 23 - Telnet**

This service was used before SSH and offers the same functionality, however, Telnet does not use encryption, so the traffic can be captured and read by an attacker. Telnet should not be used due to this weakness, and SSH should always be implemented instead.

## **Port 25 - Simple Mail Transfer Protocol (SMTP)**

This protocol is used to send emails between servers within the network, or to external networks, such as over the internet. This is just a transport method, to actually download and view emails you need to use an email client and the protocol POP or IMAP.

## **Port 53 - Domain Name System (DNS)**

DNS operates on TCP and UDP ports 53 and uses relational databases to convert human-readable hostnames and domain names (such as Google.com) into their respective IP addresses so that communications can be sent to and from these hosts. The reason we use domain names is that they're easy to remember. You remember **securityblue.team**, but you probably won't remember **3.9.68.12**!

## **Port 67, 68 - Dynamic Host Configuration Protocol (DHCP)**

DHCP is designed to assign IP address-related information to any hosts on the network automatically, such as the subnet mask and IP address. When you connect your phone to your network, it is assigned an IP on the network because of the dynamic host configuration protocol. DHCP uses 2 ports; UDP port 67 and UDP port 68.

## **Port 80 - Hypertext Transfer Protocol (HTTP)**

HTTP allows clients (browsers such as Chrome and Firefox) to connect to web servers and request content, which appears in the form of file downloads, web pages, and streaming services. So if you want to view the securityblue.team homepage, your browser will make an HTTP request to our web server, requesting to download the HTML web page. The server will respond with a 200 status code (which means "OK", it has been successful) and then send the HTML page to the client, so you can view it on your screen. As HTTP is not encrypted, it is possible to conduct sniffing attacks and see cleartext data as it is transmitted between the client and the server, such as passwords.

## **Port 443 - Hypertext Transfer Protocol Secure (HTTPS)**

HTTPS is a secure version of HTTP and has the same functionality of retrieving content from web servers. However, the difference between the two is that HTTPS uses encryption to protect the transfer of data between a web server and a client. How do you turn HTTP into HTTPS? You need to use Transport Layer Security (TLS) formerly known as Secure Socket Layer (SSL). Sites that use HTTPS are less susceptible to man-in-the-middle and sniffing attacks.

## **Port 514 - Syslog (UDP)**

A Syslog server will have port 514 open and listening for incoming Syslog notifications, transported by UDP protocol packets. These packets are generated by remote systems that have been set up to forward Syslog information to the server. This is typically used to send information about IT systems to a SIEM platform so that devices can be monitored for security events or issues.





___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 16th 2023 (10:19 am) 
Last Modified Date: June 16th 2023 (10:19 am)
