---
creation date: June 1st 2023
last modified date: June 1st 2023
aliases: []
tags: #📖
---

Primary Categories: [[000 - Global Index]] | [[01 - Administration]] 
Secondary Categories: [[02 - Windows]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Windows Powershell]]  

# PowerShell Cmdlets

PowerShell introduces the concept of "cmdlets" (pronounced "command-lets"). These are lightweight commands built into the PowerShell environment. Each cmdlet is designed to perform a single function, and they follow the verb-noun naming convention, making them easy to understand.

For example:
- `Get-ChildItem` - retrieves the items (files and directories) in a directory.
- `Set-Location` - changes the current directory.
- `New-Item` - creates a new item (like a file or directory).

Cmdlets return data as .NET objects, allowing for rich data manipulation and formatting.

___
## PowerShell ISE

The PowerShell Integrated Scripting Environment (ISE) is a graphical interface that assists with creating, testing, and running PowerShell scripts. Key features include:

1. **Script Pane**: A dedicated area to write and edit scripts.
2. **Command Pane**: Execute individual commands or run the script you've written.
3. **Output Pane**: View results/output of executed commands or scripts.
4. **Command Search/Add-on Tools**: Easily search for cmdlets or use built-in tools to enhance your scripting experience.

To open PowerShell ISE:
1. Go to the Start menu.
2. Type "powershell".
3. Select the "Windows PowerShell ISE" application.

PowerShell ISE is invaluable when writing long scripts, as it provides debugging capabilities, syntax highlighting, and tab completion.

___
# Key Commands

### 1. **Get-Command**
- Discover commands available to you.
- Filter results using `-Noun` and `-Verb` parameters.
### 2. **Get-ChildItem**
- View contents of a directory or a specific path.
- Alias: `dir` and `ls` (borrowed from Linux).
### 3. **Get-Content**
- Displays the content of a file.
- Alias: `cat` (borrowed from Linux).
### 4. **Get-Process**
- Retrieves a list of all running processes on a computer.
- Each process is represented by a unique process ID (PID).
### 5. **Start-Process**
- Start a new process or application.
- The `-FilePath` parameter specifies the program to run.
### 6. **Stop-Process**
- Ends one or multiple processes.
- Can target processes by name or by their unique ID.
### 7. **Aliases**
- Shortcut names for cmdlets.
- You can create, delete, or modify aliases with `Set-Alias`.

| Alias | Cmdlet         | Description                          |
|-------|----------------|--------------------------------------|
| cat   | Get-Content    | Display file contents                |
| cd    | Set-Location   | Change directory                     |
| dir   | Get-ChildItem  | List directory contents              |
| ls    | Get-ChildItem  | List directory contents (alternative)|
| rm    | Remove-Item    | Delete files or folders              |
## Additional Insights:

### Parameter Help

PowerShell cmdlets often have many parameters. To see all parameters and get detailed help for a cmdlet, use:

```powershell
Get-Help <cmdlet-name> -Detailed
```
### Pipelines

A hallmark feature of PowerShell is the pipeline, represented by `|`. It allows you to take the output of one cmdlet and send it as input to another cmdlet. For example, to stop all processes named "Notepad", you could do:

```powershell
Get-Process -Name notepad | Stop-Process
```
### Profile

If you find yourself setting certain aliases or configurations every time you open PowerShell, consider setting up a profile. This is a script that runs every time you open a PowerShell session. You can check if you already have a profile with:

```powershell
Test-Path $profile
```

If it returns `False`, you can create one with:

```powershell
New-Item -Type file -Path $profile -Force
```

Then, edit your profile with:

```powershell
notepad.exe $profile
```

Here, you can add cmdlets or scripts that you want to run at the start of each session.





___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 1st 2023 (01:02 pm) 
Last Modified Date: June 1st 2023 (01:02 pm)
