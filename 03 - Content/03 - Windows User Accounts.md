---
creation date: August 24th 2023
last modified date: August 24th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Administration]] | [[000 - Global Index]] 
Secondary Categories: [[02 - Windows]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Windows User Accounts]]  

___
## Overview
- A user account allows you to sign in to a computer.
- Multiple default accounts are generated during the installation of an OS like Windows.
## Default Accounts in Windows

### Administrator:
  - Has almost complete control over the system.
  - Manages other users, installs applications, etc.
### **Guest**:
  - For users without a permanent account on the system.
  - Limited capabilities; needs to be secure against misuse.
### **Default Account**:
  - Template for new user accounts.
  - Alterations affect all subsequent user accounts created.
- *Note*: All these accounts are **disabled** by default.
## Account Types in Windows 10
### **Administrator**:
  - Can affect all users.
  - Modifies other accounts, installs apps, adjusts security settings.
### **Standard**:
  - Can perform most Administrator tasks.
  - Cannot execute actions that affect all users.
### **Child**:
  - Essentially a Standard account.
  - Parental controls are active by default.
  - Monitors/limits usage time; can only be formed within a family group.
## Creating a New User

- Most shared machines require multiple user accounts.
- Several methods exist to create user accounts in Windows.
### Using Control Panel
1. **Access Control Panel**:
   - Click 'Start' > 'Settings' (cog icon).
   - Choose 'Accounts'.
2. **Navigate to Family & Other People**:
   - Select 'Family & other people' to manage other user accounts.
   - Click on 'Add someone else to this PC'.
3. **Fill Account Details**:
   - Set username and password.
   - Initially, only Standard user account type is available.
4. **Modify Account Type** (if needed):
   - Choose 'Change account type'.
   - Select 'Standard User' or 'Administrator'.
5. **Delete User Account** (use caution):
   - Select 'Remove'. 
   - Warning: Deletes all user data.
### Using Local Users Management Console (lusrmgr.msc)
1. **Access Console**:
   - Click 'Start' > type 'lusrmgr.msc'.
   - Select 'Users' to view existing accounts.
2. **Create New User**:
   - Right-click > 'New User'.
   - Fill in details with more customization options.
   - Can set initial password constraints or account status.
## Key Points to Remember
- **Administrator** has extensive system control.
- **Guest** account is for temporary users and should be safeguarded.
- **Child** accounts have built-in parental controls.
- **DefaultAccounts** are the basis for new user accounts.
- Use the **Control Panel** for a simple way to add users.
- Use **lusrmgr.msc** for advanced user account options and configurations.
## Best Practices
- Regularly audit user accounts for security.
- Always use strong, unique passwords.
- Ensure the Guest account is restricted and secure.
- Backup essential user data before removing any account.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 24th 2023 (07:41 pm) 
Last Modified Date: August 24th 2023 (07:41 pm)
