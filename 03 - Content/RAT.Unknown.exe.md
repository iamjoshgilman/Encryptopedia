---
creation date: July 25th 2023
last modified date: July 25th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Malware Analysis]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[RAT.Unknown.exe]]  

### Hashes

SHA256
```
248D491F89A10EC3289EC4CA448B19384464329C442BAC395F680C4F3A345C8C
```
SHA1
```
69B8ECF6B7CDE185DAED76D66100B6A31FD1A668
```
MD5
```
689FF2C6F94E31ABBA1DDEBF68BE810E
```

### Virtus Total Analysis : [38/71](https://www.virustotal.com/gui/file/248d491f89a10ec3289ec4ca448b19384464329c442bac395f680c4f3a345c8c)

### Strings/Floss Output

```
@SSL support is not available. Cannot connect over SSL. Compile with -d:ssl to enable.
@https
@No uri scheme supplied.
InternetOpenW
InternetOpenUrlW
@wininet
@wininet
MultiByteToWideChar
@kernel32
@kernel32
MessageBoxW
@user32
@user32
@[+] what command can I run for you
@[+] online
@NO SOUP FOR YOU
@\mscordll.exe
@Nim httpclient/1.0.6
@/msdcorelib.exe
@AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup
@intrt explr
@http://serv1.ec2-102-95-13-2-ubuntu.local
```

### IAT & PEView

Windows API Calls



### Network Signatures

Initial Run - Wireshark capture
![[Pasted image 20230725212006.png]]

Potential File Download | msdcorelib.exe
![[Pasted image 20230725212419.png]]

Listening port 5555
![[Pasted image 20230725213924.png]]

### Host Signatures

Initial Detonation
![[Pasted image 20230725211522.png]]

Downloaded .EXE
![[Pasted image 20230725213342.png]]

Persistence Binary 
![[Pasted image 20230725213503.png]]


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: July 25th 2023 (09:32 pm) 
Last Modified Date: July 25th 2023 (09:32 pm)
