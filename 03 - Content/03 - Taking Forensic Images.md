---
creation date: June 23rd 2023
last modified date: June 23rd 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Threat Intelligence]] | [[000 - Global Index]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Taking Forensic Images]]  
---

## Importance of Forensic Images
- Forensic images capture crucial evidence for incident responders to analyze and learn from an incident.
- They provide insights into the tactics, techniques, and procedures (TTPs) used by attackers and collect indicators of compromise for sharing with other organizations.

## Methods for Taking Forensic Images
- Forensic images should be taken of the hard drives of affected systems and memory dumps to capture artifacts in RAM.
- In some cases, the forensic image of the drive may be stored on a USB to facilitate analysis by multiple analysts and for easier storage.

## Tools for Forensic Imaging
### FTK Imager
- FTK Imager is a tool used for disk imaging in digital forensics.
- It allows for the collection of evidence from hard drives and other storage media.
- Refer to the "Disk Imaging: FTK Imager" lesson within the Digital Forensics domain for an in-depth explanation of evidence collection using FTK Imager.

### KAPE
- KAPE is a tool used for live acquisition in digital forensics.
- It enables quick collection of evidence from volatile locations such as RAM.
- Refer to the "Live Acquisition: KAPE" lesson within the Digital Forensics domain for more details on using KAPE for evidence collection.

## Process of Taking Forensic Images
- In a real-world incident response situation, an incident responder with digital forensics skills gains access to the affected system(s).
- KAPE is used to collect evidence from volatile locations, such as RAM.
- Hard drives are connected to a hardware write-blocker, which is then connected to a forensic laptop or workstation.
- The forensic analyst uses a bit-by-bit copy method to create a forensic image of the hard drive without altering its contents.
- Hashes are compared between the original drive and the disk image to ensure their integrity.
- The newly generated disk image is copied, and the original drive is securely stored, preserving both the original evidence and the initial copy.
- Forensic analysts can then investigate the copy of the disk image and collect further evidence following the procedures covered in the "Digital Evidence Collection" section of the Digital Forensics domain.

## Virtual Desktops
- When dealing with virtual desktop environments, such as Citrix, a different approach is taken to gather a disk image for analysis and evidence collection.
- A snapshot of the virtual system is taken, which is then mounted in another virtual machine designed for forensics purposes (e.g., Sift).
- A disk image is taken of the mounted snapshot for further analysis.

Remember: Forensic images capture vital evidence for incident response and analysis. Tools like FTK Imager and KAPE facilitate the process of collecting evidence from hard drives and volatile locations. Forensic images should be taken using a bit-by-bit copy method and compared with hashes to ensure integrity. When dealing with virtual desktop environments, snapshots of virtual systems can be used for disk imaging.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 23rd 2023 (10:20 am) 
Last Modified Date: June 23rd 2023 (10:20 am)
