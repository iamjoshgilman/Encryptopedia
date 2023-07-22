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

# [[03 - Evidence Destruction]]  
---

# Secure Disposal of Digital Evidence

This lesson covers various methods for securely destroying digital evidence once the retention period has expired. It is essential to ensure that the evidence is permanently and irretrievably destroyed. The following methods can be employed:

## 1. Degaussing

- Degaussing involves subjecting tapes or hard disks to a powerful magnetic field, effectively neutralizing or erasing the magnetic data.
- Degaussing is considered the most reliable method of hard drive erasure and serves as the standard for data destruction.
- The use of a suitable degausser guarantees that the information is no longer retrievable.

## 2. File Shredding

- File shredding refers to the process of securely deleting files or folders. Simply deleting them manually may not be sufficient, as they can still be recovered.
- Some file shredding programs employ methods to overwrite or sanitize the selected data, ensuring its irretrievability.
- The DoD 5220.22-M Wipe Method is an example of file shredding that consists of the following steps:
  - Pass 1: Writes a zero and verifies the write.
  - Pass 2: Writes a one and verifies the write.
  - Pass 3: Writes a random character and verifies the write.

## 3. Physical Shredding

- Physical shredding involves destroying physical storage media to prevent reassembly and unauthorized access.
- Industrial-grade destruction equipment is used to shred hard drives, USBs, or other hardware into small pieces.
- The process destroys the drive platters, mechanisms, and electronic components, rendering the data unrecoverable.

## 4. Hydraulic Crusher

- The hydraulic crusher method employs a hydraulic press with a metal rod that is forcefully driven through the hard drive.
- The immense pressure, approximately 3,400 kilos, completely destroys the drive platters and fractures the magnetic surfaces, making the drive data irrecoverable.
- Another variation of this method involves bending the hard drives until they snap.

## 5. Overwriting

- Overwriting offers an option to reuse hard drives or USBs involved in forensic investigations without physically destroying them.
- Data on a storage device is typically still accessible until it has been overwritten.
- The Diskpart function in Windows allows complete clearing of a hard drive from the command prompt by overwriting existing data with zeros.

By employing one or a combination of these methods, digital evidence can be securely disposed of, ensuring that it cannot be recovered or accessed in the future.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 19th 2023 (08:13 pm) 
Last Modified Date: June 19th 2023 (08:13 pm)
