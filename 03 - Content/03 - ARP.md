---
creation date: August 22nd 2023
last modified date: August 22nd 2023
aliases: []
tags: #📖
---

Primary Categories: [[03 - Network Fundamentals]] | [[02 - Networking]] 
Secondary Categories: [[01 - Administration]] | [[000 - Cybersecurity Materials]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - ARP]]  

___
# ARP (Address Resolution Protocol)

## Overview
ARP (Address Resolution Protocol) resolves the MAC address corresponding to a given IP address. It's crucial for data transfer in local networks because Ethernet frames require both source and destination MAC addresses.
## The ARP Problem
**Scenario**: Computer A (`192.168.0.5`) wants to send data to Computer B (`192.168.0.10`), but Ethernet requires Computer B's MAC address as the destination.

**Question**: How does Computer A find out the MAC address of Computer B?
## The ARP Solution

### Local Network

1. **Broadcast Request**:
    - Computer A sends a broadcast request to everyone on the local network, asking for the MAC address corresponding to `192.168.0.10`.
2. **Reply**:
    - Computer B replies with its MAC address.
3. **ARP Table**:
    - Computer A stores this IP-to-MAC mapping in its ARP table for future use.
### Internet Access

- For internet-bound traffic, Computer A needs the MAC address of the router/gateway.
- If not in the ARP table, Computer A will use ARP to find the MAC address of the router.

🔑 **Key Point**: ARP is restricted to local network queries. For addresses outside the local network, the query is directed to the router.
## ARP Table
A cache that stores IP-to-MAC address mappings so that the computer doesn't have to broadcast an ARP request each time it needs to know the same MAC address.
## Things to Remember:

1. **ARP for Local Network**: Solves the problem of finding the destination MAC address in a local network.
2. **ARP Table**: Caches IP-to-MAC mappings.
3. **Internet-bound Traffic**: For external IP addresses, the MAC address of the router is needed.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 22nd 2023 (08:07 pm) 
Last Modified Date: August 22nd 2023 (08:07 pm)
