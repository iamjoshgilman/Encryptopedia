---
creation date: August 24th 2023
last modified date: August 24th 2023
aliases: []
tags: #📖
---

Primary Categories: [[000 - Global Index]] | [[01 - Administration]] 
Secondary Categories: [[02 - Windows]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Windows File Permissions]]  

# Overview:

- **System Used**: Windows employs a **granular permissions system** for its files and folders.
- **Key Component**: Each file/folder's permissions are stored in the **Access Control List (ACL)**.

## **Accessing the ACL:**

1. **Right-click** the desired file/folder.
2. Choose **'Properties'** from the dropdown.
3. Click on the **'Security'** tab.

### **Inside the ACL:**
- Displays users/groups and their permissions.
- **Modifying Permissions**: Use the 'Edit' button to adjust permissions.

## **Important Notes on Permissions:**

- **Allowed vs. Denied**: Permissions can either be set to **Allowed** or **Denied**.
- **Priority**: A **Deny** permission always supersedes an **Allow**.
- **Defaults**: If permissions are not specified, the system defaults to **deny all**.

## **File Permissions:**

- **Full Control**: All permissions granted.
- **Modify**: Read, write, modify, execute.
- **Read & Execute**: View and run (if executable).
- **Read**: View only.
- **Write**: Add data.

## **Folder Permissions:**

- **Full Control**: Access to everything in the folder.
- **Modify**: Read, write, modify, execute inside.
- **Read & Execute**: View and run files.
- **List Folder Contents**: View contents.
- **Read**: View folder and its contents.
- **Write**: Add content.

## **Permission Inheritance:**

- **Inherited**: Files within a folder inherit permissions from it.
- **Overlap**: Files inherit "Read & Execute" due to lack of "List Folder Contents" for files.

## **Key Takeaways:**

- Use ACL for managing permissions.
- "Deny" takes precedence over "Allow".
- Distinct permissions exist for files and folders.

## **Best Practices:**

- Adhere to the **principle of least privilege**.
- Use "Deny" sparingly.
- **Regular Check**: Review ACLs periodically, especially for crucial data.

---

I hope this format is more organized and visually appealing!



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 24th 2023 (08:30 pm) 
Last Modified Date: August 24th 2023 (08:30 pm)
