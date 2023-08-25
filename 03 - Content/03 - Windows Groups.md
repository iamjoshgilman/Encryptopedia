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

# [[03 - Windows Groups]]  

___
# Overview
- **Groups** help manage user permissions efficiently in Windows.
- Instead of setting permissions for each user, place users in a group and set permissions for the group.
- Users inherit permissions from the groups they belong to.
___
## Built-in Groups in Windows

### **Administrators**:
   - Members have full system access.
   - Can access all files and make universal changes like software installation or system settings adjustments.
   - Default: The Administrator account is a part of this group.
### **Users**:
   - Default group for new standard users.
   - Members can perform most daily tasks: run apps, use printers.
   - They cannot install new software or make systemic changes.
### **Remote Desktop Users**:
   - Necessary for users who need to connect to the computer remotely.
   - A user must be in this group to establish remote desktop sessions to the machine.
   - Note: Being outside of this group only restricts incoming remote desktop connections; you can still use remote desktop to connect to other systems.
### **Guests**:
   - Members don't maintain permanent profiles.
   - A new profile is generated upon each login and deleted after logging off.
   - Default: The Guest account is a member of this group.
___
## Creating New Groups

1. **Access Management Console**:
   - Go to the start menu.
   - Type and select 'lusrmgr.msc'.

2. **Initiate Group Creation**:
   - Right-click on the 'Groups' folder.
   - Select 'New Group'.

3. **Fill Group Details**:
   - Input a name and description.
   - Adding users is optional at this phase but can be done if needed.

1. **Post-Creation**:
   - Once the group is established, users can be added.
   - Manage permissions through the group as necessary.
___
## Key Points to Remember

- **Groups** simplify permission management.
- Built-in groups like **Administrators** and **Users** cater to common needs.
- For remote desktop access, the **Remote Desktop Users** group is essential.
- **Guests** have temporary, transient profiles.
___
## Best Practices

- Regularly review and audit group memberships for security purposes.
- Ensure appropriate permissions are set for each group.
- Limit the number of users in the **Administrators** group to minimize potential security risks.
- For specific tasks or roles, consider creating custom groups to manage permissions effectively.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 24th 2023 (07:42 pm) 
Last Modified Date: August 24th 2023 (07:42 pm)
