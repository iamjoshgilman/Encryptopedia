---
creation date: May 27th 2023
last modified date: May 27th 2023
aliases: []
tags: #🧰
---

Primary Categories: [[04 - Tools & Techniques]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #🧰  

# [[04 - GoBuster]] 
---

GoBuster is a directory/file and DNS enumeration tool written in Go, used in penetration testing and CTF (Capture the Flag) scenarios to find hidden directories or files in a web server. It does this by brute-forcing GET and HEAD requests to the server. 

---
## Installation

```
$ sudo apt-get install gobuster
```
Or directly from the source:
```
$ go get github.com/OJ/gobuster
```

---
## Basic Usage

GoBuster has multiple modes: dir, dns and vhost. 

### Dir Mode
The most common use is 'dir' mode, which is used to brute-force directories and files in websites.

```
$ gobuster dir -u http://target -w /path/to/wordlist
```
In this command:
- `dir`: Indicates the mode to be used.
- `-u`: Indicates the URL for the target.
- `-w`: Indicates the wordlist to be used for brute forcing.

### DNS Mode
DNS mode is used for DNS subdomain brute-forcing.

```
$ gobuster dns -d target.com -w /path/to/wordlist
```
In this command:
- `dns`: Indicates the mode to be used.
- `-d`: Specifies the domain for DNS brute-forcing.

### Vhost Mode
Vhost mode is used to enumerate virtual hosts on the target web server.

```
$ gobuster vhost -u http://target -w /path/to/wordlist
```

---
## Common Options

- `-t`: Number of threads (default 10).
- `-x`: File extension(s) to search for.
- `-s`: Status code(s) to consider as valid (default 200,204,301,302,307,401,403).
- `-k`: Skip SSL certificate verification.
- `-n`: Don't print banner and other non-essential output.
- `-q`: Don't print the progress.
- `-o`: Write output to file.
- `-r`: Follow redirects.

---
## Examples 

```
$ gobuster dir -u http://target -w /path/to/wordlist -x php,txt -t 50
```
This will brute force directories and files with extensions `.php` and `.txt` on `http://target` using 50 threads.

```
$ gobuster dns -d target.com -w /path/to/wordlist -t 100
```
This will brute force DNS subdomains of `target.com` using 100 threads.

---
## Warning 

Ensure to use GoBuster responsibly. It's a powerful tool that can cause a Denial-of-Service (DoS) if misused. Always get proper permissions before conducting any penetration testing activities.

---

These are the basic notes for GoBuster. Depending on how advanced you want to get, you may need to dive deeper into the documentation and usage examples.




___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: May 27th 2023 (01:50 pm) 
Last Modified Date: May 27th 2023 (01:50 pm)
