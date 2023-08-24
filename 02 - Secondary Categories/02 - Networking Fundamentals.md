---
creation date: February 17th 2023
last modified date: February 17th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Administration]] | [[000 - Global Index]]
Secondary Categories: [[02 - Networking]] 
Links: [[]] 
Search Tag: #📖  

# [[02 - Networking Fundamentals]]  

[[03 - TCP Protocol]]
[[03 - UDP Protocol]]
[[03 - Ports and Protocols]]

[[03 - How Email Works]]
[[03 - Email Spoofing, SPF and DKIM]]

[[03 - DNS]]
[[03 - DNS Records]]
[[03 - DNS Lookups]]

[[03 - ICMP]]
[[03 - DHCP]]
[[03 - ARP]]
# OSI/TCP Model

- **OSI (Open Systems Interconnection) Model**: A conceptual framework used to understand how different networking protocols interact across various layers.
- **Layers**: 7 distinct layers, from high-level application interactions to low-level physical transmissions.

- ##### Please Do Not Throw Sausage Pizza Away
# OSI Model Layers

- ### Layer 7: Application Layer
	- Role: Interface for end-users and applications
	- Example: HTTP, FTP.
	- Key Point: Handles specific communication functions for applications.

- ### Layer 6: Presentation Layer
	- Role: Transforms data to/from the application layer.
	- Example: XML, JSON.
	- Key Point: Manages encryption, character encoding, and data compression.

- ### Layer 5: Session Layer
	- Role: Establishes, maintains, and terminates sessions.
	- Key Point: Manages connections, but note that some functions, like those of TCP, cross over into the transport layer.

- ### Layer 4: Transport Layer
	- Role: Ensures data transfer is reliable and manages end-to-end connections.
	- Example: TCP, UDP.
	- Key Point: It's where headers for TCP or UDP are added.

- ### Layer 3: Network Layer
	- Role: Responsible for determining the best path to route data across networks.
	- Example: IP (Internet Protocol).
	- Key Point: IP headers are added here.

- ### Layer 2: Data Link Layer
	- Role: Deals with communication between adjacent network nodes.
	- Key Point: Manages MAC addresses and encoding/decoding into bits. Ethernet frames or other protocols are used at this layer.

- ### Layer 1: Physical Layer
	- Role: Manages transmission/reception of raw binary data.
	- Key Point: Deals with the physical connection, converting data to electrical signals or vice versa.

![[Pasted image 20230822201817.png]]

# TCP/IP Model

## Overview:
- **TCP/IP Model**: A simplified, more practical framework for network communication, which combines certain layers from the OSI model. Often referred to as the Internet protocol suite.
- **Layers**: 4 distinct layers, focusing on the functions needed to transmit data over the internet.
## TCP/IP Model Layers:

- ### **Layer 4: Application Layer**
	- Role: Interface for end-users and applications. Includes functionality of the application, presentation, and session layers of the OSI model.
	- Example: HTTP, FTP, SMTP, DNS.
	- Key Point: This layer deals with end-to-end communication services for applications.
  
- ### **Layer 3: Transport Layer**
	- Role: Responsible for ensuring end-to-end communication, reliability, and data integrity.
	- Example: TCP, UDP.
	- Key Point: Manages flow control, error correction, and data segmentation. It's where the headers for TCP or UDP are added.

- ### Layer 2: Internet Layer
	- Role: Routing of data across networks and interconnecting networks.
	- Example: IP (Internet Protocol), ICMP, ARP.
	- Key Point: It's responsible for addressing, packaging, and routing functions.

- ### **Layer 1: Network Access Layer**
	- Role: Deals with hardware elements and the local network setup.
	- Key Point: Manages physical connectivity, framing, error detection, and link management. It's a combination of the OSI's physical and data link layers.
## Differences from OSI Model:
- **Layer Grouping**: TCP/IP model combines the functionalities of certain OSI layers to form a more streamlined model.
- **Terminology**: While OSI uses more generalized terms, the TCP/IP model uses names closely related to the core protocols it's built upon.
- **Focus**: TCP/IP is more focused on the practical aspects of transmitting data on the internet, while OSI provides a broader theoretical framework.
## Things to Remember:
1. **Unified Layers**: Unlike OSI, the TCP/IP model combines certain functionalities into a single layer, making it more concise.
2. **Wide Adoption**: Given the vast adoption of TCP and IP in real-world networking, this model has a more practical slant.
3. **Functionality Overlap**: The layers in the TCP/IP model might feel similar to those in the OSI model, but remember that they might encompass functionalities from multiple OSI layers.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: February 17th 2023 (07:25 pm) 
Last Modified Date: February 17th 2023 (07:25 pm)
