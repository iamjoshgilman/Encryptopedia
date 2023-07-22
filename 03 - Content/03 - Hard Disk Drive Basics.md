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

# [[03 - Hard Disk Drive Basics]]  
---

## What are HDDs?

- A hard disk drive (HDD) is a non-volatile memory hardware device used for data storage.
- HDDs are commonly used as the main storage device in desktop computers and laptops.
- They store the operating system, software programs, and user-created files.
- HDDs are typically located in drive bays and connected to the motherboard via ATA, SATA, or SCSI cables.
- They are also connected directly to the power supply unit (PSU).

## Platters

- HDD platters are circular disks where magnetic data is stored.
- Platters in hard drives are rigid, in contrast to the flexible material used in floppy disks.
- Multiple platters are mounted on the same spindle in a hard drive.
- Each platter can store information on both sides, requiring two heads per platter.

## Sectors

- A sector is a subdivision of a track on a magnetic disk or optical disc.
- Each sector stores a fixed amount of user-accessible data.
- Traditional hard disk drives have sectors of 512 bytes, while newer drives use 4096-byte (4 KiB) sectors.
- Sectors are the minimum storage units of a hard drive.
- Disk partitioning schemes are designed to have files occupy an integral number of sectors.
- Files that do not fill a whole sector have the remainder of their last sector filled with zeroes.
- Operating systems typically operate on blocks of data that may span multiple sectors.
- A physical sector consists of a sector header area (ID) and a data area.
- The header includes an address identification to ensure correct positioning of the read/write head.
- The data area contains sync bytes, user data, and error-correcting code (ECC) for error detection and correction.

## Clusters

- A cluster is a group of sectors within a disk.
- Clusters are used to organize disk files.
- Clusters are larger than sectors, and most files occupy multiple clusters.
- Each cluster has a unique ID value for identification.

## Slack Space

- Slack space refers to the remaining storage in a hard disk drive when a file does not use all the allocated space.
- It occurs when a file does not fill a whole cluster.
- Slack space examination is important in computer forensics to find residual data from previous files.
- When a user deletes files that occupied an entire cluster and saves new files that fill only a portion of the cluster, the remaining half may still contain residual information.
- Slack space may potentially contain evidence or remnants of deleted files.

___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 19th 2023 (01:01 pm) 
Last Modified Date: June 19th 2023 (01:01 pm)
