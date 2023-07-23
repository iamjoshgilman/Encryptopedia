---
creation date: July 22nd 2023
last modified date: July 22nd 2023
aliases: []
tags: #📖
---

Primary Categories: [[000 - Cybersecurity Materials]]
Secondary Categories: [[01 - Malware Analysis]]
Links: [[]] 
Search Tag: #📖  

# [[03 - Basic Static Analysis]]  

---
## Hashing Malware Samples

Using Cmder on FlareVM we can get the Hash values for the "suspected" malware or known sample.

![[Pasted image 20230722125546.png]]
![[Pasted image 20230722125642.png]]

```text
SHA256SUM - 92730427321a1c4ccfc0d0580834daef98121efa9bb8963da332bfd6cf1fda8a *Malware.Unknown.exe

MD5SUM - 1d8562c0adcaee734d63f7baaca02f7c *Malware.Unknown.exe
```

---
## Malware Repositories: VirusTotal

Submitting to Virus total the SHA256

![[Pasted image 20230722130058.png]]

---
##  Strings & FLOSS: Static String Analysis

Floss is a FlareVM tool made by FireEye that will pull out any strings over 4 characters.
	This can sometimes show us interesting and telling information

![[Pasted image 20230722131628.png]]
![[Pasted image 20230722204926.png]]

Tip: FLOSS can be run with the "-n" argument to specify your desired minimum string length. Sometimes, longer strings can be more useful to an analyst than your standard string of len(4).

For example, if I want to pull all strings of length 6 or greater, I can issue the following command:

floss.exe -n 6 `malware_name.exe`














___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: July 22nd 2023 (12:35 pm) 
Last Modified Date: July 22nd 2023 (12:35 pm)
