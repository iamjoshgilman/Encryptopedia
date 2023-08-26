---
creation date: August 26th 2023
last modified date: August 26th 2023
aliases: []
tags: #📖
---

Primary Categories: [[000 - Global Index]]  
Secondary Categories: [[02 - Foundations]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Containers]]  

## Containers vs. Virtualization

Both containers and virtual machines (VMs) offer ways to isolate applications and their runtime environments, but they achieve this in fundamentally different ways. Understanding the differences can help you decide which approach is best suited for your needs.
### Containers:

**1. Lightweight:** Containers virtualize at the application layer. This means they package the application and the necessary binaries and libraries but not an entire OS, resulting in a much smaller footprint.

**2. Speed:** Because they don't carry the overhead of entire virtual machines, containers can start almost instantly.

**3. Portability:** A containerized app can run consistently across multiple environments since it carries its dependencies with it. This aids in the "write once, run anywhere" concept.

**4. Efficiency:** Containers are known to have a smaller performance overhead than VMs since they share the same OS kernel.

**5. Management:** Container orchestration tools, like Kubernetes, offer powerful management capabilities for deploying, scaling, and operating containerized applications.
### Virtual Machines:

**1. Full Isolation:** Each VM runs its independent OS, making it completely isolated from other VMs on the same host.

**2. Diverse OS:** VMs can run multiple different OSs on the same physical host. For example, Linux and Windows VMs can coexist on the same physical server.

**3. Overhead:** Each VM includes a full OS instance, which results in more overhead in terms of storage, memory, and compute compared to containers.

**4. Management:** Hypervisor tools, such as VMware or Hyper-V, help in managing VMs.
### Some Key Takeaways:

1. **Use Case Specific:** If you need to run multiple instances of the same OS and aim for maximum density and efficiency, containers might be the way to go. On the other hand, if you require running different OSs or need full OS isolation for security reasons, VMs are more appropriate.

2. **Layer of Virtualization:** VMs virtualize the hardware, i.e., they operate on a hypervisor which runs directly on the bare metal or on top of an operating system. Containers virtualize the OS, meaning all containers on a host share the same OS kernel.

3. **Combining Both:** In some cases, organizations use both containers and VMs, taking advantage of VM isolation and container efficiency. For example, they might run multiple containers inside a VM.

___










___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 26th 2023 (10:26 am) 
Last Modified Date: August 26th 2023 (10:26 am)
