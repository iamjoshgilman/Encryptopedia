Primary Categories: [[01 - Blue Team]] | [[000 - Cybersecurity Materials]] 
Secondary Categories: [[]] 
Search Tag: #🗺  

# [[01 - Threat Hunting]]  
***

```bash
192.168.140.139
```

![[Pasted image 20230812111539.png]]

# Networking
#### <u>You can hide processes but not packets</u>

- The network is the great equalizer
	- You see everything, regardless of platform
	- Desktop, servers, IIoT, etc all reviewed the same
- Malware is usually controlled
	- Which makes targeting C2 extremely effective
	- Identify compromise when C2 "calls home"
	- Must be frequent enough to be useful

# Threat hunting process order
- Identify connection persistency
- Business need for connection?
	- Reputation check of external IP
- Abnormal protocol behavior
- Investigation of internal IP
- Disposition
	- No threat detected = add to safelist
	- Compromised = Trigger incident handling

### Don't cross "the passive/active line"
- All threat hunting activity should be undetectable to an adversary
- Passive in nature
	- Review packets
	-  Review SIEM logs
- If active techniques are required, we must trigger incident response first
	- Example: Isolating the suspect host
	- Example: Running commands on suspect host

# C2 Detection Techniques

### Where to Start
- Traffic to and from the Internet
	- Monitor internal interface of firewall
- Packet captures or Zeek data
- Analyze in large time blocks
	- More data = better fidelity
	- Minimum of 12 hours, 24 is ideal
- Analyze communications in pairs
	- Every outbound session passing the firewall
	- Ignore internal to internal (high false positive)
### AC-Hunter typical deployment

https://www.activecountermeasures.com/ac-hunter-installation/
![[Pasted image 20230812114400.png]]
### Does targeting C2 have blind spots?
- Attackers motivated by gain
	- Information
	- Control of resources
- Sometimes "gain" does not require C2
	- Just looking to destroy the target
	- Equivalent to dropping a cyber bomb
	- We are talking nation state at this level
- NotPetya
	- Worm with no C2 designed to seek and destroy

# Start by checking persistency
- Focus on persistent connections
	- Internal system in constantly initiating connections with an outside "system"
	- Long connections
	- Beacons
### Long connections
- Total time for each connection
	- Which ones have gone on the longest?
- Cumulative time for all pair connections
	- Total amount of time the pair has been in contact
- Can be useful to ignore ports or protocols
	- C2 can change channels

### What is a beacon?
- Repetitive connection establishment between two IP addresses
	- Easiest to detect
- Repetitive connection establishment between internal IP and FQDN
	- Target can be spread across multiple IP's
		- Usually a CDN (Content Delivery Network) provider
- Target IPs also destination for legitimate traffic
- Far more difficult to detect

![[Pasted image 20230812115302.png]]

![[Pasted image 20230812115356.png]]

### Beacon detection based on timing
- May follow an exact time interval
	- Technique is less common today
	- Detectable by k-means (Large patterns, algorithm done through machine learning)
	- Potential false positives
- May introduce "jitter"
	- Vary connection sleep delta
	- Avoids k-means detection
	- False positives are extremely rare
- Short enough delta for terminal activities

