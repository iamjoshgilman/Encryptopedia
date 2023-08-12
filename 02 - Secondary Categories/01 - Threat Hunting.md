Primary Categories: [[01 - Blue Team]] | [[000 - Cybersecurity Materials]] 
Secondary Categories: [[]] 
Search Tag: #🗺  

# [[01 - Threat Hunting]]  
***

```bash
192.168.140.139
```

![[Pasted image 20230812111539.png]]

## Networking

The network is the great equalizer
- You see everything, regardless of platform
- Desktop, servers, IIoT, etc all reviewed the same
#### <u>You can hide processes but not packets</u>

Malware is usually controlled
- Which makes targeting C2 extremely effective
- Identify compromise when C2 "calls home"
- Must be frequent enough to be useful

## Threat hunting process order

- Identify connection persistency
- Business need for connection?
	- Reputation check of external IP
- Abnormal protocol behavior
- Investigation of internal IP
- Disposition
	- No threat detected = add to safelist
	- Compromised = Trigger incident handling


























