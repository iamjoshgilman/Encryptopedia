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

# [[03 - Log Aggregation Explained]]  
---

Log aggregation refers to the process of collecting logs from multiple computing systems, parsing them, extracting structured data, and organizing them in a searchable and exploratory format using modern data tools.

There are several common methods for log aggregation, often combined in log aggregation systems:

1. **Syslog**: A standard logging protocol that allows network administrators to set up a Syslog server to receive logs from multiple systems. The Syslog server stores the logs in an efficient and condensed format, which can be easily queried by log aggregators.

2. **Event Streaming**: Protocols like SNMP, Netflow, and IPFIX enable network devices to provide standard information about their operations. Log aggregators intercept these protocols, parse the data, and add it to a central log storage for further analysis.

3. **Log Collectors**: These are software agents installed on network devices. Log collectors capture log information, parse it, and send it to a centralized aggregator component for storage and analysis.

4. **Direct Access**: Log aggregators can directly access network devices or computing systems by using APIs or network protocols to receive logs. This approach requires custom integration for each data source.

## Data Types

When considering the data being pulled into a Security Information and Event Management (SIEM) platform, two categories can be distinguished:

1. **Structured Data**: These logs usually come from sources such as Apache, IIS, Windows events, Cisco logs, and other similar manufacturers. Structured logs have clearly-defined fields, such as "src_ip," and they follow a consistent format, making them relatively easy to parse and normalize.

2. **Unstructured Data**: This type of logging typically originates from custom-built applications where each message can have a different format based on different operations. The events themselves may span multiple lines, with no defined start or endpoint. Unstructured data is often the majority of the data sent to the SIEM.

To facilitate searches across a large set of different logs, it is beneficial to normalize logs, making them follow a similar format. Normalization techniques can be employed to achieve this goal, which will be covered in the next section of this domain.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 21st 2023 (11:01 am) 
Last Modified Date: June 21st 2023 (11:01 am)
