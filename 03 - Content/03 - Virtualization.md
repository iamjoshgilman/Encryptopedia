---
creation date: August 16th 2023
last modified date: August 16th 2023
aliases: []
tags: #📖
---

Primary Categories: [[02 - Foundations]] | [[000 - Cybersecurity Materials]]
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Virtualization]]  

[[#Definition of Virtualization]]
[[#Hypervisors]]
[[#Uses of Virtualization]]


# Definition of Virtualization

- Virtualization allows for the creation of a virtual computer or **virtual machine (VM)** made from software that simulates the behavior of a separate computer.
- In VMs, hardware components are all software-based.
- The VM uses the hardware resources of the host computer it runs on.
- This concept is facilitated using a **hypervisor**, which acts as an intermediary layer, disrupting the direct relationship between an OS and the hardware.

**Key Point**: Virtualization lets us run one operating system inside another. E.g., Windows inside Linux.
### Hypervisor

- A crucial component in virtualization.
- Breaks the conventional 1:1 relationship between the OS and hardware.
- There are different types of hypervisors which will be explored later.
### Examples of Virtualization

- Running Windows 10 inside VMware Workstation (a virtualization software) on top of an Ubuntu Linux system.
- Conceptually: Running Windows and Mac OS X concurrently or Windows while running Linux.
### Host Operating System

- The main operating system that runs the virtualization software.
- Considered the "master" OS as it is the first to load when the physical computer is powered on.
### Guest Operating System

- The OS running within the virtual machine.
- Isolated from the host OS and doesn't have direct access to host resources.
**Example**: If Windows is the host and Linux is the guest, Linux can't directly access files on the Windows desktop.
### Importance of Separation

- The separation between the host and guest OS is vital for security reasons.
- E.g., When analyzing a computer virus, using a VM ensures the host OS remains unaffected and prevents the virus from escaping to the internet.

**Key Practices to Remember**:
1. Always be aware of which OS is your host and which one is the guest.
2. For tasks with security implications (like malware analysis), always use a VM to maintain a safe environment.

---
# Hypervisors

## What is a Hypervisor?

- A hypervisor is a layer of code that facilitates multiple operating systems to share the same hardware resources.
- It acts as the traffic director, determining memory allocation for virtual machines, storage locations for VM hard disks, and more.
## Types of Hypervisors

### Type 2 Hypervisor

- **Definition**: Virtualization performed by software that operates on an existing operating system.
- **Use in Course**: This type of virtualization will be primarily used throughout this course.
**Popular Type 2 Hypervisor Softwares**:
  - VMware Workstation
  - Virtualbox

**Key Point**: Convenient for regular users and desktop environments.
### Type 1 Hypervisor

- **Definition**: Virtualization that takes place at the firmware level. In this type, there's no host operating system; the virtualization software itself acts as the host.
- **Usage**: Widely used in server settings, especially data centers that are part of 'the cloud'.

**Key Point**: More efficient than Type 2 but not typically used for personal computers.

**Popular Type 1 Hypervisor Softwares**:
  - VMware vSphere
  - Proxmox

**Things to Remember**:

1. **Type 2 Hypervisor**:
   - Virtualization via software on an existing OS.
   - Suited for regular users.
   - Examples: VMware Workstation, Virtualbox.

2. **Type 1 Hypervisor**:
   - Virtualization at the firmware level; it is essentially the host OS.
   - Primarily for servers and data centers.
   - Examples: VMware vSphere, Proxmox.

**Diagram to Visualize**:

![[Pasted image 20230816185951.png]]

---
# Uses of Virtualization

### **Importance of Virtualization**

- A significant portion of the internet runs on virtualized servers.
- Most cloud services, like "the cloud", utilize **Type 1 hypervisors**.
- Virtualization provides major efficiency improvements, especially for large-scale operations.
### **Web Hosting & Scaling**

- **Scenario**: Websites that experience varying traffic—low at times but sudden spikes at others.
  - Without Virtualization: Need to maintain a server that can handle peak traffic, leading to underutilization during off-peak times.
  - With Virtualization: Run the site on a small virtual machine and dynamically add VMs during high traffic periods. Scale down by deleting extra VMs during off-peak times.

**Key Players**: Cloud hosting providers like **Amazon AWS** use virtualization for this scalability.
### **Uses in Cyber Security**

- Predominantly, **Type 2 hypervisors** are used in cybersecurity.
- Why?
  1. **Multiple OS Needs**: Some tools are OS-specific, necessitating both Windows and Linux access without rebooting to switch.
  2. **Safety**: Isolation ensures that tasks done in the guest OS won't harm the host OS.
      - E.g., Analyzing malware without jeopardizing the main system.
  
**Key Reminder**: When analyzing malware, disable all communication methods within the VM, such as virtual network adapters.
### **Uses in Software Development**

- Developers use VMs for testing software across various environments.
- **Scenario**: Developing on Windows but need to test on Linux.
  - Without Virtualization: Multiple installations or systems.
  - With Virtualization: Easily create a Linux VM on the Windows system for quick testing.

**Key Points to Remember**:

1. Virtualization isn't just a niche; it's foundational to many modern internet services.
2. It allows for dynamic scaling, making resources more cost-effective and efficient.
3. Cybersecurity professionals depend on virtualization for both convenience and safety.
4. Developers can quickly replicate different environments for testing purposes using VMs.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 16th 2023 (06:07 pm) 
Last Modified Date: August 16th 2023 (06:07 pm)
