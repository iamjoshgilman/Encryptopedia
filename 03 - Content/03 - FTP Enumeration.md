Primary Categories: [[03 - Network Service Discovery]] 
Secondary Categories: [[02 - Reconnaissance]] 
Search Tag: #🗺  

***
## FTP Enumeration (File Transfer Protocol)
---

FTP (File Transfer Protocol) is a standard network protocol used for transferring files from one host to another over a TCP-based network, such as the internet. FTP is built on a client-server architecture and uses separate control and data connections between the client and the server.

### Anonymous FTP / Login:

You can log into an FTP server with the `ftp` command, followed by the IP address or hostname of the server. For example:

```bash
ftp 192.168.1.1
```

Then, the system will prompt for the username and password.

```bash
Name (192.168.1.1:root): <username/"anonymous">
Please specify the password.
Password: <password>
```

When logging in as "anonymous" a password is not required

### FTP Bounce Attack:

FTP Bounce Attack is not easy to perform with modern tools because most updated FTP servers prevent it. For the sake of completion, this is a representation of how it would be performed with the tool `ncftp`:

```bash
ncftp
open 192.168.1.1
quote "PORT 127,0,0,1,0,80"
get file.txt
```

This example tries to open a connection to a localhost (`127.0.0.1`) on port 80, but as mentioned before, it's likely to fail on updated servers.

### Brute force attack:

Using `hydra` to brute force FTP logins. Suppose we have a file `usernames.txt` for usernames and `passwords.txt` for passwords:

```bash
hydra -L usernames.txt -P passwords.txt ftp://192.168.1.1
```

### Banner grabbing:

To grab a banner using `nc` (netcat), you can simply connect to the FTP port and it will display the banner:

```bash
nc 192.168.1.1 21
```

### Check for file and directory permissions:

After you log into the FTP server, you can use `ls -la` to check the file and directory permissions:

```bash
ftp 192.168.1.1
# Enter username and password
ls -la
```

## FTP Commands

| Command | Description |
|---------|-------------|
| ls -lsa | List the files in the current directory on the FTP server, including file size, modification time, and permissions. |
| cd      | Change the directory on the FTP server. |
| get     | Download a file from the FTP server. |
| put     | Upload a file to the FTP server. |
| delete  | Remove a file on the FTP server. |
| pwd     | Print the current directory on the FTP server. |
| bye     | Close the FTP connection. |
| mget    | Download multiple files from the server. |
| mput    | Upload multiple files to the server. |
| binary  | Set the file transfer type to binary, useful when transferring non-text files. |
| ascii   | Set the file transfer type to ASCII, useful when transferring text files. |
| passive | Enable passive mode. This can help when a firewall is blocking the FTP data connection. |
| !       | Escape to the shell from an ftp connection. |
| open    | Open a new FTP connection to a remote server. |
| close   | Close the current FTP connection but leaves the client program open. |
| user    | Specify the username to use on the FTP server. |
| lcd     | Change the directory on the local machine. |
| lpwd    | Print the current directory on the local machine. |
| lls     | List the contents of the local directory. |

### Mitigation Strategies against FTP Enumeration
- Disable anonymous logins
- Use strong, complex passwords
- Regularly update and patch FTP servers
- Implement a firewall to block unnecessary ports
- Limit the number of failed login attempts
- Use secure versions of FTP like SFTP or FTPS