---
creation date: June 20th 2023
last modified date: June 20th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Digital Forensics]] | [[000 - Global Index]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Volatility Walkthrough]]  
---

# Volatility Memory Dump Analysis

## Understanding Volatility Profiles
- Volatility requires profiles to work effectively.
- To determine the suggested profile for analysis:
  - Run the command `volatility -f memdump.mem imageinfo`.
  - Volatility will identify the system details from the memory image, such as operating system, version, and architecture.
  - The suggested profile is displayed, e.g., `Win7SP1x64` for Windows 7 with Service Pack 1 and 64-bit architecture.
- Always include the profile in subsequent commands using the `--profile=PROFILE` flag.

## Basic Analysis Commands

| Command | Description |
|---------|-------------|
| `volatility -f memdump.mem imageinfo` | Determine the suggested profile for analysis based on the memory image. |
| `volatility -f memdump.mem --profile=PROFILE pslist` | List running processes. |
| `volatility -f memdump.mem --profile=PROFILE pstree` | Display process hierarchy in a tree format. |
| `volatility -f memdump.mem --profile=PROFILE psscan` | Identify hidden processes commonly used by malware. |
| `volatility -f memdump.mem --profile=PROFILE psxview` | Display detailed information about processes. |
| `volatility -f memdump.mem --profile=PROFILE netscan` | View active and closed network connections. |
| `volatility -f memdump.mem --profile=PROFILE timeliner` | Generate a chronological timeline of events from the memory dump. |
| `volatility -f memdump.mem --profile=PROFILE iehistory` | Retrieve browsing history from the memory dump. |
| `volatility -f memdump.mem --profile=PROFILE filescan` | List files mentioned in the memory dump. |
| `volatility -f memdump.mem --profile=PROFILE dumpfiles -n --dump-dir=./` | Retrieve files from the memory dump and save them to the specified directory. |

## Additional Resources
- [Volatility's GitHub Memory Samples](https://github.com/volatilityfoundation/volatility/wiki/Memory-Samples)
- [Useful Volatility Commands](https://book.hacktricks.xyz/generic-methodologies-and-resources/basic-forensic-methodology/memory-dump-analysis/volatility-examples)
- [First Steps to Volatile Memory Analysis](https://medium.com/@p4n4rd1/first-steps-to-volatile-memory-analysis-3c9f65da7e8c) (Medium article on memory investigation approach)


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 20th 2023 (01:34 pm) 
Last Modified Date: June 20th 2023 (01:34 pm)
