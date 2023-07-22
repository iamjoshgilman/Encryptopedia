---
creation date: June 16th 2023
last modified date: June 16th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Security Fundamentals]] 
Secondary Categories: [[02 - Networking]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Network Tools]]  
---

# Command Line Tools

### IP and ipconfig
- `IP` or `ipconfig` on Windows, is a command-line tool that shows the current network configuration of the device that you are on. This includes information such:
	- Current private IP address of the device
	- The gateway address
	- The DNS server
		- Some common examples of _IP_ commands include:
			- `ip a` - Shows the IP addresses on the device
			- `ip r list` - Displays the current routing table on the device
			- `ip link set dev [Device Name] [up|down]` - This sets the network interface to either up (enabled) or down (disabled)

### Traceroute and Tracert
- `Traceroute`, or `tracert` on Windows, is a command-line tool that allows you to see the path that network packets take when going from one host to another.
- This tool is often used to troubleshoot routing issues between two systems.
	- Some common examples of _traceroute_ commands include:
		- `traceroute [url]` - Runs the basic traceroute to see the path it takes to get to a specified address
		- `traceroute [url] -p [port number]` - Allows the trace to be run with a specific port

### Dig and Nslookup
- `Dig*`, or `Nslookup` on Windows (and Linux), is a command-line tool that is used to query DNS servers for information about a specific domain. This tool can often be helpful when you need to quickly search for the IP address of a malicious URL or if you need to find out what mail server a domain routes its emails through.
	- Some common examples of _dig_ commands include:
		- `dig [domain name]` - Queries the DNS server for the A record for the specified domain
		- `dig [domain name] MX` - Queries the DNS server for mail (MX) records for the specified domain
		- `dig [domain name] ANY +nocomments +noauthority +noadditional +nostats` - Queries the DNS server for all DNS records for the specified domain and removes the extra information provided by dig

### Netstat
- Netstat is a Linux and Windows-based command-line tool that monitors the TCP and UDP connections on your host system. This tool can often be used for application troubleshooting or if a computer is suspected of containing malware, to see if a system has open connections to remote servers, which could be a sign of it being controlled by a C2 Server
	- Some common examples of netstat commands include:
		- `netstat -a` - Displays all of the current connections and listening ports on the system
		- `netstat -a -b` - Displays all of the current connections and listening ports on the system, as well as their corresponding executable
		- `netstat -s -p tcp -f` - Displays the statistics for all connections using TCP and then displays them in an FQDN format

### Nmap
- Nmap, or Network Mapper, is most often the tool of choice for performing Network Discovery. It is capable of revealing ports, discovering devices on a network, revealing running services, identifying operating systems, and many other functions. All of these capabilities make Nmap an effective, easy-to-use, and versatile tool. Nmap is an open-source tool that comes pre-installed on the Kali operating system, among various other Linux distributions. However, there are also Windows, Mac OS, and other operating system versions on their [website](https://nmap.org/download.html).









___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 16th 2023 (09:10 am) 
Last Modified Date: June 16th 2023 (09:10 am)
