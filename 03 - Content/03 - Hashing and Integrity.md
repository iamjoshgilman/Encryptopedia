---
creation date: June 19th 2023
last modified date: June 19th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Digital Forensics]] | [[000 - Global Index]]
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Hashing and Integrity]]  
---

In digital forensics, creating hashes is a critical step to ensure the integrity and authenticity of digital evidence. Hashes are unique fingerprints of files or strings that can detect any tampering or modification. Let's explore the concept of hashes, how they are retrieved, and their significance in maintaining evidence integrity.

## What are Hashes?
- Hash values are text strings that represent the unique fingerprint of a file or string.
- When the content of a file is modified, the hash value will change, indicating that the file has been altered.
- Commonly used hash algorithms include Message Digest 5 (MD5), Secure Hash Algorithm 1 (SHA1), and Secure Hash Algorithm 256 (SHA256).
- Due to collisions (different data values producing the same hash value), MD5 is no longer considered secure, and SHA256 is widely used.

## Gathering Hashes in Windows
- In Windows, PowerShell can be used to generate hashes for files.
- The `Get-FileHash` command without any flags will generate a SHA256 hash by default.
- To retrieve MD5 or SHA1 hashes, the `-Algorithm` flag can be used, specifying the desired hash algorithm.

## Gathering Hashes in Linux
- Linux systems offer convenient commands for generating hashes.
- The `sha256sum`, `md5sum`, and `sha1sum` commands can be used to generate SHA256, MD5, and SHA1 hashes, respectively.
- Hashes can also be retrieved for text strings using the `echo -n <text> | string` command.

## Evidence Integrity
- Hashes play a crucial role in ensuring the integrity of digital evidence.
- During investigations, a hash is generated from the original storage media (e.g., hard drive).
- A bit-by-bit copy of the storage media is then created to preserve the evidence, and a hash is generated for the copy.
- By comparing the hash values of the original and copied media, forensic analysts can verify that an exact copy has been successfully created.
- Working on a copy of the evidence preserves the integrity of the original data and mitigates the risk of data loss or tampering during analysis.
- Having an unaltered copy strengthens the admissibility of evidence in legal proceedings.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 19th 2023 (02:35 pm) 
Last Modified Date: June 19th 2023 (02:35 pm)
