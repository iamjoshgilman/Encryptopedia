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

# [[03 - Disk Imager - FTK Imager]]  
---

- FTK Imager is a powerful tool used in forensic investigations by investigators and security teams.
- It allows for the collection of forensically-sound copies of hard drives, which can be later analyzed for retrieving evidence.
- Download and try using FTK Imager to gain hands-on experience with the tool.

## Features of FTK Imager

- Dump RAM and save it as a .mem file for further analysis using tools like Volatility.
- Create forensically-sound disk images for analysis in tools like Autopsy.
- Export files directly from disk images.
- Generate MD5 and SHA1 hashes for evidence files.
- Provide a read-only view of disk image contents as seen by the user.
- And many more features!

## Dumping Memory

1. Install and launch FTK Imager.
2. To capture a snapshot of RAM, go to `File > Capture Memory`.
3. Choose a location to save the file (e.g., "Memory Dump" directory on the Desktop) and specify the filename (e.g., "memdump.mem").
4. Leave the options to create an AD1 file unchecked.
5. Click on "Capture Memory" to initiate the process.
6. FTK Imager will dump RAM contents and save them in the designated .mem file.
7. The resulting memory dump can be analyzed using tools such as Volatility.

## Hard Drive Imaging

1. In a real-world scenario, connect the suspect hard drive to a forensic workstation with a clean hard drive using a write-blocker to prevent accidental changes.
2. Launch FTK Imager.
3. Go to `File > Create Disk Image`.
4. Select the source of the evidence, such as "Physical Drive" for a USB drive.
5. Choose the USB drive from the available drives.
6. Skip Evidence Item Information unless necessary for Chain of Custody and ACPO Principles.
7. Specify the output destination and filename for the disk image (e.g., "USBImage.img" on the Desktop).
8. Set the Image Fragment Size to 0MB to keep the disk image as a single file.
9. Click on "Finish" to start the imaging process.
10. FTK Imager will copy every bit of data from the USB drive to the specified destination.
11. The time required for imaging depends on the size of the drive and existing data.
12. After completion, a window will appear to compare file hashes and ensure the forensic soundness of the copy.

## Real-World Hard Drive Copy

1. The first diagram illustrates copying a hard drive to create a .img file on the forensic workstation.

![[Pasted image 20230619195658.png]]

1. The second diagram shows how FTK Imager can write the contents of the investigated hard drive to a blank hard drive.

![[Pasted image 20230619195724.png]]

## Practice with FTK Imager

- Use FTK Imager to:
  - Image an old USB drive.
  - Copy folders by selecting the "Contents of a Folder" option when choosing the Source Evidence Type.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 19th 2023 (03:26 pm) 
Last Modified Date: June 19th 2023 (03:26 pm)