[RITA Free Tool](https://www.activecountermeasures.com/free-tools/rita/) - Detection tool for C2

# Safe listing
- Not all persistence is "evil"
- Could be part of normal operations
	- Keep computer time in sync
	- Checking for patches
	- Checking on an external service
- When business need can be identified, we should safelist the connection
	- Keep it out of future hunts
	- Don't make safelists any broader than necessary

### Identifying business need
- Do you recognize the domain?
	- microsoft.com
	- windows.com
	- ntp.org
- Can you relate the services to a specific department?
- The purchasing group can be helpful
	- Find the company behind the domain
	- Are we purchasing services from them?

### Check destination IP address
- Start simple
	- Who manages ASN?
	- Geolocation info?
	- IP delegation
	- PTR records
- Do you recognize the target organization?
	- Business partner or field office
	- Current vendor (active status)
## Some helpful links check IPs

```txt
https://www.abuseipdb.com/check/<IP Address>
https://otx.alienvault.com/indicator/ip/<IP Address>
https://search.censys.io/hosts/<IP Address>
https://dns.google/query?name=<IP Address>
https://www.google.com/search?q=<IP Address>
https://www.onyphe.io/search/?query=<IP Address>
https://securitytrails.com/list/ip/<IP Address>
https://www.shodan.io/host/<IP Address>
https://www.virustotal.com/gui/ip-address/<IP Address>/relations
```

___
# What next?
- You've identified connection persistence
- You can't identify a business need
- Next steps
	- Protocol analysis
	- Reputation check of external target
	- Investigate internal IP address
### Unexpected app or port usage
- There should be a business need for all outbound protocols
- Research non-standard or unknown ports
	- TCP/5222 (Chrome remote desktop)
	- TCP/5800 & 590X (VNC)
	- TCP/502 (Modbus)
### Unknown app on standard port
- C2 wants to tunnel out of environment
	- Pick a port likely to be permitted outbound
	- Does not always worry about protocol compliance
- Check standard ports for unexpected apps
	- Indication of tunneling
- Different than app on non-standard port
	- This is sometimes done as "a feature"
	- Example: SSH listening on TCP/2222

### Unexpected protocol use
- Attackers may bend but not break rules
- This can result in:
	- Full protocol compliance
	- Abnormal behaviour
- Need to understand "normal"
	- For the protocol
	- For your environment

![[Pasted image 20230812124934.png]]
### Example: Too many FQDNs
- How many FQDNs do domains expose?
	- Most is < 10
	- Recognizable Internet based vendors 200 - 600
		- Microsoft
		- Akamai
		- Google
		- Amazon
- Greater than 1,000 is suspicious
- Could be an indication of C2 traffic

### Bonus checks on DNS
- Check domains with a lot of FQDNs
- Get a list of the IPs returned
- Compare against traffic patterns
	- Are internal hosts visiting this domain?
	- Is it just your name servers?
- Unique trait of C2 over DNS
	- Lots or FQDN queries
	- But no one ever connects to these systems


## Look for odd HTTP user agents

![[Pasted image 20230812125907.png]]
10.0.2.15 identifies itself as:
- Windows 10 when speaking to 27 different IP's on the Internet
- Windows XP when speaking to one specific IP on the Internet

### Internal system
- Info available varies greatly between orgs
- Inventory management systems
- Security tools like Carbon Black
- OS projects like [BeaKer](https://www.activecountermeasures.com/free-tools/beaker/)
- Internal security scans
- DHCP logs
- Login events
- Passive fingerprinting

### Leverage internal host logging

- Maintain passive - connecting to computer can give us away with an active thread
- Network shows suspicious traffic patterns
- Use this data to pivot to host logs
- Filter your logs based on:
	- Suspect internal host
	- Timeframe being analyzed
- Anything stand out as unique or odd?

- Map outbound connections to the applications that created them.
![[Pasted image 20230812132920.png]]
### But I have no system logs!
- Good time to start collecting them
- Full packet captures from system
- Apply additional network tools to collect more data
- **Just remember, no detectable actions until we trigger incident response mode!**
#### What next?
- Disposition session
	- "I think it's safe" = add to safelist
	- "I think we've detected a compromise" = Incident response mode
- Remember to leave no footprints
	- All actions undetectable to potential adversaries
	- Passive activities only
- Incident response may include active tasks
___
# Network Threat Hunting Tools

## tcpdump
- What's it good for?
	- Lightweight packet capturing tool
	- Cross platform support (windump on Windows)
- When to use it
	- Audit trail of all traffic
	- Can also filter to see only specific traffic
	- Can be fully automated
- Where to get it
	- https://www.tcpdump.org/
### tcpdump example
- Debian/Ubuntu
	- Place the following in /etc/rc.local
- Red Hat/CentOS, Fedora
	- Place the following in /etc/rc.d/rc.local
- Grabs all traffic and rotates every 60 min
	- Date/time stamped and compressed

```bash
#Place _above_ any "exit" line
mkdir -p /opt/pcaps
screen -S capture -t capture -d -m bash -c "tcpdump -i eth0 -G
3600 -w '/opt/pcaps/`hostname -s`.%Y%m%d%H%M%S.pcap' -z bzip2"
```
## tshark
- What's it good for?
	- Extracting interesting fields from packet captures
	- Multiple passes to focus on different attributes
	- Combine with text manipulation tools
	- Can be automated
- When to use it
	- Both major and minor attributes
- Where to get it
	- https://www.wireshark.org/
### Tshark example - DNS queries

```bash
$ tshark -r thunt-lab.pcapng -T fields -e dns.qry.name udp.port==53 | head -10
6dde0175375169c68f.dnsc.r-1x.com
6dde0175375169c68f.dnsc.r-1x.com
0b320175375169c68f.dnsc.r-1x.com
0b320175375169c68f.dnsc.r-1x.com
344b0175375169c68f.dnsc.r-1x.com
344b0175375169c68f.dnsc.r-1x.com
0f370175375169c68f.dnsc.r-1x.com
0f370175375169c68f.dnsc.r-1x.com
251e0175375169c68f.dnsc.r-1x.com
251e0175375169c68f.dnsc.r-1x.com
```
### Tshark example - user agents
```bash
$ tshark -r sample.pcap -T fields -e http.user_agent tcp.dstport==80 | sort | uniq -c | sort -n | head -10

2 Microsoft Office/16.0
2 Valve/Steam HTTP Client 1.0 (client;windows;10;1551832902)
3 Valve/Steam HTTP Client 1.0
11 Microsoft BITS/7.5
11 Windows-Update-Agent
12 Microsoft-CryptoAPI/6.1
104 PCU
```
## capinfos (Comes with Tshark)
- Print summary info regarding pcaps
- For a decent hunt you want 12+ hours
- 86,400 seconds = 24 hours

![[Pasted image 20230812133941.png]]
## Wireshark
- What's it good for?
	- Packet analysis with guardrails
	- Stream level summaries
	- Useful when you have a target
- When to use it
	- As part of a manual analysis
	- When steps cannot be automated
- Where to get it
	- https://www.wireshark.org/

![[Pasted image 20230812134131.png]]
## Zeek
- Network recorder
- What's it good for?
	- Near real time analysis (1+ hour latency)
	- More storage friendly than pcaps
- When to use it
	- When you need to scale
	- When you know what attributes to review
- Where to get it
	- https://www.zeek.org/
	- `sudo apt -y install zeek`
### Zeek example - cert check
```bash
$ cat ssl* | zeek-cut id.orig_h id.resp_h id.resp_p
validation_status | grep 'self signed' | sort | uniq
122.228.10.51 192.168.88.2 9943 self signed certificate in
certificate chain
24.111.1.134 192.168.88.2 9943 self signed certificate in
certificate chain
71.6.167.142 192.168.88.2 9943 self signed certificate in
certificate chain
```
### -d for human readable times
- Zeek-cut prints epoch time by default
- "-d" converts to human readable
![[Pasted image 20230812134413.png]]
## zcutter.py
- zeek-cut limited to CSV format
- What if you use JSON?
- zcutter.py to the rescue!
- Like zeek-cut, but supports CSV & JSON
- Will also process multiple log files simultaneously
- Where to get it?
	- [Github - zcutter](https://raw.githubusercontent.com/activecm/zcutter/main/zcutter.py)
### Passer
```bash
TC,172.1.199.23,TCP_43,open,
TC,172.16.199.23,TCP_55443,open,
UC,172.16.199.23,UDP_626,open,serialnumberd/clientscanner likely nmap
scan Warnings:scan
UC,172.16.199.23,UDP_1194,open,openvpn/client Warnings:tunnel
UC,172.16.199.23,UDP_3386,open,udp3386/client
UC,172.16.199.23,UDP_5632,open,pcanywherestat/clientscanner
Warnings:scan
UC,172.16.199.23,UDP_64738,open,shodan_host/clientscanner abcdefgh
Unlisted host Warnings:scan
DN,2001:db8:1001:0000:0000:0000:0000:0015,AAAA,ns3.markmonitor.com.,
DN,fe80:0000:0000:0000:189f:545b:7d4c:eeb8,PTR,Apple
TV._device-info._tcp.local.,model=J105aA
```
### Smudge

![[Pasted image 20230812134700.png]]
- Can run it alone or integrated with Passer

## ngrep
- Pattern match on passing packets
- Like "grep" for network traffic
- Useful for quick checks
	- NIDS with signature better choice for long term
- Useful switches
	- "-q" = Don't print "#" for non-matches
	- "-I" = Read a pcap file
- Where to get it?
	- https://github.com/jpr5/ngrep
	- `sudo apt install ngrep`
![[Pasted image 20230812134926.png]]

## RITA
- What's it good for?
	- Beacon & long conn at scale
	- Some secondary attributes
- When to use it
	- Can better organize Zeek data
	- Good when you are comfortable scripting
	- Will scale but can be time consuming
- Where to get it
	- https://github.com/activecm/rita

### RITA example - beacons

![[Pasted image 20230812135056.png]]
- Scale is 0 - 1 with 1.0 being a perfect beacon score
### RITA can also check
- Beacons based on HTTP/host or TLS/SNI
- Beacons based on FQDN
- Beacons through SOCKS server
- Long connections
- Still open (not yet logged) connections
- C2 over DNS
- Matches against your threat intel list
## Datamash
- What's it good for?
	- Similar to the R-base tools, but more extensive
	- Performing simple calculation on data
- When to use it
	- Performing calculations on multiple lines
	- Statistical analysis
- Where to get it
	- https://www.gnu.org/software/datamash/
	- `sudo apt install datamash`
- Used for processing raw data at the command line
- Great for sifting through tabulated data
	- Like Zeek logs
- Can perform statistical analysis
	- Min, max, mean, etc.
	- Can add together values
### Datamash example
![[Pasted image 20230812135422.png]]


















