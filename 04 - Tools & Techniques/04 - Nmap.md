---
creation date: February 17th 2023
last modified date: February 17th 2023
aliases: []
tags: #🧰
---

Primary Categories: [[04 - Tools & Techniques]]
Secondary Categories: [[02 - Reconnaissance]] [[01 - Red Team]]
Links: [[nmap]] 
Search Tag: #🧰  

# [[04 - Nmap]]  
___

## Description:
Nmap, short for Network Mapper, open-source tool used for network exploration, management, and security auditing. It is designed to help system administrators and security professionals discover hosts and services on a computer network, as well as create a map of the network topology.

## Information
Stealth (SYN) scans 
		- Sends the initial SYN packets and waits for the SYN/ACK packet from the server
		- Does not respond to the SYN/ACK packet with ACK; thus does not complete the three way handshake
		- Called "stealth" scans because this method used to evade detection from primitive firewalls; however, this is definitely not the case with modern firewalls
			- you will be detected doing this, so the term "stealth" can be misleading
	UDP scans 
		- Are often unreliable as firewalls and routers may drop ICMP packets
		- *** But it is a mistake to neglect them 
			- TCP is only half of the equation 

## Commands

#### Set the IP address as a variable

```shell
export IP=192.168.1.100 
```

```shell
export NETW=192.168.1.0/24
```

#### Initial Scan 

```shell
mkdir nmap
```

```bash
nmap -sC -sV -oA nmap/initial $IP
```

-sC Default Scripts 
-sV Enumerate Versions 
-oA Output All Formats 

#### Long/Background Scan 
```shell
nmap -p- -T5 -oA nmap/allports $IP
```

-p- All Ports: 1-65535 
-T5 Very Aggressive Fast Scan (not recommended) 
-oA Output All Formats 

#### UDP scan 
	Quick UDP 
```shell
nmap -sU -v -oA nmap/quickudp $IP
```
	Longer UDP 
```shell
nmap -v -sC -sV -sU -Pn --disable-arp-ping $IP -oA nmap/longudp
```
 
#### Get the ports in the right format for a targeted nmap scan 

```shell
a=`grep -oP '\d{1,5}/open' kioptrix2.short.gnmap |sort -u |sed -e 's/\/open//g' |tr '\n' ','`; a=${a::-1}
```

-o Print only the matching part (not the entire line) 
-P interpret as Perl-compatible regex  
'\d{1,5}/open' Our regex to grep for (1 to 5 occurrences of any digit followed by /open) 

#### Scanning ipv6 

```shell
nmap -sC -sV -oA scans/mischief-ipv6 -6 dead:beef::250:56ff:feb2:0190 
```

#### Perform a targeted port scan 

```shell
nmap -p $a -sC -sV -oA  /path/file_to_output_to --script vuln $IP
```

#### Webserver enumeration 

```shell
nmap -p 80,443,8000,8080,8443 --script=http-enum $IP
```

#### Nmap Ping Sweep 

```shell
nmap -sn 10.11.0.0/16 -oG ping_sweep.txt
grep Up ping_sweep.txt |cut -f2 -d " " 
```
OR 
```shell
nmap -sn 10.11.1.1-254 -oG ping_sweep.txt
grep Up ping_sweep.txt |cut -f2 -d " "
```
- Keep in mind that systems that have ICMP disabled will not respond to ping sweeps even though they are in fact online
- This method is good/effecient but not definitive

#### Find Low-Hanging Fruit 

```shell
nmap -sT -A --top-ports=20 $IP -oG top_port_sweep.txt 
grep open  top_port_sweep.txt |cut -f2 -d " " 
```
- Machines that prove to be rich in services, or otherwise interesting, would then be individually port scanned, using a more exhaustive port list

#### OS Fingerprinting 

```shell
nmap -O $IP
```

- Will attempt to guess the underlying operating system, by inspecting the packets received from the target

#### kerberos (TCP 88) + LDAP (TCP 389) = Active Directory Domain Controller

#### Identifying NMAP Scripts 

```shell
locate -r '\.nse$' | xargs grep categories |grep 'default\|version' |grep smb 
```
	Identify all nmap default scripts (-sC) 
```shell
grep -r categories /usr/share/nmap/scripts/*.nse |grep default |awk -F: '{print $1}' |awk -F/ '{print $6}'
```

#### Check for Shellshock vulnerability 

```shell
nmap -p 80 --script=http-shellshock --script-args uri=/cgi-bin/test.cgi --script-args uri=/cgi-bin/admin.cgi 10.11.1.71 
```
- For the --script-args uri use the cgi URIs that you found using ka
example
gobuster -w /usr/share/seclists/Discovery/Web-Content/CGIs.txt -u [http://10.11.1.71:80/](http://10.11.1.71/) -s '200,204,301,307,403,500' -e | tee 'alpha/10.11.1.71/scans/10.11.1.71_80_gobuster_cgi

#### View the arguments of an nmap script 

```shell
nmap --script-help <nmap script name> 

```

Exmaple;
	nmap --script-help "irc-unrealircd-backdoor"

#### Enumerate NetBios Users 

```shell
nmap -sC --script=smb-enum-users $IP
```


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |
|https://tinyurl.com/47933acj | GitHub link to Kitsun3Sec/Pentest-Cheat-Sheets |
|https://tinyurl.com/2p83wfr5 | Elevate Pen-Test Notes - NMAP |



Created Date: February 17th 2023 (10:03 am) 
Last Modified Date: February 17th 2023 (10:03 am)
