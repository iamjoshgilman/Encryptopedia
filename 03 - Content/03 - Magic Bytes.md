---
creation date: July 23rd 2023
last modified date: July 23rd 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Malware Analysis]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Magic Bytes]]

---
## What are Magic Bytes?

Magic bytes, also known as magic numbers, are specific numerical or string values used at the start of a file that can help to identify or verify the format of a file. 

## Why are Magic Bytes Important?

1. **File Type Identification**: Magic bytes allow software to quickly identify the type of a file without relying on the extension, which can be easily changed. For example, a .jpg file always starts with the bytes `FF D8 FF`.

2. **Data Validation**: Magic bytes can also serve as a rudimentary form of data validation. If a file doesn't start with the expected magic bytes, software can immediately know that the file is not of the expected format or that it may be corrupted.

## How are Magic Bytes Used?

1. **File Analysis**: Tools like `file` in Unix or Linux can read the magic bytes of a file to identify its type. This can be useful in forensics and data recovery, as well as in malware analysis to identify the type of a payload.

2. **Programming**: In programming, magic numbers are often used to mark or tag data. For example, a developer might use a specific magic number to mark the start of a session or a specific transaction.

3. **Malware Analysis**: In malware analysis, magic bytes can be used to identify the type of a file or a payload. For example, if a payload starts with the magic bytes of a .exe file, the analyst would know that the payload is an executable.

## Examples of Magic Bytes

Commonly used magic bytes and their associated file types:

| File Format | Magic Bytes (Hexadecimal) | Magic Bytes (ASCII) |
|-------------|---------------------------|---------------------|
| JPEG        | FF D8 FF                  |                     |
| PNG         | 89 50 4E 47 0D 0A 1A 0A   | .PNG...             |
| GIF         | 47 49 46 38               | GIF8                |
| PDF         | 25 50 44 46               | %PDF                |
| ZIP         | 50 4B 03 04               | PK..                |
| RAR         | 52 61 72 21 1A 07 00      | Rar!...             |
| 7Z          | 37 7A BC AF 27 1C         | 7z...'              |
| ELF         | 7F 45 4C 46               | .ELF                |
| PE/EXE      | 4D 5A                     | MZ                  |
| MP3         | FF FB                     | ÿû                  |
| WAV         | 52 49 46 46               | RIFF                |
| AVI         | 52 49 46 46               | RIFF                |
| MP4         | 00 00 00 18 66 74 79 70   | ....ftyp            |
| ISO         | 43 44 30 30 31            | CD001               |
| BMP         | 42 4D                     | BM                  |
| DOCX, XLSX, PPTX | 50 4B 03 04          | PK..                |





___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: July 23rd 2023 (02:14 pm) 
Last Modified Date: July 23rd 2023 (02:14 pm)
