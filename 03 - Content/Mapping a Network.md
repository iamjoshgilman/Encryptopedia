---
creation date: March 31st 2023
last modified date: March 31st 2023
aliases: []
tags: #📖
---

Primary Categories: [[]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[Mapping a Network]]  

### Purpose
---
Provide scope and Discovery


### Wireshark
---
Open Wireshark, perform a packet capture - to generate this traffic do an Arp-scan
```bash
sudo arp-scan -I tap0 -g 10.10.10.0/24
```


### Ping 
---
We can ping results
```bash
ping 10.10.10.x
```


### Fping
---
F ping allows us to ping multiple hosts at one time
```bash
fping -I tap0 -g 10.10.10.0/24 -a 2>/dev/null
```
This will ping whole /24 stack and 2>/dev/null will kick out any errors such as closed hosts

---
#### Some hosts may respond to ARP while they wont respond to Ping
---





___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: March 31st 2023 (03:47 pm) 
Last Modified Date: March 31st 2023 (03:47 pm)
