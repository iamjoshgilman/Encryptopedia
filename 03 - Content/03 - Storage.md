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

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 24th 2023 (09:15 pm) 
Last Modified Date: August 24th 2023 (09:15 pm)
