---
creation date: August 24th 2023
last modified date: August 24th 2023
aliases: []
tags: #📖
---

Primary Categories: [[]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Storage]]  

# RAID:

## Introduction
RAID, or Redundant Array of Independent Disks, is a technology used to enhance storage performance, reliability, or both by combining multiple disks into one logical unit.
## Types of RAID

### RAID 0: Striping
- **Description**: Data is "striped" across multiple disks, which increases performance as multiple disks are read or written to simultaneously.
- **Advantages**: 
  1. Improved read and write speeds.
  2. Maximum utilization of storage.
- **Disadvantages**: 
  1. No fault tolerance. If one drive fails, all data is lost.
### RAID 1: Mirroring
- **Description**: Data is mirrored, meaning it's written identically to two or more drives.
- **Advantages**:
  1. High fault tolerance since data is duplicated.
  2. Read speed is improved.
- **Disadvantages**:
  1. Storage capacity is reduced by half.
### RAID 5: Striping with Parity
- **Description**: Data striping is used in conjunction with parity. Parity data is spread across the drives, allowing data recovery in the event of a disk failure.
- **Advantages**:
  1. Good balance between performance and protection.
  2. Can withstand the failure of a single drive.
- **Disadvantages**:
  1. Write speed is slightly reduced due to parity calculation.
  2. "Striping with parity" requires at least three drives to function.
 
### RAID 6: Striping with Double Parity
- **Description**: Similar to RAID 5, but with an extra parity block, ensuring data can be recovered even if two drives fail.
- **Advantages**:
  1. Can withstand the failure of two drives.
  2. Provides better fault tolerance than RAID 5.
- **Disadvantages**:
  1. Requires a minimum of four drives.
  2. Write speed is slower than RAID 5 due to double parity calculation.
### RAID 10 (1+0): Striped Mirrors
- **Description**: Combines RAID 1 and RAID 0, where data is mirrored and then striped across the mirrors.
- **Advantages**:
  1. High fault tolerance.
  2. Improved read and write performance.
- **Disadvantages**:
  1. Only 50% of total drive space is usable.
  2. Requires a minimum of four drives.

___
## Cloud Storage Mechanisms:

Storing data in the cloud is now more common than ever. Understanding the mechanisms by which data is stored can help in determining the most efficient and cost-effective storage solutions for different types of data and applications. Let's delve deeper into these storage mechanisms.
### File Storage
**Definition**: In file storage, data is organized in files and directories. This is similar to the way we organize files on our personal computers.

**Key Features**:
1. Hierarchical structure: Files are organized into directories (or folders) which can have sub-directories.
2. Metadata: Associated with every file which includes details like file creation date, modification date, size, etc.
3. Access: Typically accessed through file protocols such as NFS (Network File System) or SMB (Server Message Block).

**Use Cases**: Suitable for shared storage needs like document storage, shared drives, etc.
### Block Storage
**Definition**: In block storage, data is divided into fixed-sized blocks. Each block has a unique identifier which allows for data to be stored and retrieved without concerning the file structure.

**Key Features**:
1. Fixed-sized blocks: Data is split into chunks of a specified size.
2. Performance: Offers high performance, especially for databases and applications that require fast input/output operations.
3. Granular Control: Ideal for applications that need more fine-grained access to data.

**Use Cases**: Block storage is commonly used for databases, enterprise applications, and VM (Virtual Machine) file systems.
### Object Storage
**Definition**: In object storage, data is bundled with metadata and a unique identifier into objects. There's no hierarchical organization – all objects are stored in a flat namespace.

**Key Features**:
1. Metadata: Each object contains the data, an extensive amount of metadata, and a globally unique identifier.
2. Scalability: Highly scalable, designed to manage vast amounts of unstructured data.
3. APIs: Commonly accessed via RESTful APIs.

**Use Cases**: Ideal for storing photos, videos, backups, web content, and big data analytics. 
### Conclusion

The choice of storage mechanism depends on the use case. 

- **File storage** is great for shared storage systems where users and applications need to access and share files.
- **Block storage** is typically chosen for applications that need raw storage with high performance, such as databases.
- **Object storage** excels in scenarios where vast amounts of unstructured data need to be stored and accessed without the performance overhead and complexity of a file hierarchy, like for media storage or backups.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 24th 2023 (09:15 pm) 
Last Modified Date: August 24th 2023 (09:15 pm)
