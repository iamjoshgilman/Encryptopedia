---
creation date: March 31st 2023
last modified date: March 31st 2023
aliases: []
tags: #📖
---

Primary Categories: [[05 - INE eJPT Notes]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[DNS Zone Transfers]]  

`DNS Zone Transfer is a misconfiguration allowing us to copy or transfer zone files from primary DNS Server giving us a holistic view of the organizations network layout.`

`Domain Name System (DNS) - Acts as a telephone directory that contains domain names and their corresponding IP addresses.`


### DNS Servers
---
Cloudflare - 1.1.1.1
Google - 8.8.8.8


### DNS Record
---
A - Hostname IPv4
AAAA - Hostname IPv6
NS - Reference to domains name server
MX - Mail server
CNAME - Used for domain aliases
TXT - Text record
HINFO - Host Information
SOA - Domain Authority
SRV - Service Records
PTR - Resolves an IP to a hostname


### DNS Interrogation
---
`DNS interrogation is the process of enumerating DNS records for specific domain, particularly gives us information that is not publicly available`


### Kali Demo
---
Passive
```Bash
dnsrecon -d website.com
```

DNS Zone Transfer - Will give Passive information and will do Active in addition 
```bash
dnsenum website.com
```

DNS Zone Transfer using DiG
```bash
dig axfr @`nameserver` website.com
```


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: March 31st 2023 (07:36 am) 
Last Modified Date: March 31st 2023 (07:36 am)
