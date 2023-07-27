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

### Import Address Table (IAT) Win32 API Calls
```
GetForegroundWindow,x,-,0x00123BCE,0x002E002E,342 (0x0156),windowing,T1010 | Window Discovery,implicit,-,USER32.dll

GetWindowTextA,x,-,0x00123CD8,0x00730073,492 (0x01EC),windowing,T1010 | Window Discovery,implicit,-,USER32.dll

CopySid,x,-,0x00124210,0x00680073,133 (0x0085),security,T1134 | Access Token Manipulation,implicit,-,ADVAPI32.dll

GetLengthSid,x,-,0x00124226,0x00660063,331 (0x014B),security,T1134 | Access Token Manipulation,implicit,-,ADVAPI32.dll

SetSecurityDescriptorDacl,x,-,0x001242FA,0x0063002E,744 (0x02E8),security,T1134 | Access Token Manipulation,implicit,-,ADVAPI32.dll

SetSecurityDescriptorOwner,x,-,0x00124316,0x002E0000,746 (0x02EA),security,T1134 | Access Token Manipulation,implicit,-,ADVAPI32.dll

RegCreateKeyA,x,-,0x00124274,0x00690077,610 (0x0262),registry,T1112 | Modify Registry,implicit,-,ADVAPI32.dll

RegCreateKeyExA,x,-,0x00124284,0x0064006E,611 (0x0263),registry,T1112 | Modify Registry,implicit,-,ADVAPI32.dll

RegDeleteKeyA,x,-,0x00124296,0x0077006F,616 (0x0268),registry,T1485 | Data Destruction,implicit,-,ADVAPI32.dll

RegDeleteValueA,x,-,0x001242A6,0x002F0073,626 (0x0272),registry,T1485 | Data Destruction,implicit,-,ADVAPI32.dll

RegEnumKeyA,x,-,0x001242B8,0x00690077,632 (0x0278),registry,T1012 | Query Registry,implicit,-,ADVAPI32.dll

RegSetValueExA,x,-,0x001242E8,0x00650072,680 (0x02A8),registry,T1112 | Modify Registry,implicit,-,ADVAPI32.dll

GetCurrentProcessId,x,-,0x001245D8,0x00610063,534 (0x0216),reconnaissance,T1057 | Process Discovery,implicit,-,KERNEL32.dll

GetKeyboardState,x,-,0x00123BF8,0x00680073,363 (0x016B),input-output,T1179 | Hooking,implicit,-,USER32.dll

DeleteFileA,x,-,0x0012444C,0x002E0000,272 (0x0110),file,T1485 | Data Destruction,implicit,-,KERNEL32.dll

FindFirstFileA,x,-,0x0012449C,0x002E0065,375 (0x0177),file,T1083 | File and Directory Discovery,implicit,-,KERNEL32.dll

FindFirstFileExW,x,-,0x001244AE,0x00000063,377 (0x0179),file,T1083 | File and Directory Discovery,implicit,-,KERNEL32.dll

FindNextFileA,x,-,0x001244C2,0x002E002E,392 (0x0188),file,T1083 | File and Directory Discovery,implicit,-,KERNEL32.dll

FindNextFileW,x,-,0x001244D2,0x0070002F,394 (0x018A),file,T1083 | File and Directory Discovery,implicit,-,KERNEL32.dll

ShellExecuteA,x,-,0x00124118,0x002E002E,434 (0x01B2),execution,T1106 | Execution through API,implicit,-,SHELL32.dll

CreateProcessA,x,-,0x00124402,0x00730068,223 (0x00DF),execution,T1106 | Execution through API,implicit,-,KERNEL32.dll

GetCurrentThreadId,x,-,0x00124602,0x0063002E,538 (0x021A),execution,T1057 | Process Discovery,implicit,-,KERNEL32.dll

OpenProcess,x,-,0x00124A58,0x002E0000,1030 (0x0406),execution,T1055 | Process Injection,implicit,-,KERNEL32.dll

CloseClipboard,x,-,0x0012396E,0x002F002E,77 (0x004D),data-exchange,T1115 | Clipboard Data,implicit,-,USER32.dll

EmptyClipboard,x,-,0x00123AAA,0x002E002E,234 (0x00EA),data-exchange,T1115 | Clipboard Data,implicit,-,USER32.dll

GetClipboardData,x,-,0x00123B44,0x0077006F,310 (0x0136),data-exchange,T1115 | Clipboard Data,implicit,-,USER32.dll

GetClipboardOwner,x,-,0x00123B58,0x002F0073,313 (0x0139),data-exchange,T1115 | Clipboard Data,implicit,-,USER32.dll

OpenClipboard,x,-,0x00123E2A,0x00740073,676 (0x02A4),data-exchange,T1115 | Clipboard Data,implicit,-,USER32.dll

RegisterClipboardFormatA,x,-,0x00123EA0,0x00670067,741 (0x02E5),data-exchange,T1115 | Clipboard Data,implicit,-,USER32.dll

SetClipboardData,x,-,0x00123F6A,0x006C0064,806 (0x0326),data-exchange,T1115 | Clipboard Data,implicit,-,USER32.dll

```

### Network Signatures

Potential download via GET on HTTP
![[Pasted image 20230726211639.png]]

### Host Signatures

Putty Config on opening after powershell brief run
![[Pasted image 20230726211759.png]]


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
	`There is many API calls being made that are called out with Mitre TTPs`
- Is it likely that this binary is packed?
	`It is likely this binary is not packed as the "raw data size" and "virtual size" are nearly identical`
---

### Basic Dynamic Analysis
 - Describe initial detonation. Are there any notable occurrences at first detonation? Without internet simulation? With internet simulation?
	`Without Internet - We get a quick blue (powershell?) screen and then the typical putty config screen`
	`With Internet - Potential download of 2nd payload`
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
