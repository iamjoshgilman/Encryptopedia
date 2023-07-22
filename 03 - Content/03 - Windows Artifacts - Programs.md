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

# [[03 - Windows Artifacts - Programs]]  
---

This lesson focuses on artifacts that can be gathered from systems running Windows, specifically related to the use of applications and programs on the system. These artifacts provide valuable evidence, such as file usage information, creation dates, last access times, and file paths. The artifacts covered in this lesson include:

## 1. LNK Files / Shortcut Analysis

**Artifact Description:** LNK files serve as shortcuts in the Windows OS, linking one file to another. They provide metadata about the linked file, including the folder location, creation date, modification date, last access date, and file size.

**Artifact Location:** LNK files can be found at: `C:\Users\$USER$\AppData\Roaming\Microsoft\Windows\Recent`

**Artifact Analysis:** To view LNK files in a human-readable format, Windows File Analyzer can be used. It allows the analysis of LNK files and provides information such as filename, linked path, creation date, modification date, last access date, and file size. Individual LNK files can be examined separately, and the information can be saved or copied for further use.

## 2. Prefetch Files

**Artifact Description:** Prefetch files contain valuable information about programs, including the application name, executable file path, last run time, and creation/installation time.

**Artifact Location:** Prefetch files can be found at: `C:\Windows\Prefetch`

**Artifact Analysis:** Prefetch Explorer Command Line (PECmd.exe) is a tool used to analyze prefetch files. By using an administrative-level command prompt, the prefetch files can be accessed and analyzed. PECmd.exe provides information such as the number of times a file has been run, creation time, modification time, last access time, and related file paths. This analysis helps determine when files were last run, the frequency of their usage, and their file paths.

## 3. Jump List Files

**Artifact Description:** Jump List files are associated with the Windows Jump List feature and contain information about pinned applications on the taskbar. They include file paths, timestamps, and application identifiers (AppIDs).

**Artifact Location:** Jump List files can be found at:
- AutomaticDestination-ms: C:\Users\%USERNAME%\AppData\Roaming\Microsoft\Windows\Recent\AutomaticDestinations
- CustomDestination-ms: C:\Users\%USERNAME%\AppData\Roaming\Microsoft\Windows\Recent\CustomDestinations

**Artifact Analysis:** Jump List Explorer is a tool used to analyze Jump List files. By accessing the appropriate directory, the Jump List files can be imported and examined. The analysis reveals information such as the source file path, file size, and details about the applications. This includes the application name, creation, modification, and last access dates, as well as potential file names opened within the applications and their last access times.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 19th 2023 (08:57 pm) 
Last Modified Date: June 19th 2023 (08:57 pm)
