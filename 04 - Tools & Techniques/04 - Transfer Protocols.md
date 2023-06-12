---
creation date: June 12th 2023
last modified date: June 12th 2023
aliases: []
tags: #📕
---

Primary Categories: [[]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📕  

# [[04 - Transfer Protocols]]  
___
Sure, here is a compiled list of file transfer and hosting methods for both Linux and Windows environments, formatted in tables for better readability.

---

### **File Transfer Methods**

| **Tool/Command** | **Platform** | **Example** | **Description** |
| ---------------- | ------------ | ----------- | --------------- |
| `wget` | Linux/Unix | `wget http://website.com/file.txt` | A free utility for non-interactive download of files from the web. |
| `curl` | Linux/Unix | `curl -O http://website.com/file.txt` | A tool to transfer data from or to a server, using one of the supported protocols. |
| `scp` | Linux/Unix | `scp username@remote:/path/to/file /local/path` | A means of securely transferring computer files between a local and a remote host or between two remote hosts. |
| `rsync` | Linux/Unix | `rsync -avz -e ssh remoteuser@remotehost:/remote/dir /this/dir/` | A utility for efficiently transferring and synchronizing files across computer systems. |
| `netcat (nc)` | Linux/Unix | `nc -lvp 1234 > out.file` (receive) <br/> `nc -v 192.168.1.10 1234 < in.file` (send) | A computer networking utility for reading from and writing to network connections using TCP or UDP. |
| `ssh` | Linux/Unix | `ssh username@server "cat /path/to/remotefile" > /local/path/to/destination` | SSH is a secure protocol and can be used to transfer files. |
| `sftp` | Linux/Unix | `sftp username@host` | A secure file transfer protocol. Use `get` or `put` command to download or upload files respectively. |
| `powershell` | Windows | `(new-object System.Net.WebClient).DownloadFile('http://website.com/file.txt', 'C:\path\to\destination\file.txt')` | You can use PowerShell commands to download files. |
| `certutil` | Windows | `certutil -urlcache -split -f "http://website.com/file.txt" destinationfile.txt` | A command-line utility that can be used to obtain certificate authority information and configure Certificate Services. |
| `bitsadmin` | Windows | `bitsadmin /transfer myDownloadJob /download /priority normal http://website.com/file.txt C:\path\to\destination\file.txt` | BITSAdmin is a command-line tool that you can use to create download or upload jobs and monitor their progress. |
| `ftp` | Windows | `ftp -s:ftpscript.txt` | Windows has a built-in command line FTP client. FTP servers are less common today, but this can be handy if you're in an environment that uses it. |

---

### **File Hosting Methods**

| **Tool/Command**                                                  | **Platform** | **Example**                                                                             | **Description**                                                                       |
| ----------------------------------------------------------------- | ------------ | --------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `python -m SimpleHTTPServer 80` <br/> `python3 -m http.server 80` | Linux/Unix   | `python -m SimpleHTTPServer 80` (Python 2) <br/> `python3 -m http.server 80` (Python 3) | Starts a simple HTTP server hosting the contents of the current directory on port 80. |
| `php -S 0.0.0.0:80`                                               | Linux/Unix   | `php -S 0.0.0.0:80`                                                                     | If PHP is installed, start a simple PHP server to host files                          |
| `ruby -run -ehttpd . -p80` | Linux/Unix | `ruby -run -ehttpd . -p80` | If Ruby is installed, you can start an HTTP server hosting the current directory on port 80. |
| `busybox httpd -f -p 80` | Linux/Unix | `busybox httpd -f -p 80` | If you're on a system with Busybox installed (common in embedded Linux), you can use its HTTP daemon to host files. |
| `python -m http.server 80` | Windows | `python -m http.server 80` | Similar to Linux, you can use Python to start a simple HTTP server in Windows. Requires Python 3. |
| PowerShell Job | Windows | `$p = Start-Job -ScriptBlock {python -m http.server 80}` | You can use PowerShell to host a simple HTTP server. This starts the server in a separate PowerShell job. |
| Python FTP Server | Cross-platform | `from pyftpdlib import servers` <br/> `from pyftpdlib.handlers import FTPHandler` <br/> `handler = FTPHandler` <br/> `handler.authorizer.add_anonymous("/path/to/ftp-root")` <br/> `server = servers.FTPServer(("0.0.0.0", 21), handler)` <br/> `server.serve_forever()` | You can create an FTP server to host files for transfer using Python's `pyftpdlib`. This is a powerful and highly configurable FTP server library. |
| Netcat File Transfer | Linux/Unix | `nc -l -p 1234 > outputfile` (on the receiving machine) <br/> `nc 192.168.1.10 1234 < inputfile` (on the sending machine) | Netcat is a versatile networking tool that can read and write data across network connections. You can use it to send a file from a host machine to a client machine. |

___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 12th 2023 (07:21 am) 
Last Modified Date: June 12th 2023 (07:21 am)
