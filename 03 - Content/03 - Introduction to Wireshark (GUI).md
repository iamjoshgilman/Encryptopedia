---
creation date: June 22nd 2023
last modified date: June 22nd 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Incident Response]] | [[000 - Global Index]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Introduction to Wireshark (GUI)]]  
---

The GUI can be categorized into two screens

- _**Startup Window**_, which is displayed when Wireshark is launched.
- _**Main Window**_, which is displayed when a capture has been started or loaded.

You do not need to learn all of the settings and options, but knowing the major options will allow you to use Wireshark for network analysis with relative ease.

**Wireshark Startup Window**

The Startup Window is the screen that pops up when the user starts Wireshark. It allows the user to start or load a network traffic capture and configure some capture settings.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/ca2495e39970523c38ef459847a05a57a2669352a61dc358518295e76b8aef1cfe664665dbd33edf62db3c7c86ee.png)

**[1] Start Capture**: The blue button in the top left corner starts capturing inbound and outbound packets, with the specified capture filters, on the specified interface.

 **[2] Open Saved Files**: Wireshark traffic capture files can be saved in several formats, such as .cap, .pcap or .pcapng, and can be opened in the Main Window for analysis.

  **[3] Capture Filter**: You can write expressions in the capture filter to limit the types of packets that Wireshark captures. For example, if you specify the **not arp** capture filter, Wireshark avoid capturing Address Resolution Protocol packets. Details on how to construct capture filters are described in the next section. Capture filters can be saved for reuse at a later time.

  **[4] Capture Interface Selection**: Wireshark lists all available interfaces that it can capture on, with a graph of the recent network activity on each of those interfaces. You can select an interface that you want to capture traffic on, such as en0 for Wi-Fi traffic and vboxnet0 for virtual network traffic, in the above image.

It is recommended that promiscuous mode be turned on for capturing interfaces. Promiscuous mode allows Wireshark to capture packets that are received on an interface but not actually addressed to the host, for example, frames transmitted on a wireless network with different MAC addresses. This allows Wireshark to capture other hosts’ traffic and have a broader picture of the network. 

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/4f8e5b0b33cb3ae174bd31251adb3a619e88253ce54393e33ac961549a1a303250911a07da8aae1d88d7c1c2b065.png)

Promiscuous mode can be managed by clicking on the cog-shaped button in the top menu bar, and toggling the setting for a specific interface or for all interfaces.

**Wireshark Main Window**

The Main Window is where all of the capturing and analysis happens. There are dozens upon dozens of options, parameters, statistics, and detailed information available on the traffic being captured. The user can view the network traffic, from the individual bytes of a single packet to a statistical overview of protocols within the capture.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/46e38f7feacec7d093b4f5a6d33175eaa2299be0e8362611f90b19f47612060bef22b7195847e21ac42218addec7.png)

 **[1] Menu Bar**: The menu bar located at the top of the window is used to manage the capture. In the far left section, you can start, stop and restart the capture, and manage capture interface settings. In the next section, you can open, save and close the capture file. The magnifying glass icon is used to find a specific packet using a display filter or by a string or bytes within the packet. 
 
  **[2] Display Filter**: The display filter is used to display only specified packets. You can construct an expression by specifying header fields and optionally, the values that they should match. Logical operators can also be used to chain expressions. If a packet contains the specified header field, or if the header field has a value that is specified, the packet will be shown in the packet list – otherwise, it will not be shown. 

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/eaaa212cf6b2e83afe9658d7023b06da8a7a78ad1d56cec4b682e30df0bc3a7a614d22c5c10f2ca27832a46a19ff.png)

For example, in the capture above, a display filter of `ip.src_host == 192.168.1.7 and tcp.port == 443 and ssl.record.version == 0x0303` has been applied. The first statement matches packets with a source IP address of 192.168.1.7. The second statement matches packets with a source or destination TCP port 443 (SSL/TLS). The third statement matches packets that are using TLS version 1.2. The three statements are conjoined by the ‘**and**’ logical operator, which means a packet must satisfy all three of those statements for them to be displayed in the packet list. A more in-depth look at the display filter is described in upcoming sections.

**[3] Panes**: The Wireshark Main Window has three main panes: packet list, packet headers and the hex dump and ASCII representation of the packet bytes. 

**[4] Packet List**: The packet list aggregates major information on the packets that Wireshark captures, in columns. Generally, the packet list should display the packet number (the later the packet was captured, the higher this number is), time since the start of capture, the source and destination IP addresses, the protocol, the packet length and a summary of the packet headers or contents. You can easily get a picture of the network flow and protocol conversations being captured.

**[5] Packet Headers**: The packet headers section provides a wealth of information on each individual packet, and organizes packet header fields and values in layers of easy-to-view drop-down menus – from Layer 1 frame information to Layer 7 protocol contents. 

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/188d3f8e5b5a9fec074a706a0db9235c832b9c5fda571acb6378c503fc76e6528bce9504341f983db209bf76f007.png)

The above image shows the sheer amount of detailed information Wireshark organizes and displays on a single DNS query response. You can see the source and destination MAC & IP addresses and UDP ports, DNS flags and DNS query response answers in full detail.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/5d368831c6676e2778c7a63b7473dbebac71999b23cca33c3a5ae11c50718de66c34dd8ded7d533971fe88e82fdf.png)

- **Hex Dump & ASCII**: On the bottom pane, you can see the hexadecimal and ASCII representation of the entire packet.

Hovering over the hex dump or ASCII highlights a section of the packet and displays what field of the packet is being highlighted on the bottom bar. In the above image, the TCP sequence number has been highlighted. You may also notice that the expression for the field is also displayed – in this case, **tcp.seq**. This is especially helpful when you are constructing display filters and do not know the specific Wireshark term for specifying a certain packet field.

This section covered the basic GUI fields in Wireshark’s Startup & Main windows and what each one of them does. In the following sections, with the basic knowledge of the Wireshark GUI at hand, we will take a look at capturing live network traffic and analyzing .pcap capture files.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 22nd 2023 (12:04 pm) 
Last Modified Date: June 22nd 2023 (12:04 pm)
