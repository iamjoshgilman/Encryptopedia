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
- Example:
```PS
PS C:\Users\User> Get-Command -Noun Computer

CommandType Name                    Version Source
----------- ----                    ------- ------
Cmdlet      Add-Computer            3.1.0.0 Microsoft.PowerShell.Management
Cmdlet      Checkpoint-Computer     3.1.0.0 Microsoft.PowerShell.Management
Cmdlet      Remove-Computer         3.1.0.0 Microsoft.PowerShell.Management
Cmdlet      Rename-Computer         3.1.0.0 Microsoft.PowerShell.Management
Cmdlet      Restart-Computer        3.1.0.0 Microsoft.PowerShell.Management
Cmdlet      Restore-Computer        3.1.0.0 Microsoft.PowerShell.Management
Cmdlet      Stop-Computer           3.1.0.0 Microsoft.PowerShell.Management
```

```PS
PS C:\Users\User> Get-Command -Verb Stop
CommandType Name                             Version     Source
----------- ----                             -------     ------
Function    Stop-DscConfiguration            1.1         PSDesiredStateConfiguration
Function    Stop-Dtc                         1.0.0.0     MsDtc
Function    Stop-DtcTransactionsTraceSession 1.0.0.0     MsDtc
Function    Stop-EtwTraceSession             1.0.0.0     EventTracingManagement
Function    Stop-NetEventSession             1.0.0.0     NetEventPacketCapture
...
```
### 2. **Get-ChildItem**
- View contents of a directory or a specific path.
- Alias: `dir` and `ls` (borrowed from Linux).
- Example:
```PS
PS C:\Users\User\Demo> Get-ChildItem

    Directory: C:\Users\User\Demo
Mode        LastWriteTime   Length  Name
----        -------------   ------  ----
d-----   30/01/2018 22:28           dest_dir
d-----   30/01/2018 22:28           source_dir
-a----   30/01/2018 15:07         8 file1.txt
-a----   30/01/2018 15:07         8 file2.txt
-a----   30/01/2018 15:07        16 file3.txt
-a----   30/01/2018 16:14        10 new
```
### 3. **Get-Content**
- Displays the content of a file.
- Alias: `cat` (borrowed from Linux).
- Example:
```PS
PS C:\Users\User\Demo> Get-Content \file1.txt
"one"
```
### 4. **Get-Process**
- Retrieves a list of all running processes on a computer.
- Each process is represented by a unique process ID (PID).
- Example:
```PS
PS C:\Users\User\Demo> Get-Process
Handles NPM(K)  PM(K)   WS(K)   CPU(s)  Id      SI  ProcessName
------- ------  -----   -----   ------  --      --  -----------
299         18  8936    24372    0.13   3540    1 ApplicationFrameHost
256         13  4572    18416    2.47   3280    1 conhost
513         19  1600    4864             452    0 csrss
346         16  1636    4848             556    1 csrss
346         15  2816    12824    0.17   5280    1 ctfmon
...
```
### 5. **Start-Process**
- Start a new process or application.
- The `-FilePath` parameter specifies the program to run.
- Check out all the options by using `Start-Process -?` to display the help file.
### 6. **Stop-Process**
- Ends one or multiple processes.
- Can target processes by name or by their unique ID.
### 7. **Aliases**
- Shortcut names for cmdlets.
- You can create, delete, or modify aliases with `Set-Alias`.
- If you want to check out what other commands have an alias set, or if you want to set your own, you can do so by using the `Get-Alias` and `Set-Alias` cmdlets.
- Running `Get-Alias` will print a list of all currently set aliases, or if you want to see which command is behind the alias you can use the '-Name' argument like this:
```PS
PS C:\Users\User\Demo> Get-Alias -Name cat
CommandType Name                Version Source
----------- ----                ------- ------
Alias       cat->Get-Content
```
- Setting an alias is done by using the following arguments: `Set-Alias -Name <alias_name> -Value <cmdlet_to_run>`
- So if you wanted to add "list" as an alias of `Get-ChildItem` the command would look like: `Set-Alias -Name list -Value Get-ChildItem`

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
# PowerShell Objects

## Overview
- In PowerShell, cmdlets interact with **objects** rather than mere text.
- Objects carry additional information and functionalities than typical command-line interfaces.
## PowerShell Object Properties
- **Properties** contain information about the object.
  - For example, with the `Get-ChildItem` cmdlet, properties can show data like:
    - Time last accessed
    - Parent directories
    - Root directories
- Use `Get-Member` cmdlet to inspect the properties and methods of an object.
  ```powershell
  Get-ChildItem | Get-Member
  ```
## PowerShell Object Methods
- **Methods** are functionalities that allow manipulation of the object and its data.
  - For instance, the `Delete` method will delete the directory an object represents.
## Storing Objects in Variables
- The result of a cmdlet can be stored in a variable.
- Variables are declared using the `$` symbol.
  ```powershell
  $child_items = Get-ChildItem
  ```
- Accessing stored objects:
  ```powershell
  $child_items
  ```
  This will display the content of the variable.
## Accessing Object's Properties and Methods through Variables
- Properties can be accessed with the following syntax:
  ```powershell
  $child_items.PropertyName
  ```
  Example:
  ```powershell
  $child_items.Name
  ```
  This will display a list of file names from the stored result.
  
- Methods can be accessed similarly:
  ```powershell
  $child_items.MethodName()
  ```
  Ensure you add parentheses to invoke the method.
## Key Takeaways
1. **Objects** in PowerShell are powerful as they contain both data (properties) and functionalities (methods).
2. Inspect objects using the `Get-Member` cmdlet.
3. Store command results in **variables** for further manipulation.
4. Access and manipulate stored data using properties and methods of the object via the variable.

___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 1st 2023 (01:02 pm) 
Last Modified Date: June 1st 2023 (01:02 pm)
