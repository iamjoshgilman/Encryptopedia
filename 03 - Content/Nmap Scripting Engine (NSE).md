---
creation date: April 5th 2023
last modified date: April 5th 2023
aliases: []
tags: #📖
---

Primary Categories: [[05 - INE eJPT Notes]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[Nmap Scripting Engine (NSE)]]  
---
## Basic Nmap Script Usage
```bash
nmap --script <script> <target>
```

### Examples:
```bash
nmap --script http-title 192.168.1.1
```
```bash
nmap --script smb-os-discovery 192.168.1.0/24
```

## Script Categories
- auth
- broadcast
- brute
- default
- discovery
- dos
- exploit
- external
- fuzzer
- intrusive
- malware
- safe
- version
- vuln

### Examples:
```bash
nmap --script "auth and safe" <target>
```
```bash
nmap --script "discovery and version" <target>
```

## Script Arguments
```bash
nmap --script <script> --script-args <arg1=value1,arg2=value2> <target>
```

### Examples:
```bash
nmap --script http-form-brute --script-args "userdb=users.txt,passdb=pass.txt" <target>
```
```bash
nmap --script dns-zone-transfer --script-args "dns-zone-transfer.domain=example.com" <target>
```

## Updating Nmap Scripts
```bash
nmap --script-updatedb
```

# Some Useful NSE Scripts
---
### Vulnerability Scanning
```bash
nmap --script vuln <target>
```
---
### Banner Grabbing
```bash
nmap -sV --script=banner <target>
```
---
# SMB Enumeration
---
```bash
nmap --script smb-enum-shares -p 445 <target>
```
### Identify SMB Protocol Dialects
```bash
nmap --script smb-protocols -p 445 <target>
```
### Find SMB Security Level Information
```bash
nmap --script smb-security-mode -p 445 <target>
```
### Enumerate Active Sessions
```bash
nmap --script smb-enum-sessions -p 445 <target>
```
### Enumerate Shares
```bash
nmap --script smb-enum-shares -p 445 <target>
```
### Enumerate Windows Users
```bash
nmap --script smb-enum-users -p 445 <target>
```
### Enumerate Domains
```bash
nmap --script smb-enum-domains -p 445 <target>
```
### Enumerate Services
```bash
nmap --script smb-enum-services -p 445 <target>
```

---

### SSL/TLS Vulnerabilities
```bash
nmap --script ssl-enum-ciphers -p 443 <target>
```
---
### Heartbleed Vulnerability
```bash
nmap --script ssl-heartbleed -p 443 <target>
```
---
### Web Server Scanning
```bash
nmap --script http-* -p 80,443 <target>
```
---
### Script Help
```bash
nmap --script-help <script>
```
---
### Example:
```bash
nmap --script-help http-title
```
---




___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: April 5th 2023 (08:32 pm) 
Last Modified Date: April 5th 2023 (08:32 pm)
