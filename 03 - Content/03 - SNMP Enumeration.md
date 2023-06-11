---
creation date: June 7th 2023
last modified date: June 7th 2023
aliases: []
tags: #📖
---

Primary Categories: [[03 - Network Service Discovery]] 
Secondary Categories: 
Links: [[]] 
Search Tag: #📖  

---
# SNMP - Simple Network Management Protocol
---

## Overview

The Simple Network Management Protocol (SNMP) is a protocol used for managing devices on IP networks. Devices that typically support SNMP include routers, switches, servers, workstations, printers, modem racks, and more.

## Uses of SNMP

SNMP is used for:

1. **Collecting information**: SNMP is commonly used to monitor and manage network performance, find and solve network issues, and plan for network growth.
2. **Modifying and applying new configurations** to the network devices.

## Components of SNMP

1. **SNMP Manager**: Also known as Network Management System (NMS). This is a centralized system used to monitor, control, and configure devices on a network.

2. **SNMP Agent**: This is a software management component that resides in the managed device. The agent collects the information from the managed device in the form of SNMP MIBs and stores it locally.

3. **Management Information Base (MIB)**: This is a virtual database containing the specifications of the different aspects of the device that can be managed.

## SNMP Versions

SNMP has three versions:

1. **SNMPv1**: The original version, which operates over protocols such as User Datagram Protocol (UDP), Internet Protocol (IP), AppleTalk Datagram-Delivery Protocol (DDP), and Novell Internet Packet Exchange (IPX). SNMPv1 has a few security features.

2. **SNMPv2**: Has enhancements over SNMPv1 in terms of performance, security, and manager-to-manager communications. However, SNMPv2 does not define a single security mechanism, leading to the development of SNMPv2c and SNMPv2u.

3. **SNMPv3**: This version introduces a full-fledged security system. It supports authentication (prevents unauthorized access), privacy (encrypts data to prevent snooping), and integrity (ensures that the data is not tampered during transit).

## Security

SNMPv1 and SNMPv2c use a community-based form of security. The information is transmitted in plaintext, and anyone can read it if they know the community string, which acts like a password.

SNMPv3, however, enhances security with encryption and user authentication.

## SNMP Enumeration

SNMP enumeration is the process of using SNMP to enumerate user accounts or devices on a network. This could help attackers identify potential targets. Therefore, it is crucial to secure SNMP to prevent unauthorized access.

## Tools for SNMP Enumeration

1. [[04 - snmpwalk]]: A tool for "walking" through the MIB tree of an SNMP enabled device.

2. [[04 - snmp-check]] : Allows you to enumerate the SNMP devices and places the output in a very human readable friendly format.

3. [[04 - onesixtyone]] : An SNMP scanner that sends multiple SNMP requests to multiple IP addresses, trying different community strings and waiting for replies.

Please remember that these tools should only be used in a legal and authorized context. Unauthorized network scanning and device tampering can lead to serious legal consequences.

## Mitigations

1. Use SNMPv3, which provides better security than previous versions.
2. Disable SNMP if not required.
3. Regularly update and patch SNMP agents and managers.
4. Limit SNMP access to a small number of IP addresses.
5. Use complex, hard-to-guess community strings (for SNMPv1 and SNMPv2c) and credentials (for SNMPv3).
6. Use firewalls to limit access to the SNMP agents.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 7th 2023 (09:51 pm) 
Last Modified Date: June 7th 2023 (09:51 pm)
