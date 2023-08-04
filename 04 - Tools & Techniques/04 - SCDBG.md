---
creation date: August 3rd 2023
last modified date: August 3rd 2023
aliases: []
tags: #🧰
---

Primary Categories: [[01 - Malware Analysis]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #🧰  

# [[04 - SCDBG]]  
___
# scdbg (Shellcode Debugger)

`scdbg` is a tool designed to assist analysts in the testing, debugging, and reverse engineering of shellcode. Shellcode is a small piece of code used as the payload in the exploitation of a software vulnerability.

## Description:

`scdbg` is not a full-featured debugger but a way to emulate the functionality of shellcode to determine its purpose. It can handle a variety of shellcode inputs and provide detailed output on what the shellcode is doing.

## Installation:

`scdbg` is available for download from the official [SecuritySift website](http://securitysift.com/download-tools/). As of my knowledge cutoff in September 2021, there is no official package available for package managers like `apt` or `brew`.

## Usage:

The basic usage of `scdbg` is straightforward. You need to provide it with shellcode to analyze, either directly on the command line or in a file.

- Analyze shellcode from a file:

```bash
scdbg <filename>
```

- Analyze shellcode directly:

```bash
scdbg -f <shellcode>
```

Where `<shellcode>` is a string of shellcode that you want to analyze and `<filename>` is the name of a file containing shellcode.

## Features:

1. **Shellcode Emulation**: `scdbg` can emulate the execution of shellcode, providing detailed reports on its functionality without executing it in a live environment.

2. **Input Format Options**: `scdbg` can handle a variety of shellcode inputs, including ASCII, Unicode, WideChar, Hex, and Binary.

3. **Code Graphing**: `scdbg` can create a flow chart of the shellcode execution, which can be useful for understanding complex shellcode payloads.

4. **API Logging**: `scdbg` will record any Windows API calls made by the shellcode, providing insight into what it's attempting to do.

5. **Memory Dump**: `scdbg` can dump the shellcode's memory, allowing for further analysis of its state at various points during execution.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 3rd 2023 (09:13 pm) 
Last Modified Date: August 3rd 2023 (09:13 pm)
