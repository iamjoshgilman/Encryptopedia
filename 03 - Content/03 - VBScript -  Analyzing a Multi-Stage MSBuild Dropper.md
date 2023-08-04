---
creation date: August 3rd 2023
last modified date: August 3rd 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Malware Analysis]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - VBScript -  Analyzing a Multi-Stage MSBuild Dropper]]  
___

MSBuild droppers are a type of malicious software that use Microsoft's build engine, MSBuild, to compile and execute malicious code. They can be difficult to detect because they abuse legitimate software and often operate in multiple stages to further obfuscate their activities. Here's a basic outline for analyzing a multi-stage MSBuild dropper delivered via VBScript:

## 1. Initial VBScript Analysis
The initial delivery vector is often a VBScript file. Start by examining the VBScript content.

- Look for obfuscation techniques such as character substitution, Base64 encoding, or encrypted strings. 

- Pay attention to the use of `CreateObject` which is often used to interact with other Windows components.

- Use a VBScript beautifier to make the code more readable.

## 2. Unpacking the Payload
The initial VBScript is often used to unpack or decrypt the next stage of the payload.

- Try to identify the decryption or unpacking algorithm used.

- Look for function calls that write out new files to disk.

- Consider running the VBScript in a controlled environment to see what files it creates.

## 3. Analyzing the MSBuild Project
The next stage is often a .csproj (C# project file) or .xml file to be compiled and executed by MSBuild.

- Understand that MSBuild can include inline C# code, which is a common method for hiding malicious activity.

- Look for `<Target>` elements, which define tasks to be executed.

- Be aware that obfuscation techniques can be used here too, such as Base64 encoding or encrypted strings.

## 4. Understanding the Final Payload
The MSBuild project usually compiles and executes the final payload.

- Attempt to retrieve the final payload's code, possibly from inline C# code or from an external file.

- Analyze the final payload to understand the purpose of the malware. This could involve file system analysis, network analysis, or reverse engineering of any binaries involved.

## 5. Useful Tools

- **VBScript Beautifier/Formatter:** Online services or IDEs can help to make obfuscated VBScript code more readable.

- **Decoders/Decrypters:** Online or local tools can help decode Base64 strings or decrypt strings, depending on the encryption used.

- **Disassemblers/Debuggers:** Tools like Ghidra, IDA Pro, or x64dbg can help in reverse engineering any binary components.

- **Dynamic Analysis Tools:** Sandboxing tools, or tools like Wireshark for network analysis, can provide insights into the behavior of the payload.




___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 3rd 2023 (09:21 pm) 
Last Modified Date: August 3rd 2023 (09:21 pm)
