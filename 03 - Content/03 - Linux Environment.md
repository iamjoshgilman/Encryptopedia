---
creation date: August 17th 2023
last modified date: August 17th 2023
aliases: []
tags: #📖
---

Primary Categories: [[02 - Foundations]] | [[000 - Cybersecurity Materials]]
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Linux Environment]]  

[[#Linux Superuser Overview]]
[[#Linux File Permissions]]
# Linux Superuser Overview

### **Understanding the Superuser in Linux**

- **Superuser Account**: Administrative account on Linux, primarily referred to as **'root'***
  - *Capabilities**: Total control and permissions over the OS. 
  - **Contrast**: Unlike Windows, where some tasks are restricted to even administrative accounts, 'root' can do anything, including damaging the OS.
  - **Caution**: Linux doesn't provide many warnings. An erroneous command can wreak havoc if executed as root.

- **Best Practice**: Don't use the root account for daily tasks. Begin as a standard user, switch to root when necessary, and revert back.

**Procedure**:
```bash
user@sans:~/Desktop$ whoami    # To check the current user
user@sans:~/Desktop$ su root   # To switch to the root user
root@sans:~/home/user/Desktop# exit  # To exit root user mode
```
### **The 'sudo' Mechanism**

- **sudo**: A program allowing a user to execute commands with temporary superuser rights.
  
  - **How it Works**: A configuration called the 'sudoers' file dictates which users or groups can execute which commands with superuser rights.
  - **Using sudo**: Append 'sudo' before a command. Enter the user password (not root) to execute the command with elevated privileges.
  - **Password Caching**: After entering the password once, it gets cached for a short duration, hence no prompt in quick successive uses.

  - **Example**:
    ```bash
    user@sans:~/Desktop$ whoami       # Current user is 'user'
    user@sans:~/Desktop$ sudo whoami  # Using sudo to get the identity as 'root'
    ```

- **sudoers File**: Configuration dictating privileges for sudo.
  
  - **Key Sections**: Contains user privilege specifications, detailing rights for users or groups.
  - **Precaution**: Only use 'visudo' to edit the sudoers file. It checks for errors prior to saving, reducing the risk of misconfigurations.
  - **Example**:
    ```bash
    %sudo ALL=(ALL:ALL) ALL
    ```
    This line implies members of the 'sudo' group can execute any command as root
### **Linux User Groups**

- Users can belong to groups, inheriting permissions associated with those groups.
  - **Example**:
    ```bash
    user@sans:~/Desktop$ groups   # Lists the groups a user belongs to
    ```

---
# **Root Directories in Linux**:

| Directory    | Description                                                                                               |
|--------------|-----------------------------------------------------------------------------------------------------------|
| `/bin`       | Houses executable files, typically system-level binaries.                                                  |
| `/boot`      | Contains files necessary for booting the system. Caution is advised when making changes in this directory. |
| `/cdrom`     | Maps to the CD-ROM tray. Provides access to files on any inserted CD-ROM.                                 |
| `/dev`       | Represents hardware components as files (e.g., CPU, hard drives). Generally, manual modifications are discouraged.|
| `/etc`       | Central location for system-wide configuration files and shell scripts.                                   |
| `/home`      | Stores user directories (excluding the root user).                                                        |
| `/lib`       | Contains shared libraries and kernel modules critical for system operations.                               |
| `/lost+found`| A recovery directory for orphaned and corrupted files.                                                    |
| `/media`     | Common mount point for removable devices like USB drives and external hard drives.                        |
| `/mnt`       | An alternative mount point for external devices.                                                          |
| `/opt`       | Reserved for optional software and applications.                                                          |
| `/proc`      | Dynamic directory that provides information about system processes.                                        |
| `/root`      | Home directory for the root user.                                                                        |
| `/run`       | Holds temporary runtime data for early-boot programs.                                                    |
| `/sbin`      | Like `/bin`, but for administrative binaries and system tasks.                                            |
| `/srv`       | Contains data served by the system, e.g., for web or FTP servers.                                         |
| `/sys`       | Houses information about system devices as seen by the kernel.                                            |
| `/tmp`       | Temporary directory with ephemeral content.                                                               |
| `/usr`       | Repository for user-related programs, libraries, and other files.                                         |
| `/var`       | Contains variable data like logs, databases, and mail queues.                                             |

___
# Linux File Permissions

File permissions in Linux are straightforward once you grasp the core concepts. Each file/folder has a user owner and a group owner:
- **User**: Refers to the user that owns the file.
- **Group**: Refers to the group that the file belongs to.
### Types of Permissions:
- `r`: Read Permissions.
- `w`: Write Permissions.
- `x`: Execute Permissions.

The order in which these permissions are displayed is crucial:
1. **User**
2. **Group**
3. **Others**

For example, `-rwxr-x-w-` means:
- The **user** can Read, Write, and Execute (`rwx`).
- The **group** can Read and Execute, but not Write (`r-x`).
- **Others** can Write but not Read or Execute (`-w-`).
### Setting File Permissions:

- Use the `chown` command to change file ownership.
  ```bash
  sudo chown root permission_example
  ```
- Use the `chgrp` command to change the group ownership.
  ```bash
  sudo chgrp sudo permission_example
  ```
- Use the `chmod` command to set permissions.
  ```bash
  chmod 755 permissions_example
  ```
### Using Numerical Values for Permissions:

Permissions can be represented in binary, with `r` as 4, `w` as 2, and `x` as 1. So, `rwx` is represented as 7 (4 + 2 + 1).

For example, the permission `r-x` is represented as 5 (4 + 0 + 1).
### Shortcut:
- **Read** = 4
- **Write** = 2
- **Execute** = 1

Add up the numbers based on the desired permissions to derive the right chmod value. For instance:
- `r-x` = 4 + 1 = 5
- `rw-` = 4 + 2 = 6
Remembering this simple mapping can help in setting the desired permissions more swiftly and accurately.
___





___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 17th 2023 (10:30 am) 
Last Modified Date: August 17th 2023 (10:30 am)
