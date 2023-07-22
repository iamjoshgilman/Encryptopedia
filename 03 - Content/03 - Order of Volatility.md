---
creation date: June 19th 2023
last modified date: June 19th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Digital Forensics]] | [[000 - Global Index]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Order of Volatility]]  
---

When examining digital evidence, understanding the order of volatility is crucial due to the volatile nature of certain types of evidence. Volatile evidence is susceptible to being lost when a system is powered down or disconnected. The order of volatility categorizes different locations of potential evidence based on their level of volatility, ranging from most volatile (1) to least volatile (6).

1. Registers & Cache:
   - CPU cache and registers contain extremely volatile data that constantly changes.
   - Investigators should retrieve data from the cache and registers immediately before it is lost.

2. Memory:
   - Random Access Memory (RAM) holds temporary data that can be lost due to power spikes or system disconnection.
   - RAM stores running processes, network connections, and other valuable information.

3. Disk (HDD and SSD):
   - Data on hard disk drives (HDD) and solid-state disk drives (SSD) can be lost if overwritten.
   - SSDs have additional risks like Garbage Collection and TRIM that may delete recoverable files.
   - Offline disk space is no longer considered volatile as it cannot be overwritten.

4. Remote Logging and Monitoring Data:
   - Remote logging and monitoring data can change more frequently than data on a hard drive.
   - Although more volatile, data on the hard drive takes precedence in importance.

5. Physical Configuration, Network Topology, Archival Media:
   - Physical configuration and network topology provide useful information but have a lesser impact on an investigation.
   - Archival data is typically stored on separate physical devices like USB drives or external hard drives.
   - These items are less vital or not volatile.

Digital forensics examiners must consider volatility when collecting evidence. It is crucial to employ methods that ensure volatile evidence is collected promptly and transferred to a non-volatile medium, such as an external hard drive, as quickly as possible.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 19th 2023 (01:35 pm) 
Last Modified Date: June 19th 2023 (01:35 pm)
