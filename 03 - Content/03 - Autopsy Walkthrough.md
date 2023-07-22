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

# [[03 - Autopsy Walkthrough]]  
---

## Opening Autopsy and Creating a New Case

1. Open Autopsy.
2. Click on "New Case" when presented with the initial screen.

### Providing Case Information

3. Enter a name for the case and select a base directory to store all files.
   - Example: Name: BTL1AutopsyWalkthrough, Base Directory: Documents/BTL1AutopsyWalkthrough.

### Optional Investigation Metadata

4. Optional: Input investigation-related metadata if required.
   - This allows adding additional information related to the investigation.

## Adding a Data Source and Running Ingest Modules

5. Autopsy prompts to add a data source.
6. Select "Disk Image or VM File" as the data source type and click "Next."
7. Browse and select the .E01 disk image file.
8. Click "Next" to add the selected file as a data source.

### Selecting Ingest Modules

9. Autopsy asks whether to run any ingest modules.
   - Ingest modules automate actions to retrieve useful information, saving time.
10. From the drop-down menu, choose "All Files, Directories, and Unallocated Space."
11. Select the following ingest modules (Note: Names may vary):
    - Recent Activity
    - File Type Identification
    - Embedded File Extractor
    - Exif Parser
    - Email Parser
    - Encryption Detection
    - Additional modules as required

### Running Ingest Modules

12. Observe the progress bar in the bottom right corner.
   - Each ingest module completion is indicated.
13. Wait for Autopsy to complete the analysis of the data source.
   - The values on the left-hand pane increase as important information is discovered and placed into the artifact tree.

## Analyzing Ingest Module Results

14. Once the ingest modules are complete, the progress bar disappears.
15. Navigate through the left pane to explore the extracted information.
   - Numbers next to headings indicate the presence of categorized information.

### Examining Volumes

16. Click the "+" icon next to "Data Sources" in the navigation tree.
17. Click the "+" icon next to the selected disk image file.
18. Explore the volumes (e.g., vol1, vol2, vol3) by clicking on them.
   - Left-clicking on the disk image in the navigation tree shows the Partition Table with volume details.

### Browsing File Structure

19. Double-click a volume (e.g., vol2) to view a read-only file structure.
   - This allows browsing files as if using the laptop itself.
20. Familiarize yourself with navigating the forensic image's file structure.

### Viewing Ingest Module Results

21. In the navigation tree, under the "Results" heading, access the various modules' results.
22. Click on "Web History" to view visited sites, dates accessed, and accessing programs.
   - Timestamps help establish timelines for investigations.
23. Explore the "Recycle Bin" section to identify deleted files, their paths, and deletion details.

### Exporting Files

24. Right-click on a specific file path (e.g., "Underage_lolita_r@ygold_001.jpg") to export the file.
25. Select the desired destination for file export.
26. Open the exported file to examine its contents.

### Investigating Installed Programs

27. Click on the "Installed Programs" section.
28. Review the list of installed programs on the right pane.
   - Note program names and installation dates.

### Analyzing Email Files

29. Navigate to "Accounts > Email" at the bottom of the navigation tree.
30. Review the list of downloaded email files
31. Export a specific email file and open it using an email client or text editor.
   - Extracted information may include sender, recipient, date/time, subject, and more.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 20th 2023 (03:28 pm) 
Last Modified Date: June 20th 2023 (03:28 pm)
