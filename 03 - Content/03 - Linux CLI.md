
Primary Categories: [[01 - Administration]] 
Secondary Categories: [[]] 
Links: [[Linux]] - [[CLI]]
Search Tag: #📖  

# [[03 - Linux CLI]]  

## SSH - Secure Shell Login
	ssh [username]@[IP address]

## pwd - Where am I within system
	Print Working Directory

## locate - find file or directory
	locate passwords.txt

## Make a File
	Touch [info.txt]

## Make Directory
	mkdir [Storage]

## What is my IP
	ip addr show tun0

## "Load" IP into terminal
	export IP= [IP Address]

## $IP - Use exported IP address
	nmap $IP

## Search for SUID files
	find / -user root -perm -4000 -exec ls -ldb {} \;

## Netcat 'reverse shell listen'

	nc -lnvp [port] 

## Find websites IP address
	host [website]

## Display route to reach a target 
	traceroute [website]

## Can't use 'cat' - read file

	while read line; do echo $line; done < file.txt
	grep . file.txt

## base64 decode - keep adding "| base64 -d" if not working

	echo "base64" | base64 -d

## Cut info out using spaces
	cat ip.txt | grep "64 bytes" | cut -d " " -f 4

___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: February 17th 2023 (08:38 am) 
Last Modified Date: February 17th 2023 (08:38 am)
