---
creation date: May 26th 2023
last modified date: May 26th 2023
aliases: []
tags: #🧰
---

Primary Categories: [[04 - Tools & Techniques]]
Secondary Categories: [[02 - Reconnaissance]] [[01 - Red Team]]
Links: [[]] 
Search Tag: #🧰  

# [[04 - FFUF]]  
___

## **Description:**

FFUF (Fuzz Faster U Fool) is an open-source web fuzzing tool used for discovering elements and content in web applications, such as directories and files. It's written in Go and is highly customizable, allowing for fast and efficient fuzzing.

---

## **Installation (Kali and Arch):**

1. **Kali Linux:**

Since FFUF is written in Go, you need to install Go first. If not already installed, you can do so by running:

```bash
sudo apt-get update
sudo apt-get install golang
```

After Go is installed, install FFUF:

```bash
go get -u github.com/ffuf/ffuf
```

The executable will be in your GOPATH. If you followed the default installation, it should be `$HOME/go/bin/ffuf`.

2. **Arch Linux:**

Similar to Kali, you need to install Go first:

```bash
sudo pacman -Sy
sudo pacman -S go
```

After Go is installed, you can install FFUF:

```bash
go get -u github.com/ffuf/ffuf
```

---

## **Commands and Use:**

To run FFUF, you generally specify the target URL, including the `FUZZ` keyword at the location where you want to fuzz. The `FUZZ` keyword will be replaced by the wordlist inputs.

For example, if you want to fuzz for directories:

```bash
ffuf -w /path/to/wordlist -u https://target.com/FUZZ
```

In the above command, `-w` is used to specify the wordlist location and `-u` is used to specify the URL.

Here are some more options you might use often:

- `-mc`: Match HTTP status codes, e.g., `-mc 200,204`
- `-fc`: Filter HTTP status codes, e.g., `-fc 404`
- `-e`: Specify file extension, e.g., `-e .php,.html,.js`
- `-X`: Specify HTTP method, e.g., `-X POST`
- `-d`: Specify POST data, e.g., `-d "username=FUZZ&password=FUZZ"`
- `-H`: Specify headers, e.g., `-H "Cookie: SESSION=FUZZ"`

### **Use Case 1: Directory Discovery**

You can use FFUF to find hidden directories or files on a web server. Here's an example:

```bash
ffuf -w /path/to/wordlist -u http://targetip/FUZZ
```

In this case, `FUZZ` will be replaced by each entry in your wordlist to discover potential hidden directories.

### **Use Case 2: Subdomain Discovery**

FFUF can be used to find subdomains for a specific domain. In this case, the `FUZZ` keyword would be placed before the domain:

```bash
ffuf -w /path/to/wordlist -u http://FUZZ.target.com
```

### **Use Case 3: File Extension Discovery**

You might want to find out if a certain file with various extensions exists:

```bash
ffuf -w /path/to/wordlist -u http://targetip/index.FUZZ
```

In this case, your wordlist could include file extensions like 'php', 'html', 'txt', etc.

### **Use Case 4: Parameter Fuzzing**

You can also use FFUF to fuzz parameters in a URL:

```bash
ffuf -w /path/to/wordlist -u http://targetip/page?param1=value1&param2=FUZZ
```

This can be useful in finding vulnerabilities associated with specific parameter values.

### **Use Case 5: Post Data Fuzzing**

If a page requires POST data, you can fuzz these values as well:

```bash
ffuf -w /path/to/wordlist -X POST -d "username=admin&password=FUZZ" -u http://targetip/login
```

### **Use Case 6: Header Fuzzing**

Sometimes you might want to fuzz the headers, for example, to test for Host Header Injection vulnerabilities:

```bash
ffuf -w /path/to/wordlist -H "Host: FUZZ" -u http://targetip/
```

### **Use Case 7: IP-based Target**

If you only have an IP address and not a domain, FFUF still works just as well. Any of the previous examples can be used with an IP address. Just replace the domain part with the IP address:

```bash
ffuf -w /path/to/wordlist -u http://192.168.1.1/FUZZ
```


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: May 26th 2023 (09:13 pm) 
Last Modified Date: May 26th 2023 (09:13 pm)
