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

# [[03 - Introduction to Wireshark (Analysis)]]  
---

As described in the previous sections, the display filter controls which packets are shown in the packet list. This significantly improves the ease of traffic analysis, as important traffic can be separated from the general noise in the network. To filter by the presence of a protocol or header field in a packet, the expression should specify only the protocol or header field, e.g.

- **udp** to display only UDP packets, and
- **http.request** to display only HTTP requests

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/6788d7599cb25c8cb46e4df3aedc311edaab99a0ffb7c93a759cf0df0938766ebd7d0ca6d44b9f76e276243e90a0.png)

To filter by the values of header fields, you can specify the header field, then a comparison operator, and then the value that it should match. For example, `tcp.port == 80` displays packets that have a source or destination port of 80 (HTTP), and `tcp.window_size_value >= 8000` displays TCP packets with a window size of 8000 bytes or over. 

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/e9e5ac7efae8dc605cd83509e06581784925160e009fe80dbb10607c2624d8791ed321c774ed576281088129c463.png)

Multiple filter statements can be chained by using logical operators, including `and (&&)` and `(or/||)`. For example, to display TCP packets addressed to 192.168.1.7, you can use `ip.dst_host == 192.168.1.7 && tcp`, and to display either NTP traffic or UDP traffic from/to port 20000, you can use `ntp or udp.port == 20000`. The **not** (**!**) operator excludes specific packets from being displayed, such as `not ftp` to exclude FTP packets from being displayed in the packet list. Finally, brackets can be used to group statements together.

# Following Streams & Custom Columns

Imagine you want to analyze an HTTP communication between a web server and a host. You are interested in having a holistic view of the dozens of HTTP requests and responses. In this case, looking at each individual packet will not be of much profit to us – this is where Wireshark’s protocol stream following feature shines. 

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/fec16ef725a9cc211a00109f773828bbec0ba813ad98da34431e6fafecf2d0a1b2affb2dd475c77f8e0932dc6f12.png)

To follow a stream, right-click on a packet within the stream, and click `Follow > TCP/UDP/SSL/HTTP Stream`. Inapplicable streams should be greyed out in the pop-up menu. Wireshark should automatically apply a display filter for the stream and open a new window displaying the contents of the packets in the stream. 

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/fcbcbac30c4298cf552058a16ece4e05811e1e4e75acc3cf65a25c2038524cb64e0f1cf8aaad8771732132172db3.png)

As you can see from the above image of a simple HTTP file download, HTTP requests should be highlighted in red and HTTP responses in blue. You can easily see the request header and the response header and file content. Compared to looking at the request and response packets individually, looking at the stream saves time and effort as the communication is displayed all in one window. 

In addition to following streams, you can view specific packet information in the packet list by customizing the columns in the packet list. 

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/87d11fa8705e761a0de313b5e4d41595520d00180b4127e5e7b58c3228a8f4fdf5816d937f0c7b718ef79411300d.png)

To add a packet header value as a column, right-click the header field and select Apply as Column. In the above image, the SSL content type is applied as a column. The benefit of adding certain header values as a column is the ability for quick visual identification of packets having a specific value that we are interested in.

# Viewing Capture Statistics

Wireshark collects different statistics about the traffic in the capture file – such as the percentage proportions of protocols, the number of bytes transmitted to different hosts, the IP addresses of all the hosts that has appeared in the capture. They are helpful in certain scenarios, such as finding potential exfiltration vectors and identifying the exfiltrating host based on network usage.

**This section will discuss three of the statistics windows:**

- Protocol Hierarchy
- Conversations,
- and Endpoints

## Protocol Hierarchy

The Protocol Hierarchy window displays the percentages of the number of packets or bytes in a protocol conversation against the entire traffic. The protocols are organized in layers from Layer 2 to Layer 7. The below image shows:

- 99.7% of the traffic captured were IPv4 packets
- 96.6% being TCP, and
- 46.3% being SSL
- It also shows that there were 2167 SSL packets, totaling around 177 KB.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/c8c984df37535b782e92c34fa052fb54c8b1706c37e8d44cdbb1ff231b5f4838252d67effa7f8279efd579056cff.png)

To check a specific protocol traffic in the packet list, right-click on a protocol and select `Apply as Filter > Selected/Not Selected` to have Wireshark automatically create and apply a display filter showing/excluding the specified protocol traffic.

The Protocol Hierarchy window can also identify data exfiltration through unusual or unused protocols. If you notice a very small portion of FTP traffic in a large network that doesn’t use FTP, it might be worth it to check out the FTP traffic and make sure the traffic is legitimate. Quite a few of network analysis challenges in CTFs dealing with data exfiltration can be solved by identifying unusual protocols from the Protocol Hierarchy window.

## Conversations

The Conversations window also provides a wealth of information on the traffic, including which hosts have communicated to other hosts, on which ports, and with a total of how many bytes and packets in the conversation. This window is great for identifying the different MAC or IP addresses that a host has communicated with, and the volume of traffic between them.

Similarly to the Protocol Hierarchy window, the Conversations window can be very helpful in investigating data exfiltration attempts, as it can identify the attacker by IP address. If a host has been transmitting many packets and bytes to an unidentified IP address without receiving many packets in return, an exfiltration could have been occurring.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/860861ba2bd29c27957357a85558461f7bd44e289a3a8ef9b82980e785890defb835348ff310b9d1f7cc33da3e10.png)

 In the above image, as shown by the first line, host 192.168.1.7 has been connecting to 172.217.167.98’s HTTPS server (this is actually Google) with port 65220 and has sent and received 9 packets. Similar to the Protocol Hierarchy window, you can right-click on a line, select `Apply as Filter > Selected/Not Selected` and choose the direction of traffic to apply a filter for the line.

## Endpoints

Lastly, the Endpoints window shows all of the different hosts that appear in the capture and the amount of packets/bytes they sent and received. This window is useful in sorting hosts by their network activity, by either transmission or receiving volume, or by both. 

If a host has been receiving much more traffic than they have been transmitting, the host is probably downloading a large file. On the other hand, if the host has been transmitting more than they have been receiving, the host is probably uploading files or backing up to remote storage, such as the cloud. 

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/98531f9b99fe6c88ed88542df456dacd608c5bf4bc9a6bd5be4bfd4a08240c82ba7fba25ae94b3b7d79eee6d5a6e.png)

In the above diagram, host 192.168.1.7 has sent 1156 packets, totaling 311 KB, and has received 1080 packets, totaling 182 KB. You can switch to other protocols, such as TCP to have traffic sorted by ports and Ethernet to have traffic sorted by MAC addresses. Same with all other statistics windows, you can right-click on a host to apply it as a filter.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 22nd 2023 (12:10 pm) 
Last Modified Date: June 22nd 2023 (12:10 pm)
