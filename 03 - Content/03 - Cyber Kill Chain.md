---
creation date: May 31st 2023
last modified date: May 31st 2023
aliases: []
tags: #📕
---

Primary Categories: [[01 - Administration]] 
Search Tag: #📕  

# [[03 - Cyber Kill Chain]]  
___
# Cyber Kill Chain: Comprehensive Course Notes

## 00: What is the Cyber Kill Chain?
* The Cyber Kill Chain is a model created by Lockheed Martin in 2011, used for understanding the steps an adversary takes to breach a network.
* The chain consists of seven stages:
    1. Reconnaissance
    2. Weaponization
    3. Delivery
    4. Exploitation
    5. Installation
    6. Command & Control (C2)
    7. Actions on Objectives

## Phase 1: Reconnaissance Phase
* The first phase in which the attacker researches, identifies, and selects targets.

|Key Aspects of Reconnaissance| Examples|
|----|----|
| Passive Gathering | Researching public records or information posted online |
| Active Gathering | Interacting with the target system, for instance, port scanning |

## Phase 2: Weaponization Phase
* The attacker creates a malware payload intended to exploit the target.

|Types of Malware| Function|
|---|---|
|Ransomware|Encrypts a user's data and demands payment for the decryption key|
|Spyware|Stealthily collects information without the user's consent|
|Trojans|Misrepresents itself to appear legitimate|

## Phase 3: Delivery Phase
* This is the method by which the weaponized bundle is delivered to the victim.

|Common Delivery Methods| Description|
|----|----|
|Email Attachments|Often disguised as a legitimate attachment|
|Drive-by downloads|Involuntary download of malware by visiting an infected website|
|USB baiting|Leaving a USB containing malware in a location where someone will find it and use it|

## Phase 4: Exploitation Phase
* The exploitation phase is where the malware delivered to the victim exploits a vulnerability in the system or network.

|Vulnerability Exploitation| Description|
|---|---|
|Software vulnerabilities|Occurs when software contains bugs or misconfigurations|
|Zero-day vulnerabilities|Exploits that take advantage of vulnerabilities on the same day that the vulnerability becomes generally known|

## Phase 5: Installation/Persistence Phase
* The malware establishes a presence on the infected system, usually in a way that allows it to persist even after system reboots.

|Malware Persistence Methods| Description|
|---|---|
|Registry modifications|Changes to the registry to start the malware during system boot|
|Rootkit installation|Software tools that enable an unauthorized user to take control of a computer system without being detected|

## Phase 6: Command & Control (C2)
* This phase is when the malware communicates back to the attacker, essentially giving the attacker "command and control" over the victim’s system.

|C2 Communication Methods| Description|
|---|---|
|HTTP/HTTPS|Communication disguised as regular web traffic|
|DNS requests|Malware communication disguised as domain name lookup requests|

## Phase 7: Actions on Objectives Phase
* The final phase where the attacker takes action to achieve their goals, such as data exfiltration, data destruction, or encryption for ransom.

|Types of Actions| Description|
|---|---|
|Data exfiltration|Unauthorized copying, transfer or retrieval of data from a computer|
|Data destruction|Deleting or corrupting the victim's data|

## Adversary Simulation
* Adversary simulation involves simulating a full attack lifecycle to test and improve network defenses.
* This often involves ethical hacking and red team operations.

|Key Aspects of Adversary Simulation| Examples|
|----|----|
|Ethical Hacking | Conducting attacks on one's own systems to find vulnerabilities |
|Red Teaming| Simulating real-world attacks to test security |
|Purple Teaming| Combining attack (Red team) and defense (Blue team) actions to enhance security | 

# Conclusion
* The Cyber Kill Chain model is a useful tool for understanding and preventing cyber threats.
* Each phase of the chain offers opportunities for defensive actions.
* Simulating real-world attacks can help strengthen an organization's defenses.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: May 31st 2023 (01:23 pm) 
Last Modified Date: May 31st 2023 (01:23 pm)
