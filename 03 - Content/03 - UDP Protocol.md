---
creation date: August 21st 2023
last modified date: August 21st 2023
aliases: []
tags: #📖
---

Primary Categories: [[02 - Networking Fundamentals]] | [[000 - Global Index]] 
Secondary Categories: [[01 - Administration]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - UDP Protocol]]  

## Overview
UDP (User Datagram Protocol) is a simple protocol in the realm of networking. Unlike TCP, UDP is connectionless, meaning it doesn't establish a formal connection nor does it ensure that the data is delivered reliably.

## Characteristics of UDP
1. **No Handshake**: UDP doesn’t perform any handshake to establish a connection.
2. **No Teardown**: Since there’s no formal connection, there's no teardown process.
3. **No Acknowledgments**: There are no mechanisms for acknowledging the receipt of data.
4. **No Sequence Numbers**: There's no sequencing of data packets as in TCP.

## Sending a UDP Packet
Here’s how a UDP packet looks:

```
Source      Destination   Prot   Info
Computer A  Computer B    UDP    50183 > 1337 Len=6 [data = stuff]
```

🔑 **Key Point**: If a UDP packet is lost, there’s no mechanism to detect or recover it. The sender assumes it's sent, while the receiver may never know of its existence.

## Advantages of UDP
1. **Speed**: UDP's simplicity makes it faster than TCP.
2. **Ideal for Real-time Applications**: Perfect for tasks like video streaming or online gaming where occasional data loss doesn't severely impact the experience.
3. **No Overhead**: Without the need for acknowledgments and sequence numbers, there's less overhead.

## Limitations of UDP
1. **Unreliable**: Data might be lost, and there's no built-in mechanism to detect or rectify it.
2. **Not Ordered**: Data packets might arrive out of order, and unlike TCP, UDP won’t reorder them.

🔑 **Real-world Application**: In video chats or streaming, a missing frame or two (due to dropped packets) is preferable to delaying the entire stream waiting for that frame. Thus, applications prioritize speed over guaranteed delivery.

## Things to Remember:
1. **UDP is Connectionless**: No handshakes, no teardown.
2. **UDP is Fast but Unreliable**: No acknowledgments, no sequencing.
3. **Ideal for Real-time Data**: Perfect for tasks where speed is more critical than complete data accuracy.
4. **Less Overhead**: Makes it lighter than TCP.
5. **Applications**: Video chats, online gaming, streaming.

Given UDP's characteristics, it's essential to evaluate the application's needs. If reliable data delivery is critical, TCP might be the choice. If speed and low overhead are prioritized, then UDP is the go-to protocol.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 21st 2023 (09:00 pm) 
Last Modified Date: August 21st 2023 (09:00 pm)
