---
creation date: August 22nd 2023
last modified date: August 22nd 2023
aliases: []
tags: #📖
---

Primary Categories: [[02 - Foundations]] | [[000 - Cybersecurity Materials]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Web Servers]]  

___
# Overview
Web servers are designed to serve files or data to users over specific network protocols like HTTP. They've grown more complex, supporting new protocols and functionalities.
## Basic Functionality
- Web servers are **applications** that listen on specific network ports.
- They operate over protocols like HTTP/1.1 (ASCII-based) and HTTP/2.0 (binary-based).
- Clients connect and request resources, often via HTTP methods like 'GET /'.
## File Access and Permissions
- Web servers require access to directories like `/var/www/html` on Linux systems.
- In basic setups, they only need **read permissions** to serve files.
- Advanced setups may require **write permissions** but must be carefully controlled to prevent attacks.
## Dynamic Functionality
- Support for dynamic applications and websites (e.g., PHP, Python, etc.).
- Instead of serving static files, they can process and serve dynamic content.
- Common to be paired with databases in stacks like **LAMP (Linux, Apache, MySQL, PHP)**.
## Why Are Web Servers Attractive to Hackers?

1. **Public Exposure**: They are designed to be publicly accessible.
2. **Permission Levels**: May have elevated permissions for file access.
3. **Dynamic Capabilities**: Features like PHP can be exploited to modify functionality.
4. **User Traffic**: High traffic can be hijacked to distribute malicious code.
5. **Database Connection**: Potential to steal sensitive data (e.g., credit cards, passwords).
6. **Lateral Movement**: Can be used as a stepping stone to access other network resources.
7. **Multi-Site Hosting**: A single compromised server can affect multiple hosted websites.
### Important Terms

- **Patching**: Updating the web server software to fix known vulnerabilities.
- **Configuration**: The settings and permissions that dictate how the web server operates.
- **Lateral Movement**: The practice of moving from one system to another within a network.
- **Pivoting**: Technique used by attackers to route traffic through a compromised host to attack other hosts.
## Best Practices

- **Regular Patching**: Keep the web server updated.
- **Secure Configuration**: Only grant necessary permissions.
- **Monitoring**: Regularly monitor logs and traffic.
- **Follow Mainstream Practices**: Use well-known security configurations rather than custom solutions.

🔑 **Key Points**
- Understanding web server functionalities and configurations is crucial for security.
- Being aware of why web servers are attractive targets can help in implementing robust security measures.




___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 22nd 2023 (08:11 pm) 
Last Modified Date: August 22nd 2023 (08:11 pm)
