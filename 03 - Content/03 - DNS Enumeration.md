---
creation date: February 17th 2023
last modified date: February 17th 2023
aliases: []
tags: #📖
---

Primary Categories: [[03 - Network Service Discovery]]
Secondary Categories: [[02 - Reconnaissance]] 
Links: [[DNS]] -  
Search Tag: #📖  

# [[03 - DNS Enumeration]]  

#### Nslookup

Resolve a given hostname to the corresponding IP

```shell
nslookup targetorganization.com
```

#### Reverse DNS lookup

```shell
nslookup -type=PTR IP_address
```

#### MX(Mail Exchange) lookup

```shell
nslookup -type=MX domain
```

#### Zone Transfer

Using nslookup Command

```shell
nslookup
server domain.com
ls -d domain.com
```

#### Using HOST Command

Host -t ns(Name Server) < domain >

```shell
host -t ns domain.com
```

After that test nameservers

host -l < domain > < nameserver >

```shell
host -l domain.com ns2.domain.com
```

#### Nmap Dns Enumaration

```shell
nmap -F --dns-server <dns server ip> <target ip range>
```

##### Auto tools
__DNSenums__
```shell
dnsenum targetdomain.com
```

```shell
dnsenum --target_domain_subs.txt -v -f dns.txt -u a -r targetdomain.com
```

#### DNSmap

```shell
targetdomain.com
```

```shell
dnsmap targetdomain.com -w <Wordlst file.txt>
```

Brute Force, the file is saved in /tmp

```shell
dnsmap targetdomain.com -r
```

#### DNSRecon DNS Brute Force

```shell
dnsrecon -d TARGET -D /usr/share/wordlists/dnsmap.txt -t std --xml ouput.xml
```

#### Fierce.pl

```shell
fierce -dns targetdomain.com
```

#### HostMap

```shell
hostmap.rb -only-passive -t <IP>
```

We can use -with-zonetransfer or -bruteforce-level



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: February 17th 2023 (01:59 pm) 
Last Modified Date: February 17th 2023 (01:59 pm)
