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



