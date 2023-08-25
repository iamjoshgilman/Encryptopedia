---
creation date: August 24th 2023
last modified date: August 24th 2023
aliases: []
tags: #📖
---

Primary Categories: [[]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - CPU Components]]  

___
# Overview
The CPU (Central Processing Unit) is the primary component responsible for executing computer programs. Its core components include the Control Unit, Arithmetic Logic Unit, and Registers.
## Control Unit (CU)
- **Definition**: The Control Unit directs the execution of program instructions by sending electrical signals to the computer system.
- **Analogy**: 
  - Think of the CU as the **director of a movie** or the **conductor of an orchestra**.
  - It doesn't execute program instructions directly but guides other parts of the computer to do so.
## Arithmetic Logic Unit (ALU)
- **Function**: Performs arithmetic and logical operations.
### Arithmetic Operations
1. **Addition**: Adds values.
2. **Subtraction**: Deducts values.
3. **Multiplication**: Multiplies values.
4. **Division**: Divides values.
### Logical Operations
- Responsible for making comparisons between values.
1. **Equal-To**: Determines if two values are identical.
2. **Less-Than**: Checks if one value is smaller than another.
3. **Greater-Than**: Compares if one value exceeds another.
4. Additional Operations:
   - **NOT**: Negates a comparison, e.g., NOT Equal To (two values are different).
   - **OR**: Checks for multiple conditions, e.g., Less Than OR Equal To.

> Note: More detailed exploration of logical operations will be covered in the data modules.
## Registers
- **Definition**: Small memory units physically inside the CPU.
- **Features**:
  - **Faster than RAM**: Due to their location inside the CPU, electrical signals have minimal distance to travel.
  - **Limited Capacity**: There are few registers, and they can hold a very restricted amount of data.
  - Explored in detail in the section on CPU registers.
## Register Capacity based on Architecture
- **32-bit architecture**: 
  - Register capacity: 32 bits of data
  - Equivalent to: 4 bytes or 4 characters (using ASCII encoding)
- **64-bit architecture**: 
  - Register capacity: 64 bits of data
  - Equivalent to: 8 bytes or 8 characters (using ASCII encoding)
## General Purpose Registers

### For 32-bit Intel CPU (x86)
Four primary registers that can be divided into sub-registers:
1. **EAX**: 
   - Divided into AX, AL (lower 8 bits of AX), and AH (higher 8 bits of AX)
2. **EBX**: 
   - Similar to EAX, it can be split as BX, BL, BH
3. **ECX**
4. **EDX**

|_8 bits_|_8 bits_|_8 bits_|_8 bits_|
|---|---|---|---|
|EAX|EAX|EAX|EAX|
|||AX|AX|
|||AH|AL|

> Note: Accessing different sections of a register (like AH or AL) doesn't change the overall register. You're just viewing specific portions of it.
### Other General Purpose Registers
These are less divisible than the primary ones:
1. **ESP (Stack Pointer)**: Points to the top of the current stack frame in RAM.
2. **EBP (Base Pointer)**: Points to the bottom of the current stack frame in RAM.
3. **ESI (Source Index)**: Holds the memory address of source data in operations.
4. **EDI (Destination Index)**: Contains the destination memory address for operations.

> Caution: While named 'general purpose', some registers serve specific functions. Indiscriminate data storage in them can lead to issues.
## Special Purpose Registers
Registers reserved for specific tasks and can't be freely manipulated by most programs.
- **EIP (Instruction Pointer)**: 
  - Specific to 32-bit Intel x86 processors.
  - Holds the memory address of the next CPU instruction.

> Note: There are more special purpose registers, but they are omitted here for simplicity.
## Key Takeaways
1. **General Purpose Registers**:
   - Primary registers on 32-bit CPUs are divisible, and each segment refers to a specific portion.
   - There are registers with specific functions like stack pointers and index holders.
2. **Special Purpose Registers**: Reserved for crucial tasks, the most prominent being the instruction pointer.




___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 24th 2023 (09:04 pm) 
Last Modified Date: August 24th 2023 (09:04 pm)
