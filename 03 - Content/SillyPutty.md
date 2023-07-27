---
creation date: July 26th 2023
last modified date: July 26th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Malware Analysis]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[SillyPutty]]  

### Hashes

SHA256
```
0C82E654C09C8FD9FDF4899718EFA37670974C9EEC5A8FC18A167F93CEA6EE83
```
SHA1
```
C6A97B63FBD970984B95AE79A2B2AEF5749EE463
```
MD5
```
334A10500FEB0F3444BF2E86AB2E76DA
```

### Virtus Total Analysis: [60/70](https://www.virustotal.com/gui/file/0c82e654c09c8fd9fdf4899718efa37670974c9eec5a8fc18a167f93cea6ee83)

FLOSS/Strings output

```
PuTTY downstream no longer available
SSHCONNECTION@putty.projects.tartarus.org-2.0-

```






___
### Challenge Questions:

### Basic Static Analysis
---

- What is the SHA256 hash of the sample?
	`0C82E654C09C8FD9FDF4899718EFA37670974C9EEC5A8FC18A167F93CEA6EE83`
- What architecture is this binary?
	`32bit`
- Are there any results from submitting the SHA256 hash to VirusTotal?
	`Score of 60/70`
- Describe the results of pulling the strings from this binary. Record and describe any strings that are potentially interesting. Can any interesting information be extracted from the strings?
	`Lot of reabible strings, seems to act like the real putty tool, was not many actionable results`
- Describe the results of inspecting the IAT for this binary. Are there any imports worth noting?
- Is it likely that this binary is packed?
---

### Basic Dynamic Analysis
 - Describe initial detonation. Are there any notable occurrences at first detonation? Without internet simulation? With internet simulation?
 - From the host-based indicators perspective, what is the main payload that is initiated at detonation? What tool can you use to identify this?
 - What is the DNS record that is queried at detonation?
 - What is the callback port number at detonation?
 - What is the callback protocol at detonation?
 - How can you use host-based telemetry to identify the DNS record, port, and protocol?
 - Attempt to get the binary to initiate a shell on the localhost. Does a shell spawn? What is needed for a shell to spawn?




---
## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: July 26th 2023 (08:02 pm) 
Last Modified Date: July 26th 2023 (08:02 pm)
