---
creation date: July 31st 2023
last modified date: July 31st 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Malware Analysis]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Binary Patching & Anti-analysis]]  
___

# Binary Patching

Binary patching involves modifying a binary executable by changing its machine code instructions, often for the purpose of reversing, cracking, or modifying the binary's behavior. 

## Concepts:

1. **Hex Editors**: Tools like HxD, Hex Fiend, or Ghidra can be used to modify the binary data.

2. **Debuggers and Disassemblers**: Debuggers like x64dbg or OllyDbg and disassemblers like IDA Pro or Ghidra can provide a more comprehensible view of the code and allow patching.

3. **Patching Process**: Involves finding the location of the machine code instruction to change (often a conditional jump or function call), and replacing it with NOPs (no operation instructions), a jump to a different location, or new instructions.

## Use Cases:

1. **Cracking Software**: Modifying condition checks that involve software licensing or authentication.

2. **Malware Analysis**: Disabling certain harmful functions in malware for safe analysis.

# Anti-Analysis Techniques

Anti-analysis techniques are methods employed by malware authors to hinder or evade analysis of their malware. These techniques make it more difficult for researchers and automated tools to understand the malware's behavior, functionality, and impact.

## Techniques:

1. **Obfuscation**: Code or instructions are obscured, making analysis more difficult. This can involve packing, encryption, or complex code constructs.

2. **Environment Checks**: The malware checks whether it's being run in a sandbox or virtual environment, and alters its behavior if it detects such an environment.

3. **Anti-Debugging**: Techniques to detect or disrupt debugging. This can involve timing checks, exception handling, or checking for artifacts of a debugger.

4. **Anti-Disassembly**: Techniques to disrupt disassembly of the code. This can involve inserting invalid or misleading instructions that confuse disassemblers.

## Countermeasures:

1. **Static Analysis**: Use tools that can statically analyze the binary, like IDA Pro or Ghidra, to see through some obfuscation techniques.

2. **Debugging**: Use advanced debugging techniques, like stealth debugging or hardware breakpoints, to work around anti-debugging techniques.

3. **Emulation**: Emulate instead of executing the malware to avoid environment checks.

4. **Deobfuscation Tools**: Use specialized tools that can deobfuscate or unpack the malware to reveal the underlying code.




___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: July 31st 2023 (08:03 pm) 
Last Modified Date: July 31st 2023 (08:03 pm)
