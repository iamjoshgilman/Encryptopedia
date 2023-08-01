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
@:houdini
@Authorization
@Host
@httpclient.nim(1144, 15) `false` 
@Transfer-Encoding
@Content-Type
@Content-Length
@httpclient.nim(1082, 13) `not url.contains({'\r', '\n'})` url shouldn't contain any newline characters
@http://cdn.altimiter.local/feed?post=
@Nim httpclient/1.6.2
@Desktop\cosmo.jpeg
@SikoMode
@iterators.nim(240, 11) `len(a) == L` the length of the seq changed while iterating over it
@ccc
@Mozilla/5.0
@C:\Users\Public\passwrd.txt

<?xml version="1.0" encoding="UTF-8" standalone="yes"?><assembly xmlns="urn:schemas-microsoft-com:asm.v1" 
manifestVersion="1.0"><assemblyIdentity version="1.0.0.0" processorArchitecture="*" name="winim" 
type="win32"/><dependency><dependentAssembly><assemblyIdentity type="win32" name="Microsoft.Windows.Common-Controls" 
version="6.0.0.0" processorArchitecture="*" publicKeyToken="6595b64144ccf1df" 
language="*"/></dependentAssembly></dependency></assembly>

./mingw-w64-crt/crt/crtexe.c
./build/x86_64-w64-mingw32-x86_64-w64-mingw32-crt


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
	NIM
- What is the architecture of this binary?
	x64
- Under what conditions can you get the binary to delete itself?
	No internet 
- Does the binary persist? If so, how?
	No
- What is the first callback domain?
	http://update.ec12-4-109-278-3-ubuntu20-04.local/
- Under what conditions can you get the binary to exfiltrate data?
	Internet present
- What is the exfiltration domain?
	http://cdn.altimiter.local/feed?post=A8E437E8F0367592569A2870BBDD382A1DFBB01A15FC23999D7788C33502AD9256E481B402BDC6BC25167B6478F204C49A9BADD68C4AC2A617437ECCBBA9
- How does exfiltration take place?
- What URI is used to exfiltrate data?
	http://cdn.altimiter.local/feed?post=A8E437E8F0367592569A2870BBDD382A1DFBB01A15FC23999D7788C33502AD9256E481B402BDC6BC25167B6478F204C49A9BADD68C4AC2A617437ECCBBA9
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
