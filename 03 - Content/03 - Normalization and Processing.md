---
creation date: June 21st 2023
last modified date: June 21st 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Security Information and Event Management]] | [[000 - Global Index]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Normalization and Processing]]  
---

## Normalization
- Normalization merges events containing different data into a reduced format with common event attributes.
- Most logs capture basic information like time, network address, and operations performed.
- Categorization adds meaning to events by identifying log data related to system events, authentication, local/remote operations, etc.

## Log Enrichment
- Log enrichment involves adding important information to make the overall data more beneficial for security analysts during investigations.
- For example, performing a simple lookup to determine the geographical location of an IP address mentioned in logs can aid investigations and provide analysts with the country the IP is based in.

## Log Indexing
- SIEMs store large amounts of data, and searching through all that data can be slow, especially over long periods.
- Indexing attributes shared by a large number of logs can speed up searching for specific attributes across large data sets.
- Indexing allows for faster retrieval of information compared to scanning every piece of data in the SIEM storage.

## Log Storage
- Large organizations may require significant storage to support a SIEM, requiring efforts from infrastructure and security teams.
- Alternatives to on-premises servers include cloud services like Amazon Web Services S3 buckets or Hadoop.
- Factors such as cost, ease-of-use, and scalability should be considered when choosing a log storage solution.

## Normalization
- Different software, hardware, and devices produce logs in their own formats, leading to challenges when sending logs to a SIEM.
- SIEM log normalization involves changing log formats into a consistent format across all devices and log sources.
- Normalization enables more consistent searching and information breakdown within the SIEM.
- Although logs from different systems may not look the same, matching attributes as closely as possible allows the SIEM to handle the variations.
- Example: "source_ip" may represent both the "src_ip" field from Cisco network devices and the "source_address" from Juniper network devices.
  - Searching for the "source_ip" value in the SIEM would check logs from both Cisco and Juniper devices.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 21st 2023 (11:50 am) 
Last Modified Date: June 21st 2023 (11:50 am)
