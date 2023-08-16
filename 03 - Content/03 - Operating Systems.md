---
creation date: August 16th 2023
last modified date: August 16th 2023
aliases: []
tags: #📖
---

Primary Categories: [[02 - GFACT]] | [[000 - Cybersecurity Materials]]
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Operating Systems]]  


[[#What is an Operating System?]]
[[#What is the Kernel?]]
[[#Understanding Processes]]

# What is an Operating System?

- An **Operating System (OS)** is the foundational software on a computer.
- It **manages** the computer's operations and **interacts** with hardware components.
- Provides essential features including:
  - **Window Management**: Ability to organize, resize, and move application windows.
  - **Copy and Paste**: Facilitating data transfer within or between applications.
  - **Peripheral Management**: Recognizes and communicates with external devices like mice, keyboards, printers, etc.

## Different Operating Systems:

- Multiple OS choices available, each with distinct characteristics.

### 1. Windows:

- Developed by Microsoft.
- Dominates the desktop and laptop market.
- Known for user-friendly interfaces and wide software compatibility.

### 2. Ubuntu Linux:

- A popular distribution of the **Linux** OS.
- Open-source and community-driven.
- Preferred for its security features and customizability.

### 3. Mac OS:

- Developed by Apple for its Mac computers.
- Known for sleek design and robust performance.
- Offers a seamless experience with other Apple products like iPhone, iPad, etc.

### 4. Android:

- Primarily for mobile devices like smartphones and tablets.
- Developed by Google; open-source.
- Most widely used OS for mobile devices due to its versatility and extensive app ecosystem.
## Selection Considerations:

1. **Personal Preference**: The feel and user experience of an OS is subjective; some people might prefer one OS's interface over another.
  
2. **Task Specific**: Depending on the task, some OSs might be better suited. For instance, graphic designers might prefer Mac OS for certain software, while developers might lean towards Linux for development tasks.

3. **Compatibility**: The availability of desired software and compatibility with specific hardware can influence the choice.

4. **Cost**: While some OSs come pre-installed or are free (like certain Linux distributions), others might have licensing fees.

5. **Security and Updates**: The frequency of security patches and the general security architecture can be crucial for certain users.

---
# What is the Kernel?

- The **Kernel** is the fundamental component of an operating system.
- It is the **first** segment of the OS code to be loaded during the booting process.
- Acts as a bridge between **applications** and the **actual data processing** done at the hardware level.

## Key Responsibilities:

1. **Protection**: Positioned in a safeguarded memory region to ensure its integrity against unintended or malevolent interference from other software components.

2. **Resource Management**: Oversees shared hardware resources such as:
   - **RAM (Random Access Memory)**: Allocates memory for processes, ensuring efficient use and preventing memory leaks or overlaps.
   - **Hard Drive**: Manages file operations, storing, retrieving, and organizing data.
   
3. **Process Management**: Handles:
   - Process **creation**, **termination**, and **scheduling**.
   - Maintaining the **Process Control Block (PCB)**, which contains vital process information like its current state, priority, etc.
   
4. **I/O Management**: Directs the flow of input and output between the computer and external peripherals. This includes devices like keyboards, mice, printers, and more.

## A Simple Graphic Representation:

![[Pasted image 20230816183544.png]]

---
# Understanding Processes

## What is a Process?

- A **process** is a running instance of a program.
- Represents a program's **active execution state** including the program counter, processor registers, and system memory.
- Ensures programs function as intended, and facilitates multitasking where multiple programs can run concurrently.

## Key Characteristics:

1. **Life Cycle**:
   - **Creation**: Begins when a user or system initiates the loading of a program.
   - **Execution**: Actively runs and performs its tasks.
   - **Termination**: Completes its tasks or is forcibly closed.

2. **Process States**:
   - **Ready**: Awaits the processor's attention.
   - **Running**: Actively being executed by the processor.
   - **Blocked/Wait**: Awaiting an event or resource to continue.
   - **Terminated**: Has finished execution.

3. **Context Switching**:
   - Processes may alternate between different states, and the action of saving the state of a currently running process to resume another is known as **context switching**.

4. **Multiprocessing**:
   - Many modern systems support running multiple processes at once. This is achieved through techniques like multitasking and multi-threading.

## Practical Example: Google Chrome

1. When you open Google Chrome:
   - A **new process** is created for the main browser window.
   - This process contains all the data Chrome needs to function: memory addresses, variable values, etc.

2. **Tabs and Extensions**:
   - Modern browsers, like Chrome, often spawn **multiple processes** for different tabs, plugins, or extensions. This approach can improve performance and stability since the failure of one tab doesn't necessarily crash the whole browser.

---
# Understanding Interrupts

## Introduction to Interrupts

- An **interrupt** is a mechanism that allows a hardware device or a software program to communicate with the CPU, typically indicating an event that needs immediate attention.
- Interrupts pause the current operations of the CPU to handle urgent tasks.

## Types of Interrupts

### 1. Hardware Interrupts

- Generated by **hardware devices**, either internal or external to the computer.
  
- **Examples**:
  - **Keyboard**: Generates an interrupt when a key is pressed.
  - **Mouse**: Generates an interrupt when it is moved or clicked.
  - **Disk Drives**: Signals the completion of a read/write operation.

- Upon receiving an interrupt, the CPU saves its current state, executes the interrupt handler (a predefined routine), and then resumes its previous operation.

### 2. Software Interrupts

- Generated by **software applications** or the operating system itself.

- **Purpose**: Often used as a mechanism for software to request services from the operating system.

- **Examples**:
  - **System Calls**: When a program needs to perform actions like opening a file, reading from a disk, or establishing a network connection.
  - **Exceptions**: Such as divide-by-zero errors, which require special handling.

- Unlike hardware interrupts, software interrupts are usually anticipated and invoked intentionally by the programmer.

## Significance of Interrupts

1. **Responsiveness**: Ensure that the system reacts swiftly to external changes or user actions, like the immediate recognition of a newly plugged-in mouse.
  
2. **Multitasking**: Enables the CPU to efficiently switch between tasks and provide the illusion of simultaneous execution.
  
3. **Resource Management**: Efficiently manage and prioritize access to system resources.

4. **Safety and Control**: Software interrupts allow user programs to safely request potentially dangerous or privileged operations via the kernel, ensuring system stability and security.

---
# BIOS and UEFI

## Introduction to BIOS

- **BIOS** stands for **Basic Input Output System**.
- It's a type of firmware used during the boot process (start-up) of a computer.
- Stored in a chip on the computer's motherboard.
- The primary role of the BIOS is to **initialize** and test the system hardware components and then load the bootloader or operating system software.

---

## Key Functions of BIOS

1. **Power-on Self-test (POST)**: Upon starting the computer, BIOS performs a test to make sure all necessary hardware components are present and functioning properly.
  
2. **Boot Sequence**: Determines the order in which the computer will look for devices to boot from (e.g., USB drives, hard drives, CD-ROM drives).
  
3. **Setup Utility**: Allows users to configure hardware settings, including system settings like date and time.

4. **Software Interface**: Provides an interface for the operating system to interact with the hardware.

---

## UEFI: The Modern Successor

- **UEFI** stands for **Unified Extensible Firmware Interface**.
- Intended as a more advanced and modern replacement for BIOS.
- While it accomplishes similar tasks to BIOS, UEFI provides more capabilities.

### Advantages of UEFI over BIOS:

1. **Faster Boot Time**: UEFI's boot time is generally faster than BIOS.
  
2. **Secure Boot**: UEFI can prevent the loading of viruses and unauthorized bootloaders.
  
3. **Support for Larger Drives**: Supports hard drives larger than 2TB.
  
4. **Graphical Interface**: Can display images and use mouse pointers, providing a richer interface for user configuration.
  
5. **Modularity**: UEFI's architecture is modular, meaning individual pieces of the system's firmware can be updated without updating the entire UEFI.

---

## Key Takeaways

- Both **BIOS** and **UEFI** are integral components in the boot process of a computer.
- While they serve the same essential purpose, UEFI provides a more modern and versatile approach.
- **UEFI** has become the standard in newer systems, offering advantages in boot time, security, and compatibility.
- Despite the shift to UEFI, the term "BIOS" is often colloquially used to refer to the system's firmware, encompassing both traditional BIOS and UEFI.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 16th 2023 (06:56 pm) 
Last Modified Date: August 16th 2023 (06:56 pm)
