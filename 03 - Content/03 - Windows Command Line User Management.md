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

# [[03 - Windows Command Line User Management]]

___
# Overview
- Use the `net` command to manage user accounts in Windows.
- Ensure you're using an administrative Command Prompt for these commands.
## 1. Viewing User Accounts: `net user`
- Displays a list of all the user accounts on the machine.
  
**Usage**:
```shell
C:\Windows\system32>net user
```

**Sample Output**:
```
User accounts for \\DESKTOP-3VSCDO9
---------------------------------------
Administrator   DefaultAccount  Guest
User            user2           WDAGUtilityAccount
```

___
## 2. Adding a New User: `net user /add`
- Create a new user and set a password for them.

**Usage**:
```shell
net user /add <username> <password>
```

**Example (with prompted password)**:
```shell
C:\Windows\system32>net user /add user3 *
```

___
## 3. Removing a User: `net user /delete`
- Removes the specified user from the machine.

**Usage**:
```shell
net user /delete <username>
```

**Example**:
```shell
C:\Windows\system32>net user /delete user3
```

___
## 4. Checking User Details: `net user <username>`
- Displays details about a specific user account.

**Usage**:
```shell
C:\Windows\system32>net user user3
```

**Output Includes**:
- User details (name, profile, logon hours, group memberships, etc.)

___
## 5. Changing User Groups: `net localgroup`
- Manage the groups a user belongs to using the `net localgroup` command.

### 5.1 Checking Current Group Membership
```shell
net user <username>
```

### 5.2 Adding User to a Group
**Usage**:
```shell
net localgroup <groupname> /add <username>
```

**Example**:
```shell
C:\Windows\system32>net localgroup Administrators /add user3
```

## Summary
- **`net user`**: Display, add, or remove user accounts.
- **`net user <username>`**: Get details of a specific user account.
- **`net localgroup`**: Manage user group memberships.

---

Managing users and their privileges is essential for system administrators. Ensure you double-check any changes, especially when removing users or modifying group memberships. Use `net user /?` or `net localgroup /?` to get more details on the available command options.




___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 24th 2023 (08:11 pm) 
Last Modified Date: August 24th 2023 (08:11 pm)
