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

# [[03 - Manual Collection - Web Artifacts]]  
---

# Email Artifact Extraction

When analyzing phishing emails, it's important to extract the URL or hyperlink safely to avoid accidental visits to malicious websites. Here are the extraction methods for email clients and text editors:

# Email Client Extraction

In an email client, such as Outlook, you can extract the URL by following these steps:

1. Identify the hyperlinked text in the email.
2. Hover your mouse over the text to reveal the URL.
3. Right-click on the URL and select "Copy Hyperlink" to save it to your clipboard.
4. Paste the URL in a safe location for further analysis.

Note: Exercise caution to avoid accidentally clicking on the malicious URL while performing these actions. Analyze phishing emails in a virtual machine or on a separate system to minimize risks.

# Text Editor Extraction

Using a text editor, such as Sublime, you can extract the URL by following these steps:

1. Open the email in the text editor.
2. Use the CTRL+F keyboard shortcut to enable the "Find" feature.
3. There are three quick ways to find the URL(s):

   - Search for "http" to identify any HTTP or HTTPS addresses mentioned in the email.
   - Search for anchor HTML tags `<a>` used for hyperlinking.
   - Search for the specific text from the email body that represents the hyperlink.

In this example, let's use the last method:

![[Pasted image 20230618140716.png]]


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 18th 2023 (02:48 pm) 
Last Modified Date: June 18th 2023 (02:48 pm)
