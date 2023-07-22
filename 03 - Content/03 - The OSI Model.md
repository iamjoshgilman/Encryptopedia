---
creation date: June 16th 2023
last modified date: June 16th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Security Fundamentals]] [[000 - Global Index]] 
Secondary Categories: [[02 - Networking]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - The OSI Model]]  
---
### Open Systems Interconnection Model (OSI)
- reference scheme ==developed by the International Organization for Standardization (ISO) in 1984== with the purpose of abstracting in a detailed way the operation of the communication networks, showing the different phases through which the files must pass in data transmission and especially, displaying how the different protocols are executed along with this communication.

![[Pasted image 20230616091242.png]]

- The OSI model is divided into 7 layers, where each layer plays a specific role in communication and each one serves and is served by its directly superior and directly inferior layers respectively, working together to carry out data transmission between computers, between applications, and between networks.
	- **Top to Bottom =** All People Seem To Need Data Processing (**APSTNDP**)
	- **Bottom to Top =** Please Do Not Throw Sausage Pizza Away (**PDNTSPA**)

![[Pasted image 20230616092127.png]]

#### **Step 1. The Application Layer (Layer 7)**
- This layer (also known as a ==high-level layer==) is one of only 2 layers that the ==user can interact with.== The Application layer is in charge of ==providing an interface to the user to interact, communicate, and even give commands to the computer==. In this one, you will find e-mail applications, web browsers, file transfer applications, etc.
- Some application layer protocols include ==HTTP== as well as ==SMTP== (Simple Mail Transfer Protocol is one of the protocols that enables email communications).

#### **Step 2. The Presentation Layer (Layer 6)**
- This layer is considered the =="translator" between the machine and the user==. It is in charge of guaranteeing that the data is understandable for the applications that will be operated by the user, allowing its correct visualization. And is also responsible for the ==encryption and decryption of the incoming and outgoing data==.

#### **Step 3. The Session Layer (Layer 5)**
- The session layer is responsible for ==managing sessions between machines== to enable communication between them. It is responsible for handling the ==opening, closing, and resetting of sessions== (to ensure proper communication between both parties), and is in charge of establishing the order of communication between a sender and a receiver, among many other activities of this nature.

#### **Step 4. The Transport Layer (Layer 4)**
- The transport layer is responsible for the transparent ==transfer of data between two computers==. It ==assembles and fragments the packet==s that will be sent in the communication, while providing different mechanisms for ==verifying the integrity==, to ensure that the information reaches the system accurately (some of these are error control, flow control, control of congestion, and re-sending of information, in case there is a failure in the communication).

#### **Step 5. The Network Layer** **(Layer 3)**
- The network layer is responsible for ==redirecting the connection and transferring== the data between ==two different networks by physical means==, in search of the best path that allows this data to reach its destination in the shortest time possible.

#### **Step 6. The Data Link Layer (Layer 2)**
- This layer is in charge of the addressing and ==physical transmission of the data==, carrying out its ==encapsulation, and separating them into frames== that will be easily directed by the physical transfer media.

#### **Step 7. The Physical Layer (Layer 1)**
- This layer (also known as a ==low-level layer==) is another of the 2 layers that ==can be manipulated by the user==, since, in this case, it includes the physical elements of the networks ==(ethernet cables, optical fiber, etc.==) responsible for the topology and the global connections from the computer to the network that allows the transmission and the physical operation of the system.














___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 16th 2023 (09:00 am) 
Last Modified Date: June 16th 2023 (09:00 am)
