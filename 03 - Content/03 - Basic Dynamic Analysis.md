---
creation date: July 25th 2023
last modified date: July 25th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Malware Analysis]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Basic Dynamic Analysis]]  

---
Dynamic analysis, also known as behavioral analysis, involves analyzing a program while it is running. In the context of malware, it is used to observe and document the behavior of a piece of malware as it interacts with a system.

## Purpose

1. **Identify Malware Behavior**: Dynamic analysis helps to identify what the malware does when it's executed, such as which files it changes, what network activity it triggers, and what changes it makes to the registry.

2. **Understand Attack Vectors**: It helps to understand how the malware infects systems, how it propagates, and what vulnerabilities it exploits.

3. **Create Signatures**: The observed behavior can be used to create signatures for intrusion detection systems (IDS) and antivirus software.

4. **Develop Countermeasures**: By understanding the behavior of the malware, researchers can develop countermeasures to neutralize it.

## Process

1. **Set up Environment**: First, set up a controlled environment, usually a virtual machine, to run the malware. The environment should be isolated to prevent accidental infections.

2. **Execute Malware**: Execute the malware within the controlled environment and let it run.

3. **Monitor**: Use monitoring tools to track what happens when the malware runs. Track changes to the file system, the registry, and network activity.

4. **Analyze**: After execution, analyze the collected data to understand what the malware does. 

## Tools

1. **Virtual Machines**: VMWare, VirtualBox - These create isolated environments where malware can safely be executed.

2. **Monitoring Tools**: Process Monitor, Regshot - These track changes to the system.

3. **Network Monitoring Tools**: Wireshark - This tracks network activity.

4. **Automated Analysis Platforms**: Cuckoo Sandbox - These can automatically execute and analyze malware in an isolated environment.

## Precautions

- Always perform dynamic analysis on an isolated machine to avoid accidental damage or spreading of the malware.
- Be aware that some sophisticated malware can detect virtual environments and alter their behavior accordingly - This is where the Remnux "DNS" server running 



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: July 25th 2023 (11:26 am) 
Last Modified Date: July 25th 2023 (11:26 am)
