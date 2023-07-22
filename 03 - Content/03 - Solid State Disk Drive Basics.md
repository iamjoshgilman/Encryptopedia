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

# [[03 - Solid State Disk Drive Basics]]  
---

## What are SSDs?

- Solid-state drives (SSDs) are storage devices that use flash-based memory.
- They are faster than traditional mechanical hard disk drives (HDDs) due to low read-access times and fast throughputs.
- Data is written to "pages" on SSDs and then organized into "blocks" on the drive.

## Garbage Collection

- Garbage collection is a process used by SSDs to optimize space and improve efficiency.
- The goal is to keep as many empty blocks as possible for faster data writing.
- The SSD controller identifies unused or deleted data and moves used pages to new blocks.
- The controller erases the empty blocks, making them available for use.
- Garbage collection is a background process managed by the SSD controller and the operating system.
- In digital forensics, garbage collection poses a risk of erasing data, including potential evidence, if the SSD identifies blocks as unwanted. Immediate power-off (hard shut-down or pulling the plug) is recommended to prevent data loss during investigations.

## Trim

- Trim is a feature related to garbage collection that operates similarly but at the operating system level.
- When files are deleted or moved to the Recycle Bin, they are not immediately overwritten.
- Trim informs the SSD to clear the data associated with deleted files, making it unrecoverable.
- It removes any chance of forensic investigations recovering the file or its parts.
- Similar to garbage collection, power-off with a hard shut-down or pulling the plug is advised to counter the effects of trim.

## Wear Leveling

- Wear leveling is a technique used by some SSDs to evenly distribute write operations across all blocks.
- It increases the lifetime of the SSD memory by preventing excessive wear on specific blocks.
- The micro-controller or firmware of the SSD performs wear leveling.
- Two common types of wear leveling algorithms are:
  - Dynamic wear leveling: Blocks undergoing rewriting are moved to new blocks, while infrequently updated blocks remain in their original positions.
  - Static wear leveling: Blocks of static data are moved when their block erase count falls below a certain threshold. This results in more effective wear leveling and enhanced longevity of the SSD.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 19th 2023 (01:24 pm) 
Last Modified Date: June 19th 2023 (01:24 pm)
