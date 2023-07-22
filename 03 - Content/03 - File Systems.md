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

# [[03 - File Systems]]  
---

# Notes on File Systems: FAT16, FAT32, NTFS, EXT3/EXT4

## What are File Systems?

- A file system is a means of classifying, organizing, and storing data on a storage medium.
- It helps efficiently manage space and enables data storage, categorization, management, navigation, and access.
- File systems are used in storage devices such as optical disks and magnetic storage disks.
- They consist of data types and mechanisms for accessing and recovering data.

## FAT16

- File Allocation Table (FAT) is a method of using a table to mark file positions.
- FAT16 is the original file system used in DOS and Windows 3.x.
- It was designed for use on small partitions.
- If the File Allocation Table is lost or damaged, the operating system cannot locate files.

## FAT32

- FAT32 is a revised version of FAT16.
- It supports larger partitions and has native support for long filenames.
- The "32" in the name refers to the use of 32 bits for identifying data clusters.
- Advantages of FAT32:
  - Compatibility with a wide range of devices and operating systems.
- Disadvantages of FAT32:
  - Limitation on file size (less than 4 GB).
  - Limitation on partition capacity (maximum 8 TB).
  - No data protection in case of power loss.
  - No built-in file compression or encryption features.

## NTFS

- NTFS (NT File System) is a proprietary journaling file system developed by Microsoft.
- It is the default file system of the Windows NT family.
- NTFS offers technical improvements over FAT and High-Performance File System (HPFS).
- Features of NTFS include metadata support, advanced data structures, performance improvement, reliability, and disk space utilization.
- NTFS supports access control lists (ACLs) for security and file system journaling.
- It is supported in other operating systems, but write support in non-Windows systems may be limited or unstable.

## EXT3 / EXT4

- Linux file systems are divided into user space, kernel space, and disk space.
- Ext3 is a journaled file system commonly used by the Linux kernel.
- Ext3 includes journaling, which improves data recovery and error detection.
- Changes in the file system are recorded in the journal.
- Ext4 is the stable version introduced in 2008.
- Ext4 supports larger volume and file sizes compared to Ext3.
- It replaces fragmentation with extents for improved performance.
- Extent is a data storage area that reduces file fragmentation.

## Identifying File Systems FTK Imager

1. Open FTK Imager.
2. Click on "File" in the menu bar.
3. Select "Add Evidence Item" from the dropdown menu.
4. In the "Source Type" selection window, choose "Image File".
5. Click on the "Browse" button and navigate to the disk image file you want to analyze.
6. Select the disk image file and click "Finish".
7. FTK Imager will analyze the disk image and provide information about the file system.
8. Look for the file system type, such as NTFS, FAT32, etc., in the analysis results.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 19th 2023 (01:05 pm) 
Last Modified Date: June 19th 2023 (01:05 pm)
