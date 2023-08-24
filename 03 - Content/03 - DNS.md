---
creation date: August 22nd 2023
last modified date: August 22nd 2023
aliases: []
tags: #📖
---

Primary Categories: [[03 - Network Fundamentals]] | [[02 - Networking]] 
Secondary Categories: [[01 - Administration]] | [[000 - Global Index]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - DNS]]  

___
# Overview

**DNS** is essentially the phonebook of the internet. It translates human-readable domain names into IP addresses so that browsers can load resources.
## Key Concepts

### 1. Purpose of DNS
- It **translates domain names** (e.g., google.com) to IP addresses (e.g., 192.168.1.1 or fd15:611d:d0dd:0209:xxxx:xxxx:xxxx:xxxx for IPv6).
- This translation is crucial because humans find it easier to remember names rather than long strings of numbers, especially with the complexity of IPv6 addresses.
### 2. DNS Configuration
- Every computer must have a **DNS server configured** in its network settings.
- Typically, an **Internet Service Provider (ISP)** will provide a DNS server or pre-setup a router to use one.
- If using a router, the router often employs **DHCP (Dynamic Host Configuration Protocol)** to instruct every computer on the network about which DNS server to use.
### 3. DHCP and DNS
- **DHCP** is responsible for dynamically assigning IP addresses to devices on a network.
- In cases where a separate DHCP server exists (e.g., in business environments), the DHCP functionality on the router should be disabled to prevent conflicts.
- Without a DHCP-enabled router, users might need to manually find a DNS server (like Google's or OpenDNS) and configure each device's network settings.
### 4. Browser Interaction with DNS
- Upon entering a domain name into a browser:
  1. The computer sends a **request to the configured DNS server**.
  2. The DNS server responds with the **corresponding IP address**.
  3. The browser sends an HTTP request to that IP address, typically over port **80** (for HTTP) or **443** (for HTTPS).
## Things to Remember:
1. **DNS** translates domain names to IP addresses, enabling browsers to retrieve web resources.
2. Every device needs a configured DNS server, often provided by the ISP or set manually.
3. **DHCP** can dynamically assign IP addresses and DNS server details to devices on a network.
4. For web browsing, once the domain name's IP address is known, HTTP requests can be made to ports 80 or 443.

🔑 **Key Point**: Always ensure the correct DNS configuration to maintain stable internet connectivity. Familiarize yourself with the relationship between DNS and DHCP and understand the steps a browser takes to retrieve a web page using DNS.

___
# TLD - Authoritative Name Servers - Caching

## 1. DNS Hierarchical Structure
- The **Domain Name System (DNS)** operates hierarchically.
- No single server holds all domain-related data; it's a collaborative and distributed effort.
- This hierarchy ensures resilience and robustness, preventing one single point of failure from crashing the entire system.
## 2. Top-Level Domains (TLD)
- **Definition**: The final segment of a domain name.
- Examples:
  - In `google.com`, the TLD is `.com`.
  - In `google.co.uk`, the TLD is `.co.uk`.
- Role of TLD:
  - Dictates which DNS server to consult first.
  - The server for the TLD won't have the exact IP address but will direct to the appropriate name server that does.
## 3. Authoritative Name Servers
- **Definition**: A DNS server that maintains and controls the actual domain-to-IP mapping for specific domains.
- If we consider the example domain `thisisnotarealdomain.fake`:
  - Suppose its IP address is `192.168.0.6`.
  - The authoritative name server for this domain (referred by `.fake` TLD) might have the IP `192.168.0.100`.
  - This server is the definitive source for the mapping between `thisisnotarealdomain.fake` and its IP.
  - All DNS queries for this domain's IP will be referred to this authoritative server, making it the final word for that domain's mapping.
## 4. Caching and DNS
- **Purpose**: Enhances the efficiency of DNS lookups.
- **How it works**:
  - After an initial DNS lookup, a name server can store/cache the result.
  - This cached result can be used for subsequent requests to the same domain.
  - Periodically, this cache is cleared or updated to reflect potential changes in domain-to-IP mappings.
  - It reduces the constant need to consult the authoritative name server, reducing traffic and improving response times.
## Key Points to Remember:
1. **TLDs** guide the initial step in DNS queries by pointing to the right starting server.
2. **Authoritative Name Servers** are the final reference points for specific domain-to-IP mappings.
3. **Caching** is a crucial efficiency strategy in the DNS system, reducing repeated queries to authoritative servers and speeding up domain resolution for users.

🔑 **Pro-tip**: When encountering DNS resolution issues, it's sometimes beneficial to flush or clear the DNS cache to ensure you're getting the most up-to-date mapping.

___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 22nd 2023 (07:11 pm) 
Last Modified Date: August 22nd 2023 (07:11 pm)
