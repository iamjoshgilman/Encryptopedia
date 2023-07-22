---
creation date: June 20th 2023
last modified date: June 20th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Digital Forensics]] | [[000 - Global Index]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Windows Artifacts - Browsers]]  
---

The artifacts provide valuable information for digital forensic investigations, such as visited websites, browsing activities, downloaded files, search history, cached webpages, and more. The tools used in this lesson include:

1. KAPE: KAPE is a tool used for digital evidence collection. In this lesson, the browser-based modules of KAPE are utilized to collect information from running systems, specifically targeting Chrome, Edge, and Firefox.

2. Browser History Viewer: Browser History Viewer is a free tool developed by Foxton Forensics. It allows the analysis of browser history by importing the data captured using Browser History Capturer.

3. Browser History Capturer: Browser History Capturer is another tool developed by Foxton Forensics. It is used to forcefully retrieve important files for browser forensics, which can then be imported into Browser History Viewer.

## Acquisition via KAPE

- KAPE is loaded and the target directory and output directory are selected.
- Browser-based targets for Chrome, Firefox, and Edge are enabled.
- KAPE is executed, and the required information is gathered from the specified browsers.
- The retrieved files can be found in the output directory.

## Browser History Viewer

- Browser History Capturer is run to collect necessary files by selecting the user profile and capturing the data.
- The captured files are located in the "Capture" folder.
- Browser History Viewer is opened, and the captured directory is loaded.
- Pane 1 displays the imported information, including Website History, Cached Images, and Cached Web Pages.
- Pane 2 shows the website visit count per month.
- Pane 3 provides filtering options based on keywords, date, or web browser.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 20th 2023 (08:03 am) 
Last Modified Date: June 20th 2023 (08:03 am)
