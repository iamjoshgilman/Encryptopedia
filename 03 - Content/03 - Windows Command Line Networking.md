---
creation date: August 24th 2023
last modified date: August 24th 2023
aliases: []
tags: #📖
---

Primary Categories: [[000 - Global Index]] | [[01 - Administration]] 
Secondary Categories: [[02 - Windows]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Windows Command Line Networking]]  

___
# Overview
- The Command Prompt in Windows offers a quick way to manage and assess network settings.
- Different utilities exist for different network tasks such as `ipconfig`, `netsh`, and `net`.
## 1. Checking Network Settings with `ipconfig`
**Definition**: `ipconfig` is a command line utility available in all versions of Windows to retrieve and manage network configuration.
  
**Usage**:
```shell
C:\Users\User\Demo>ipconfig
```
  
**Sample Output**:
```
Windows IP Configuration
Ethernet adapter Ethernet0:
Connection-specific DNS Suffix  : localdomain
IPv4 Address.                   : 172.16.16.129
...
```
## 2. Setting IP Address with `netsh`
**Definition**: `netsh` is the Network Shell utility that manages local or remote network settings.
  
**Command Structure**:
```shell
netsh interface ip set address <connection name> static <IP> <subnet> <gateway>
```

**Example**:
```shell
netsh interface ip set address "Ethernet0" static 172.16.16.150 255.255.255.0 172.16.16.1
```

To verify the change:
```shell
C:\Windows>ipconfig
```

**Expected Output**:
```
IPv4 Address.                   : 172.16.16.150
```
## 3. Accessing Network Resources with `net`
**Definition**: The `net` command manages various network aspects such as shares, print jobs, and users.

### 3.1 Mounting a Network Drive
**Command**:
```shell
net use x: \\DESKTOP-3VSCDO9\Share
```

Where:
- `x:` is the drive letter you're mapping the network share to.
- `\\DESKTOP-3VSCDO9\Share` is the address of the network share you want to access.

**To Navigate to the Mounted Drive**:
```shell
C:\Users\User\Demo>X:
```
### 3.2 Removing a Mounted Drive
**Command**:
```shell
net use x: /delete
```

**Expected Output**:
```
x: was deleted successfully.
```

And trying to access the drive afterwards will show:
```
The system cannot find the drive specified.
```
## Summary
- **`ipconfig`**: Quickly view network configurations of a machine.
- **`netsh`**: Set or change the IP configurations of a machine.
- **`net`**: Access and manage network resources like mounting and unmounting shared drives.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 24th 2023 (08:10 pm) 
Last Modified Date: August 24th 2023 (08:10 pm)
