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

# [[03 - Artifact Sanitization]]  
---

## Artifact Sanitization

Artifact sanitization refers to the process of making URLs or IP addresses harmless by defanging them. This is crucial when writing reports to prevent accidental clicks on potentially malicious links. By defanging URLs and IP addresses, the risk of compromising systems within an organization is reduced.

The rules for artifact sanitization are as follows:

1. Surround the "." within URLs and IP addresses with "[]" to become "[.]".
2. Change "tt" to "xx" within the "http" of URLs to become "hxxp".

For example:
- `8.8.8.8` becomes `8[.]8[.]8[.]8`
- `https://hello.example.com` becomes `hxxp[://]hello[.]example[.]com`

Performing artifact sanitization for a batch of URLs and IP addresses can be time-consuming. However, the process can be automated using tools like CyberChef's Defang IP Addresses and Defang URL operations.

1. Open the CyberChef tool (available at https://gchq.github.io/CyberChef/).
2. In the "Recipe" section, locate the "Defang IP Addresses" operation.
3. Drag the "Defang IP Addresses" operation onto the canvas.
4. In the input field, enter the IP address or a batch of IP addresses that need to be defanged.
5. The output field will display the defanged IP addresses.
6. Next, locate the "Defang URL" operation in the "Recipe" section.
7. Drag the "Defang URL" operation onto the canvas.
8. In the input field, enter the URL or a batch of URLs that need to be defanged.
9. The output field will display the defanged URLs.
10. Copy the defanged IP addresses and URLs from the output fields as needed for your report.

___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 18th 2023 (05:30 pm) 
Last Modified Date: June 18th 2023 (05:30 pm)
