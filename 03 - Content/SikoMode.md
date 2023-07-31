---
creation date: July 31st 2023
last modified date: July 31st 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Malware Analysis]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[SikoMode]]  

### Hashes

SHA256
```
3ACA2A08CF296F1845D6171958EF0FFD1C8BDFC3E48BDD34A605CB1F7468213E
```
SHA1
```
6C8F50040545D8CD9AF4B51564DE654266E592E3
```
MD5
```
B9497FFB7E9C6F49823B95851EC874E3
```

### Virtus Total Analysis : [40/70](https://www.virustotal.com/gui/file/3aca2a08cf296f1845d6171958ef0ffd1c8bdfc3e48bdd34a605cb1f7468213e)


### Strings/Floss Output


```
@iterators.nim(240, 11) `len(a) == L` the length of the seq changed while iterating over it
@net.nim(1438, 12) `avail <= size - read` 
@recv
@net.nim(1367, 14) `size - read >= chunk` 
@net.nim(1319, 9) `not socket.isClosed` Cannot `recv` on a closed socket
@readLine
@' timed out.
@Call to '
@net.nim(1403, 24) `false` 
@Could not send all data.
@No valid socket error code available
@net.nim(1669, 9) `not socket.isClosed` Cannot `send` on a closed socket
@Couldn't resolve address: 
@net.nim(233, 10) `fd != osInvalidSocket` 
```


### Windows API Calls

```
GetCurrentProcessId
VirtualProtect
GetCurrentThreadId
TerminateProcess
RtlAddFunctionTable
RtlLookupFunctionEntry
getenv
```


### Network Signatures








### Host Signatures









---
## Challenge Questions:

- What language is the binary written in?
- What is the architecture of this binary?
- Under what conditions can you get the binary to delete itself?
- Does the binary persist? If so, how?
- What is the first callback domain?
- Under what conditions can you get the binary to exfiltrate data?
- What is the exfiltration domain?
- How does exfiltration take place?
- What URI is used to exfiltrate data?
- What type of data is exfiltrated (the file is cosmo.jpeg, but how exactly is the file's data transmitted?)
- What kind of encryption algorithm is in use?
- What key is used to encrypt the data?
- What is the significance of `houdini`?


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: July 31st 2023 (07:30 pm) 
Last Modified Date: July 31st 2023 (07:30 pm)
