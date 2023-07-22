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

# [[03 - Linux Artifacts - User Files]]  
---

## Bash History

- Location: The `.bash_history` file is located in a user's home directory. It is a hidden file and can be revealed using the command `ls -a`.
- The `.bash_history` file contains a list of commands executed by the specific user.
- Use the command `history` in the terminal to display the command history.
- Users can clear the terminal history using the `history -c` command, but the commands are still stored in the `.bash_history` file.

Example:
```bash
$ cat .bash_history        # View the contents of .bash_history
$ history                  # Display the command history
```

- Reviewing the `.bash_history` file can reveal executed commands, including potentially relevant actions such as running scans or accessing sensitive files.

## Hidden Files and Directories

- Files or directories that begin with a dot (`.`) are considered hidden in Linux systems.
- By default, these hidden files are not displayed when using the `ls` command.
- Use the `ls -a` command to view all files, including hidden ones.
- Hidden files can be used to hide sensitive or incriminating data.

Example:
```bash
$ ls                # Display visible files and directories
$ ls -a             # Display all files and directories, including hidden ones
```

## Clear Files and Directories

Clear files are accessible through standard means such as the terminal or graphical browser. They include:

- User's desktop
- User's default directories: Downloads, Music, Pictures, Public, Templates, Videos
- The Trash Bin

To search for clear files, navigate to the corresponding directories or use a file browser. These files may contain useful information if not deliberately hidden by the user.

## Steganography

Steganography involves concealing messages or information within non-secret text or data. This technique can hide files or messages within innocent-looking files, making data harder to find. Steganography can be employed in various ways:

1. Hiding ZIP Files Inside Images:
   - Files can be hidden by combining them with image files.
   - Example: Using the command `cat Dog.jpg secretmessage.zip > Dog2.jpg` to insert a ZIP file into an image file.

2. Using Steghide to Hide and Retrieve Files:
   - Steghide is a tool that can embed files within other files, known as cover files.
   - Example: Using the command `steghide embed -cf Dog.jpg -ef secretmessage` to hide a file inside Dog.jpg.
   - To extract the hidden file, use the command `steghide extract -sf Dog.jpg`.

3. Hiding Strings in Metadata:
   - Text strings can be inserted into the metadata of a file.
   - Example: Using the command `exiftool -Comment="Super Sneaky!" Dog.jpg` to embed the phrase "Super Sneaky!" in Dog.jpg's metadata.
   - Retrieve the metadata using the `exiftool` command.

Note: Hiding files with passwords or encoding techniques can make it more challenging for forensic investigators, but tools like StegCracker can be used to attempt password recovery.

It's important to be aware of these techniques and thoroughly examine user files to uncover potential hidden information or evidence.

References:

- TechTarget article on steganography: [Link](https://www.techtarget.com/searchsecurity/definition/steganography)
- StegCracker GitHub repository: [Link](https://github.com/Paradoxis/StegCracker)
- ExifTool: [Link](https://exiftool.org/)


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 20th 2023 (01:44 pm) 
Last Modified Date: June 20th 2023 (01:44 pm)
