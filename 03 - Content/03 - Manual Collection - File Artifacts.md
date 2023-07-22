---
creation date: June 18th 2023
last modified date: June 18th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Phishing Analysis]] | [[000 - Global Index]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Manual Collection - File Artifacts]]  
---

# Retrieving Hashes via PowerShell

When working on Windows OS, security analysts often use PowerShell for their day-to-day tasks. File hashes can be retrieved using the `Get-FileHash` command in PowerShell. By default, this command generates a SHA256 hash.

Here's how you can retrieve MD5, SHA1, and SHA256 hashes using PowerShell:

- To retrieve a SHA256 hash:
  ```powershell
  Get-FileHash -Algorithm SHA256 <file>
  ```

- To retrieve an MD5 hash:
  ```powershell
  Get-FileHash -Algorithm MD5 <file>
  ```

- To retrieve a SHA1 hash:
  ```powershell
  Get-FileHash -Algorithm SHA1 <file>
  ```

You can also chain these commands together using the `;` character to retrieve all three hash values at once:
```powershell
Get-FileHash -Algorithm SHA256 <file>; Get-FileHash -Algorithm MD5 <file>; Get-FileHash -Algorithm SHA1 <file>
```

# Retrieving Hashes via Linux CLI

In Linux, you can easily retrieve file hashes using the command-line interface. The three commands commonly used are:

- To retrieve a SHA256 hash:
  ```bash
  sha256sum <file>
  ```

- To retrieve a SHA1 hash:
  ```bash
  sha1sum <file>
  ```

- To retrieve an MD5 hash:
  ```bash
  md5sum <file>
  ```


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 18th 2023 (02:32 pm) 
Last Modified Date: June 18th 2023 (02:32 pm)
