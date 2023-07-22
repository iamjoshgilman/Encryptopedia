---
creation date: June 15th 2023
last modified date: June 15th 2023
aliases: []
tags: #📖
---

Primary Categories: [[03 - Network Fundamentals]] [[000 - Global Index]]
Secondary Categories: [[02 - Networking]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Network Fundamentals]]  
---

### Transmission Control Protocol (TCP)
- ==Connection-oriented protocol== that allows two systems to establish a connection that will enable the two-way transmission of data. Any ==data loss is detected and automatically corrected==, which is why TCP is a ==reliable protocol==. TCP works at the ==transport layer in the OSI model==. The term TCP/IP protocol stack is also commonly used to refer to the Internet protocol suite since the== ==TCP protocol is almost always based on the Internet protocol (IP)== and this connection is the foundation for the majority of public and local networks and network services.

- Systems communicate with each other using TCP through a process referred to as the "==three-way handshake==". To start, both systems must have unique IP addresses and have assigned and enabled the port for the data transfer. The IP address works as a primary identifier, while the specified port allows the operating system to assign connections to the specific client and server programs.
	1. The requesting client sends the server an SYN (==synchronize==) packet with a random number, which ensures that data is sent in the right order and nothing is missed.
	2. The server receives the packet and accepts the connection by sending an SYN-ACK (==synchronize acknowledgment==) packet back to the client, including the client's sequence number plus 1. It also transmits its own sequence number to the requesting client.
	3. Finally, the **client** acknowledges the receipt of the SYN-ACK segment by sending its own ==**ACK packet**==, which in this case contains the server's sequence number plus 1. At the same time, the client can already begin transferring data to the server.
![[Pasted image 20230615213521.png]]

### User Datagram Protocol (UDP)
- Allows ==datagrams== to be sent ==without connection== in IP-based networks. To achieve the desired services on the target hosts, it uses ports that are listed as one of the core components in the UDP header. Like many other network protocols, UDP belongs to the internet protocol family, where it is classified as a mediator between the network layer and the application layer at the transport level.
	1. ==**UDP is connectionless**==: Data transport via UDP is characterized by the fact that it takes place without an existing connection between addressee and recipient. The respective packets are then sent to the preferred IP address, **specifying the target port**, without the computer behind them having to respond. However, if packets are also to be returned to the recipient, the UDP header can optionally also contain the source port.
	2. **UDP uses ports**: Like TCP, UDP uses ports so that the packets are transferred to the correct subsequent protocols or the desired applications on the target system. The ports are defined by numbers according to the proven pattern, with numbers between 0 and 1023 assigned to fixed services.
	3. ==**UDP enables fast, delay-free communication**==: The transport protocol is suitable for fast data transmission ==due to the lack of connection setup==. This also results from the fact that the loss of individual packets only affects the quality of the transmission. With TCP connections, on the other hand, lost packets are automatically re-requested, causing the entire transmission process to come to a standstill.
	4. ==**UDP does not guarantee the security and integrity of the data**==: The absence of mutual authentication between addressee and recipient ensures the excellent transmission speed of UDP – however, the protocol can neither guarantee the completeness nor the security of the data packets. The correct sequence of the sent packets is also not guaranteed. For this reason, the services that use UDP must provide their own measures for correction or protection.

###  Internet Control Message Protocol (ICMP)
- Internet layer protocol used by network devices to ==diagnose network communication issues==. ICMP is mainly used to determine whether or not data is reaching its intended destination in a timely manner. Commonly, the ICMP protocol is used on network devices, such as routers.

### IP Addresses (IP)
- Provides an identity to a networked device on the internet. Similar to a home or business address that supplies a specific physical location with an identifiable address, devices on a network are differentiated from one another through IP addresses.
- #### **Private IP Addresses**
	- These are used inside a network, for example, a home network that is used by tablets, Wi-Fi cameras, wireless printers, and desktop PCs. These types of IP addresses provide a way for devices to communicate with a router and the other devices on the private home network. Private IP addresses can be set manually or assigned automatically by the router. The private IP ranges are:
		- **192.168.0.0 - 192.168.255.255** (65,536 IP addresses)
		- **172.16.0.0 - 172.31.255.255** (1,048,576 IP addresses)
		- **10.0.0.0 - 10.255.255.255** (16,777,216 IP addresses)
- #### **Public IP Addresses**
	- These are used on the outside of a network and are assigned by an Internet Service Provider (ISP). It's the main address that a home or business network uses to communicate with the rest of the networked devices around the world
- #### **Static and Dynamic IPs**
	- Both private IP addresses and public IP addresses are either dynamic or static, they either change or they don't.
	- An IP address that is ==assigned by a DHCP server is a dynamic== IP address. If a device doesn't have DHCP enabled or doesn't support DHCP, then the IP address must be ==assigned manually==, in which case it's called a ==static IP== address.

### MAC Address
- hardware identification number that uniquely identifies each device on a network. The MAC address is manufactured into every network card, such as an Ethernet card or Wi-Fi card, and therefore cannot be changed (but it can be spoofed by attackers!). MAC addresses are made up of six two-digit hexadecimal numbers, separated by colons. 
	- For example, an Ethernet card may have a MAC address of 00:0d:83:b1:c0:8e.
	- We can view the MAC of our interface card in Windows by searching for "Network Status" in the Windows search bar, then clicking on "View your network properties".




___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 15th 2023 (09:08 pm) 
Last Modified Date: June 15th 2023 (09:08 pm)
