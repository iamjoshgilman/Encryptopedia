---
creation date: June 16th 2023
last modified date: June 16th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Security Fundamentals]] [[000 - Global Index]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Change and Patch Management]]  
---

## Change Management
- The process of ensuring that changes within an organization are planned, supported, well documented, and audit-able. In regards to cybersecurity, this allows us to identify the accountability of individuals or teams if a change results in a security risk, especially if it has been exploited.
	- From our perspective, if we are trying to get systems patched, we may be asked to raise (or assist in raising) a change request so that it can be reviewed, key stakeholders identified, and the whole process of patches being deployed can be well documented. The same could occur if we are making major security changes, such as editing security controls on employee systems or editing rules on a firewall.
	- By having a record of who made what changes, we can quickly identify individuals involved should we need to ask them questions about the activity they conducted.

## Patch Management
- process relating to IT administration, but can also be very closely associated with vulnerability management. It involves the ability to deploy patches and security fixes to IT assets that require them, such as Windows updates to laptops and servers, and new versions of software such as web browsers.
	- By deploying patches, an organization can remediate vulnerabilities that are present in older versions of software or the operating system and reduce the risk to the company. Some businesses may also choose to meet stricter patching requirements for compliance frameworks such as Security Essentials+, which can be a business enabler as clients must not work with companies that do not hold this qualification. Under this framework, critical and high-rated vulnerabilities must be remediated within 14 days of discovery to ensure compliance.

### Windows Server Update Services (WSUS)
- enables IT teams to deploy the latest Microsoft product updates. You can use WSUS to fully manage the distribution of updates that are released through Microsoft Update to computers on your network.
	- In a WSUS implementation, at least one WSUS server, known as an “upstream server” on the network must be able to connect to Microsoft Update to get available update information. 
	- This means that endpoints and servers do not need to have an internet connection to download patches themselves – the upstream WSUS server will be the single system that communicates on the internet, downloads the patches, and deploys them to all systems that require them.

### Microsoft System Center Configuration Manager (SCCM)
- Paid solution that acts as an asset inventory, assists in software installation, and deploys updates and security patches to systems across the network. 
	- SCCM uses Microsoft’s WSUS as we covered above to check for and install updates, however, it provides users with additional patch management control over when and how patches are applied.
	- Non-Windows systems including Mac and Linux can be managed in a limited way through SCCM, but this poses a number of problems and 3rd-party patching requires additional configuration and is more work, compared to a solution that is designed to patch multiple operating systems and software products.
	- SCCM is built first and foremost for Windows systems and therefore its functionality and updates are focused on Windows. 

### Commercial Patch Management Solutions:
- There is a wide range of commercial solutions out there that are either designed purely to conduct patch management or offer this as part of a wider range of endpoint-based tools in a larger solution. To highlight some of the functionality these tools can include, we’re going to focus on ManageEngine Patch Manager Plus. The functionality this solution offers includes:
	- Deploy patches to Windows, MacOS, and Linux-based systems
	- Update operating systems
	- Update Microsoft Office software (widely used across organizations)
	- Update 3rd party applications such as Adobe products (Reader, Acrobat, Flash Player), browsers (internet explorer, chrome, Firefox, Edge), and utilities (7zip, CCleaner, and more)
	- Scan endpoints to detect any missing patches and report this to show patch compliance across the environment
- One additional way commercial tools can aid organizations in effectively deploying patches is by managing the patch testing phase, transferring the risk away from the internal IT team.




___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 16th 2023 (11:08 am) 
Last Modified Date: June 16th 2023 (11:08 am)
