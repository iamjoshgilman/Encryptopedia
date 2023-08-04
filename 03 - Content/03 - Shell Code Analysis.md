---
creation date: August 3rd 2023
last modified date: August 3rd 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Malware Analysis]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Shell Code Analysis]]  


```python
#1/user/bin/env python3

with open("shellcode.txt", "r") as f:
	hex_string = f.read().replace("0x","").replace("byte[] rsrc = new byte[464] {","").replace("};","").replace(",","")
```



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 3rd 2023 (09:24 pm) 
Last Modified Date: August 3rd 2023 (09:24 pm)
