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

# [[03 - Automated Collection With PhishTool]]  
---

# PhishTool Artifact Retrieval and Analysis

PhishTool is a powerful platform that enables forensic analysis of phishing emails, allowing users to analyze emails, tag malicious artifacts, and generate investigation reports. Let's walk through the process of using PhishTool to upload phishing emails and generate reports.

# Analyzing a Phishing Email

1. Access the PhishTool analysis console homepage, where you'll find an interface to drag-and-drop or browse for a malicious email.

![[Pasted image 20230618144029.png]]

2. Click the "Browse" button to select the email you want to submit for analysis. You can upload the email file from your file system.

3. Once the analysis is completed, you'll see a results page with various artifacts extracted and analyzed from the email.

![[Pasted image 20230618144059.png]]

4. In the Basic Header section, you can retrieve the following artifacts:
   - Sending Address
   - Subject Line
   - Recipients
   - Date + Time

![[Pasted image 20230618144138.png]]

5. In the Detailed Header section, you'll find the X-Originating-IP and reverse DNS results, providing the Sending Server IP and Reverse DNS artifacts.

![[Pasted image 20230618144217.png]]

6. In the URLs section, you can retrieve all hyperlinks present in the email.

![[Pasted image 20230618144239.png]]

# Analyzing an Email with Malicious Attachment

1. Submit the email with a potentially malicious attachment to PhishTool.

2. In the Basic Header section, locate the Attachments subsection. Here, you'll find the MD5 hash of the attached file and its name.

![[Pasted image 20230618144338.png]]

3. Click on the VirusTotal link provided to automatically submit the hash for analysis and retrieve a community reputation score.

PhishTool allows you to gather important artifacts such as sending addresses, subject lines, recipients, date and time, sending server IP, reverse DNS, URLs, file names, and file hashes from phishing emails. It streamlines the artifact retrieval process and provides a comprehensive analysis of the submitted emails.

___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 18th 2023 (01:28 pm) 
Last Modified Date: June 18th 2023 (01:28 pm)
