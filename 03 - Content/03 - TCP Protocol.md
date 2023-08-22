---
creation date: August 21st 2023
last modified date: August 21st 2023
aliases: []
tags: #📖
---

Primary Categories: [[02 - Networking Fundamentals]] | [[000 - Cybersecurity Materials]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - TCP Protocol]]  

## Overview
TCP (Transmission Control Protocol) focuses on the **reliable transmission of data**. It has mechanisms in place to ensure that data gets from one point to another without loss or errors.

## TCP Handshake
The process by which TCP connections are established:

1. **SYN Packet**:
    - **Computer A** → **Computer B**.
    - Flags: SYN.
    - Example:
    ```
    Computer A	Computer B	TCP	63410 > 1337 [SYN] Seq=0 Len=0
    ```

2. **SYN-ACK Packet**:
    - **Computer B** → **Computer A**.
    - Flags: SYN, ACK.
    - Example:
    ```
    Computer B	Computer A	TCP	1337 > 63410 [SYN, ACK] Seq=0 Ack=1 Len=0
    ```

3. **ACK Packet**:
    - **Computer A** → **Computer B**.
    - Flags: ACK.
    - Example:
    ```
    Computer A	Computer B	TCP	63410 > 1337 [ACK] Seq=1 Ack=1 Len=0
    ```

🔑 **Key Point**: Once the handshake is completed, a connection is established, allowing data transmission between the two computers. Sequence and acknowledgment numbers help detect missing data and request re-transmissions.

## TCP Transmission
Transferring data after a connection is established:

- Data Packet Example:
    ```
    Computer A	Computer B	TCP	63410 > 1337 [PSH, ACK] Seq=1 Ack=1 Len=12 [Data = Hello World]
    ```

- Acknowledgement Example:
    ```
    Computer B	Computer A	TCP	1337 > 63410 [ACK] Seq=1 Ack=13 Len=0
    ```

🔑 **Key Point**: The acknowledgment number increases by the length of the previously received packet, signifying the number of bytes successfully received.

## TCP Teardown
Terminating the connection:

1. **FIN-ACK Packet**:
    - **Computer A** → **Computer B**.
    - Flags: FIN, ACK.
    - Example:
    ```
    Computer A	Computer B	TCP	63410 > 1337 [FIN, ACK] Seq=13 Ack=1 Len=0
    ```

2. **ACK Packet**:
    - **Computer B** → **Computer A**.
    - Flags: ACK.
    - Example:
    ```
    Computer B	Computer A	TCP	1337 > 63410 [ACK] Seq=1 Ack=14 Len=0
    ```

3. **FIN-ACK Packet**:
    - **Computer B** → **Computer A**.
    - Flags: FIN, ACK.
    - Example:
    ```
    Computer B	Computer A	TCP	1337 > 63410 [FIN, ACK] Seq=1 Ack=14 Len=0
    ```

4. **ACK Packet**:
    - **Computer A** → **Computer B**.
    - Flags: ACK.
    - Example:
    ```
    Computer A	Computer B	TCP	63410 > 1337 [ACK] Seq=14 Ack=2 Len=0
    ```

🔑 **Key Point**: The teardown process ensures a graceful termination of the connection.

## Reset
In situations where a connection can't be torn down gracefully:

- **RST Packet**: Either side can send an 'rst' (reset) packet to abruptly terminate the connection.

🔑 **Key Point**: This method is used as a last resort, ending the connection immediately without the usual teardown sequence.

## Things to Remember:
1. **TCP Handshake**: Three-step process: SYN → SYN-ACK → ACK.
2. **Sequence & Acknowledgment Numbers**: Vital for reliable data transmission.
3. **Transmission**: Data is sent with sequence numbers, acknowledgment signifies the receipt of data.
4. **Teardown**: Four-step process to gracefully terminate the connection.
5. **Reset (RST)**: Abrupt connection termination.




___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 21st 2023 (09:57 pm) 
Last Modified Date: August 21st 2023 (09:57 pm)
