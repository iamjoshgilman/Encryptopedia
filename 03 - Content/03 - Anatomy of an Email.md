---
creation date: June 16th 2023
last modified date: June 16th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Phishing Analysis]] [[000 - Global Index]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Anatomy of an Email]]  
---

## Email Header
- set of lines containing information about the message's transportation, such as the sender's address, the recipient's address, or timestamps showing when the message was sent by intermediary servers to the transport agents (MTAs), which act as a mail sorting office. 
- The header begins with the **From** line and is changed each time it passes through an intermediary server. 
- Using headers, you can see the exact path taken by the email and how long it took each server to process.

### Header Fields
- The **message** itself, is made up of the two following elements: the **header fields**, a set of lines describing the message's settings, such as the sender, the recipient, the date, etc. An email includes at least the three following headers:
	- `From`, showing the sender's email address
	- `To`, showing the recipient's email address
	- `Date`, showing the date when the email was sent.

### **Optional Header Fields**
- It may also contain the following optional fields:
	- `Received`, showing various information about the intermediary servers and the date when the message was processed
	- `Reply-To`, showing a reply address
	- `subject` showing the message's subject
	- `message-ID`, showing a unique identification for the message
	- `message body`, containing the message, separated from the header by a line break

### **Custom X-Headers**

It is important to note that header data is no guarantee of when the message was sent or who sent it, as values can be edited without any requirement for authorization, such as changing the From address to make it look like the email has come from "contact@amazon.co.uk". Additional personalized headers (called **X-headers**) can be set in order to provide the appropriate information. X-headers are called such because their name must begin with **X-**. For example, some anti-spam software programs mark messages as unwanted using the following header: `X-Spam-Status: YES`.

## Email Body
- An email body is where the information written by the sender is displayed for the recipient. This can be purely text-based or it can include hyperlinks, images, and HTML styling.









___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 16th 2023 (09:58 pm) 
Last Modified Date: June 16th 2023 (09:58 pm)
