---
creation date: June 7th 2023
last modified date: June 7th 2023
aliases: []
tags: #📖
---

Primary Categories: [[03 - Network Service Discovery]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

---
# HTTP/HTTPS Enumeration
---

## Overview

HTTP (Hypertext Transfer Protocol) and HTTPS (HTTP Secure) are protocols for transmitting hypermedia documents, such as HTML. They are the foundation of data communication on the World Wide Web. HTTP operates at the highest layer of the TCP/IP model, the Application layer; as does HTTPS, which secure HTTP communication with SSL/TLS encryption.

## HTTP/HTTPS Enumeration

HTTP/HTTPS Enumeration is a process carried out to gather information about a target that is hosting a web service. This could include identifying server and application vulnerabilities, directory structures, and important files.

## Steps for HTTP/HTTPS Enumeration

1. **Banner Grabbing**: Identify the web server and version.

```bash
curl -I http://192.168.1.1
```

2. **HTTP Methods Testing**: Discover the HTTP methods (GET, POST, HEAD, PUT, DELETE, etc.) that the server allows.

```bash
nmap -p 80 --script http-methods 192.168.1.1
```

3. **Directory and File Enumeration**: Check for hidden directories and files that might contain sensitive information.

4. **Identify application entry points**: Analyzing the website to identify all possible places where input can be provided.

5. **Input Validation**: Check how the application responds to various inputs. This could potentially identify points vulnerable to attacks like SQL Injection or Cross Site Scripting (XSS).

6. **Session Management**: Understand how sessions are managed. Look for vulnerabilities in cookies and session tokens.

7. **Error code interpretation**: Analyzing error codes to gain more information about the server and its configuration.

## Tools for HTTP/HTTPS Enumeration

- [[04 - Nmap|Nmap]] : Used for scanning the target server. Nmap scripts can identify the server, open ports, running services, and more.

- [[04 - FFUF|FFUF]] / [[04 - GoBuster|GoBuster]] : Tools for brute forcing directories and files.

- [[04 - Nikto|Nikto]] : An open-source web server scanner which can perform comprehensive tests against web servers for multiple items, including potentially dangerous files and outdated versions.

- [[04 - Burp Suite|Burp Suite]] : A platform for performing security testing of web applications. Its tools work seamlessly together to support the entire testing process.

## Mitigation strategies against HTTP/HTTPS Enumeration

- Regularly update and patch web servers and applications.

- Remove or secure potentially sensitive information, directories, and files.

- Implement a Web Application Firewall (WAF) to block malicious requests.

- Configure servers to prevent the disclosure of sensitive information in error responses.

- Use HTTPS instead of HTTP to secure the communication.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 7th 2023 (09:20 pm) 
Last Modified Date: June 7th 2023 (09:20 pm)
