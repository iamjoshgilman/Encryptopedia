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

# [[03 - Metadata and File Carving]]  
---

In digital investigations, understanding metadata and employing file carving techniques are essential for retrieving valuable information and recovering deleted files. Metadata refers to the descriptive information about data, while file carving involves searching for and extracting files from a data stream. Let's explore these concepts further.

## Metadata

Metadata provides additional context and details about data. It includes information such as authorship, creation and modification timestamps, file properties, and even camera settings or GPS location in the case of photos. Extracting metadata can be done through various methods, depending on the operating system.

In Windows:
1. Right-click on a file and select "Properties."
2. Navigate to the "Details" tab to view metadata like author, creation time, and word count.

In Linux:
1. Right-click on a file and select "Properties," or use the following commands in the terminal:
   - `ls -lisap <file>`: Displays file information, including permissions, size, and timestamps.
   - `stat <file>`: Provides detailed information about a file, such as access and modification times.

The `exiftool` command-line tool in Kali Linux is useful for extracting metadata from files. Check if it's installed with the command `exiftool`, or install it using `sudo apt-get install exiftool`. To retrieve metadata, use the command `exiftool <filename>`.

## File Carving

File carving is a process used to recover deleted files from a disk image. By analyzing the underlying data stream, it's possible to identify and extract hidden or deleted files that haven't been overwritten. Here's an example of using the `scalpel` tool in Linux for file carving:

1. Edit the `scalpel.conf` file located at `/etc/scalpel/scalpel.conf` using a text editor.
2. Uncomment the section relevant to the file type you want to recover (e.g., `.jpg` for JPEG images).
3. Save the changes and close the file.
4. Run the following command: `scalpel -o <output> <disk image file>`.
   - `-o <output>` specifies the output directory where recovered files will be stored (must be empty or non-existent).
   - `<disk image file>` indicates the disk image file to search for files inside.
   - Example command: `scalpel -o /root/Desktop/ScalpelOutput DiskImage1.img`.
5. Wait for `scalpel` to complete the process and retrieve the files.
6. Check the specified output directory to access the recovered files.

The `scalpel` tool identifies and extracts the specified file types based on the configuration in `scalpel.conf`. It creates an output directory to store the recovered files.

Note: Custom detection profiles can be created in `scalpel.conf` by modifying file extension, header, and footer values. Refer to the file's top section for detailed information on creating custom detection profiles.

Understanding metadata and utilizing file carving techniques are valuable skills for digital investigators. They help uncover hidden information, provide context, and retrieve deleted files for further analysis.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 19th 2023 (02:54 pm) 
Last Modified Date: June 19th 2023 (02:54 pm)
