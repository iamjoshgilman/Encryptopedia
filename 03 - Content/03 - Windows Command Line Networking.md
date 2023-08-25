---
creation date: August 24th 2023
last modified date: August 24th 2023
aliases: []
tags: #📖
---

Primary Categories: [[]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Windows Command Line Networking]]  

#### IP Configuration

- **Command:** `ipconfig`
- **Purpose:** View the current network configuration.
- **Output Example:**
  ```plaintext
  C:\Users\User\Demo>ipconfig
  Ethernet adapter Ethernet0:
      IPv4 Address: 172.16.16.129
  Ethernet adapter Ethernet1:
      IPv4 Address: 192.168.196.135
  ```

#### `ipconfig` Utility

- **Utility:** `ipconfig`
- **Available:** On all versions of Windows.
- **Purpose:** Retrieve network configuration and manage active TCP/IP connections.

#### Setting IP Address

- **Utility:** `netsh`
- **Purpose:** Manage network settings of local or remote computers.
- **Usage:** Set IP of a machine.
- **Command Example:**
  ```plaintext
  netsh interface ip set address "Ethernet0" static 172.16.16.150 255.255.255.0 172.16.16.1
  ```

#### Verifying IP Address

- **Command:** `ipconfig`
- **Expected Output:**
  ```plaintext
  Ethernet adapter Ethernet0:
      IPv4 Address: 172.16.16.150
  ```

#### Accessing Network Resources

- **Utility:** `net`
- **Purpose:** Manage network settings including shares, print jobs, and users.
- **Usage:** Mount a network drive.
- **Command Example:**
  ```plaintext
  net use x: \\DESKTOP-3VSCD09\Share
  ```

#### Removing a Mounted Drive

- **Command:** `net use x: /delete`
- **Expected Output:**
  ```plaintext
  x: was deleted successfully.
  ```

This should give a more concise, structured, and markdown-friendly format for your information.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 24th 2023 (08:10 pm) 
Last Modified Date: August 24th 2023 (08:10 pm)
