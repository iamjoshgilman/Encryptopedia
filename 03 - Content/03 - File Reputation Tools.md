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

# [[03 - File Reputation Tools]]  
---

# Reputation Checks for Suspicious Attachments

Performing reputation checks on suspicious attachments or their associated hashes can help identify their reputation within the security community. Let's explore two online services for reputation checks: VirusTotal and Talos File Reputation.

## Important Note
It's crucial to remember that if something is not identified as malicious by online reputation tools, it does not guarantee its safety. Assume that suspicious files are malicious until proven safe through further analysis.

# VirusTotal

VirusTotal is a platform where you can upload files, search for IP addresses, domains, URLs, and other artifacts to retrieve a community-generated reputation value. Here's how it works:

1. Visit VirusTotal and utilize the file upload function to upload the suspicious file.
2. After the upload, you will see the reputation value and which security vendors have identified the file as malicious.
3. Pay attention to the number of vendors flagging the file as malicious. If even a few vendors detect it as malicious, defensive measures should be taken.

![[Pasted image 20230618152427.png]]

Remember that VirusTotal is not a definitive indicator. A file that is not flagged as malicious in VirusTotal may still be malicious, as it may not have been detected by security vendors yet. Further investigation is necessary to confirm whether a file is truly malicious or safe.

# Talos File Reputation

Talos File Reputation, offered by Cisco, allows you to search for SHA256 hashes against their reputation database. Here's how to use it:

1. Generate the SHA256 hash of the suspicious file using PowerShell on Windows (`Get-FileHash`) or the Linux command-line (`sha256sum`).
2. Take the generated SHA256 hash and search it in the Talos File Reputation system.
3. Talos File Reputation will provide information about the file's reputation, including a score indicating maliciousness, file size, file type, detection name, and aliases used to track the malware.
4. A high reputation score or clear indication of maliciousness suggests that the file is indeed malicious.

![[Pasted image 20230618152505.png]]

Talos File Reputation can provide insights into whether the file has been classified as malicious by Cisco's security products. However, as with any reputation check, it should not be the sole basis for determining a file's safety. Further investigation and analysis are necessary to make a conclusive determination.

Reputation checks on suspicious attachments can provide initial indications of potential maliciousness, but they should always be accompanied by thorough analysis to ensure accurate assessment.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 18th 2023 (03:00 pm) 
Last Modified Date: June 18th 2023 (03:00 pm)
