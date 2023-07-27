---
creation date: July 26th 2023
last modified date: July 26th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Malware Analysis]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Advanced Static Analysis]]  

Advanced static analysis involves examining the malware's code without executing it. This process often requires a thorough understanding of low-level programming languages, especially assembly language. Tools like disassemblers and decompilers can aid in this process, allowing researchers to look at the program's instructions.

## Assembly Language

Assembly language is a low-level programming language specific to a particular computer architecture. In the context of malware analysis, understanding assembly language is essential to figure out the malware's operation, as malicious programs often utilize assembly language for its fine control over the system.

Key aspects to understand include:

- **Registers**: These are small storage areas where temporary data is kept. Important registers include EAX, EBX, ECX, EDX, ESI, EDI, EBP, ESP, and EIP.
- **Instructions**: These are commands that perform operations, such as moving data, comparing values, or altering the program flow. Examples include MOV, ADD, SUB, MUL, JMP, JNZ, etc.
- **Flags**: These indicate the status of a mathematical operation and influence the flow of the program. They include Overflow flag, Direction flag, Interrupt flag, etc.

## Disassembling

Disassembling is the process of converting machine code into assembly language. Disassemblers are tools used for this purpose. A disassembler can convert the malware binary into an easier-to-read format for those who understand assembly language. 

Here are some popular disassemblers:

- **IDA Pro**: An industry standard, IDA Pro offers various features like a robust debugging suite, multi-architecture support, and graphing capabilities.
- **Ghidra**: A free and open-source tool developed by the NSA that includes a disassembler and decompiler. It's widely used due to its powerful capabilities and zero cost.
- **Radare2**: This is a free, open-source reverse engineering framework that includes a disassembler among many other tools.

## Decompiling

Decompiling is the process of translating a program's binary code into a higher-level language, usually C or C++. A decompiler can make the code even more readable and accessible if you don't have a deep understanding of assembly language.

Here are some popular decompilers:

- **Ghidra**: As well as being a disassembler, Ghidra also includes a powerful decompiler.
- **Hex-Rays Decompiler**: An add-on for IDA Pro, it can decompile code into C-like syntax.

## Advanced Static Analysis Process

1. **Identify Key Binary Components**: Examine the PE header and sections to get a sense of the binary's layout and key components.
2. **Disassemble the Binary**: Use a tool like IDA Pro or Ghidra to disassemble the binary and examine the assembly code.
3. **Identify Key Subroutines**: Look for key subroutines that could represent the malware's main functionality.
4. **Decompile the Binary**: If possible, decompile the binary to get a more readable representation of the code.
5. **Analyze the Code**: Examine the code in detail, looking for operations like file manipulation, network communication, or system changes.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: July 26th 2023 (10:01 pm) 
Last Modified Date: July 26th 2023 (10:01 pm)
