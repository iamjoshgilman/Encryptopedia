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

# [[03 - Windows Artifacts - Recycle Bin]]  
---

## Artifact Description

The **Windows Recycle Bin** is a system folder that temporarily stores deleted files and folders before their permanent removal from the computer's hard drive or storage device. Key points about the Windows Recycle Bin in digital forensics include:

1. **Recovery of deleted files**: The Recycle Bin allows forensic examiners to easily restore recently deleted files, which can provide valuable evidence for investigations.
2. **Tracing user activity**: The Recycle Bin can reveal a user's attempt to delete evidence or hide their actions. Examining metadata like timestamps and file paths helps establish a timeline of events and identify patterns.
3. **File remnants and data carving**: Even after emptying the Recycle Bin, deleted file data may persist on the storage device until overwritten. Specialized techniques like data carving can recover remnants and reconstruct deleted files.
4. **Analysis of Recycle Bin artifacts**: The Recycle Bin maintains system files containing information about deleted items, including original file paths, deletion timestamps, and other metadata. These artifacts provide context and insights for investigations.

## Artifact Location

On **Windows 10**, the Recycle Bin directory for all users is located at `C:\$Recycle.Bin`. If the Recycle Bin has been emptied, the artifact becomes unavailable for analysis.

## Artifact Analysis Tools

To collect and triage Recycle Bin artifacts, the following tools are recommended:

1. **Command Prompt (CMD)**: Used for executing commands and navigating through directories.
2. **RBCmd**: [GitHub - EricZimmerman/RBCmd: Recycle bin artifact parser](https://github.com/EricZimmerman/RBCmd) that parses Recycle Bin artifacts.
3. **CSVQuickViewer**: A tool for viewing CSV files generated during analysis.

## Technical Analysis

1. To reveal the Recycle Bin directory, use the command `dir /a` in Command Prompt. The `/a` flag displays hidden folders like the Recycle Bin.

2. Recycle Bin sub-folders are named using account security identifiers (SIDs). To determine the username associated with a SID, use the command `wmic useraccount get name,SID`.

3. Suppose we are investigating the account **Simon.Leeves**. To navigate to the folder associated with Simon.Leeves' SID, use the [Tab] key for auto-fill. List the hidden contents with `dir /a`.

4. After Windows Vista, when a file is deleted, two files are generated in the Recycle Bin:
   - Files starting with "$R" followed by a random string contain the true file contents.
   - Files starting with "$I" and ending in the same string as the "$R" file counterpart contain metadata such as the original filename, path, size, and deletion timestamp.

5. Analyzing specific $R and $I files related to Simon.Leeves' account using RBCmd:
   - Use the command `C:\Users\BTLOTest\Desktop\Recycle-Bin-Analysis\Tools\RBCmd.exe -f $I1UOZ51.xlsx` to analyze the first $I file in the folder.
   - The output provides details about the file, such as its size, original location, name, and deletion timestamp.

6. Analyzing the entire folder using RBCmd and exporting to a CSV file:
   - Use the command `C:\Users\BTLOTest\Desktop\Recycle-Bin-Analysis\Tools\RBCmd.exe -d . --csv "C:\Users\BTLOTest\Desktop\RBCmdOutput"` to analyze the current directory recursively and export a CSV file.
   - Open the generated CSV file with CSVQuickViewer to investigate the deleted files, their timestamps, and other relevant information.

7. To analyze the Recycle Bin

 for all local accounts on a system, run RBCmd from the `C:\$Recycle.Bin` directory using the `-d .` argument. RBCmd will recursively analyze the SID sub-folders and their associated $I files.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 20th 2023 (11:45 am) 
Last Modified Date: June 20th 2023 (11:45 am)
