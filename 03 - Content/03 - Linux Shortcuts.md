---
creation date: March 2nd 2023
last modified date: March 2nd 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Administration]]] 
Secondary Categories: [[02 - Linux]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Linux Shortcuts]]  

### Cursor Movement

`[CTRL] + A` - Move the cursor to the beginning of the current line.
`[CTRL] + E` - Move the cursor to the end of the current line.
`[CTRL] + [←] / [→]`  - Jump at the beginning of the current/previous word.
`[ALT] + B / F` - Jump backward/forward one word.

### Erase The Current Line

`[CTRL] + U` - Erase everything from the current position of the cursor to the beginning of the line.
`[CTRL] + K` - Erase everything from the current position of the cursor to the end of the line.
`[CTRL] + W` - Erase the word preceding the cursor position.

### Paste Erased Contents

`[Ctrl] + Y` - Pastes the erased text or word.

### Edit /etc/hosts file

`echo "IP Domain_Name" | sudo tee -a /etc/hosts`

### Ends Task

`[CTRL] + C` - Ends the current task/process by sending the SIGINT signal. For example, this can be a scan that is running by a tool. If we are watching the scan, we can stop it / kill this process by using this shortcut. While not configured and developed by the tool we are using. The process will be killed without asking us for confirmation.

### End-of-File (EOF)

`[CTRL] + D` - Close STDIN pipe that is also known as End-of-File (EOF) or End-of-Transmission.

### Clear Terminal

`[CTRL] + L` - Clears the terminal. An alternative to this shortcut is the clear command you can type to clear our terminal.

### Background a Process

`[CTRL] + Z` - Suspend the current process by sending the SIGTSTP signal.

### Search Through Command History

`[CTRL] + R` - Search through command history for commands we typed previously that match our search patterns.
``[↑] / [↓]`` - Go to the previous/next command in the command history.

### Switch Between Applications

``[ALT] + [TAB]`` - Switch between opened applications.

### Zoom

``[CTRL] + [+]`` - Zoom in.
``[CTRL] + [-]`` - Zoom out.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: March 2nd 2023 (07:01 pm) 
Last Modified Date: March 2nd 2023 (07:01 pm)
