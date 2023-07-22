---
creation date: June 23rd 2023
last modified date: June 23rd 2023
aliases: []
tags: #📖
---

Primary Categories: [[]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Using ATT&CK Navigator]]  
---

In this activity you’re going to become familiar with using ATT&CK Navigator as a tracking tool, and understand how it can be used by blue team and red team members with the ultimate goal of improving an organisation’s security posture. At the end of this lesson you’ll get hands-on with this tool and answer a number of questions about ATT&CK Navigator.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/files/c07af856f6a3c98d49647c9082673ad1e5edfe279b28efe843c850c8244dd1e1865f35db06409cce5894b035823c.png)

The above image is a screenshot of the MITRE ATT&CK framework in ATT&CK Navigator. We have specified a number of techniques that were “used” by an adversary in a fictional attack. Can you work out what the attacker did by looking at the colored items?

**In this example the attack scenario would look something like this:**

1. An attacker sends a phishing email to an employee at the target organization including a Microsoft Word document with a malicious macro.
2. PowerShell was executed to download an executable file that initiates a reverse connection to a command-and-control server (C2) and was added as a scheduled job to execute at a routine interval on the infected system to provide persistence.
3. The registry was modified to reduce the chance of detection.
4. The attacker then dumped credentials from the OS by retrieving memory from LSASS.exe and then standard sniffing network traffic to identify other online systems and the services they are running.
5. The attacker logged into other systems using the valid credentials obtained from LSASS to perform lateral movement.
6. Emails and local files were collected and prepared for exfiltration.
7. These files were encoded and exfiltrated through a connection to the C2 server, uploading them to an external attacker-owned system.
8. Ransomware was then deployed to cover the attacker’s tracks and cause disruption to the target organization.

While the above image doesn’t capture all of the details, it is immediately clear what techniques were used by an adversary in this fictional cyber attack. If you can’t already see the value of using ATT&CK Navigator, let’s explore some more use cases for this tool!

# For Threat Hunting

## **The Purpose of Threat Hunting:**

Threat Hunting is the process of identifying threat actors that have already made it past the perimeter and are now operating inside an environment undetected. It is our job to create a hypothesis, investigate it, and come to a conclusion. An example could include “I believe that malicious actors are utilizing PowerShell within the environment to complete malicious actions”. We would then look to audit all PowerShell logs and look for specific commands that are suspicious or malicious, either proving or disproving our hypothesis. Threat Hunting requires a very mature security function as some basic requirements include experienced analysts that understand the ATT&CK framework and cyber kill chain, centralized logging (more than just a SIEM!), and the time to deep-dive into endless logs and events to find the ones that indicate the presence of an adversary.

## **How ATT&CK Navigator Can Help:**

A great way that ATT&CK Navigator can be utilized is to keep track of what techniques the threat hunters have tried to discover the presence of. For example, if we wanted to hunt for malicious phishing emails that adversaries have sent that haven’t been detected by employees or security controls (such as spear-phishing emails) then we would create an ATT&CK graph and begin our phishing threat hunt. Once this was concluded the team could color in that technique to show that they have conducted a hunt to try and detect it.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/files/fb044cd944c8de3b6437d8820248ab429f03710b878fdb0a5e638a65a2796f3b59f349369f6646e6ca0f92a9f4d5.png)

Then the hunters would move onto the next technique they want to check, over time building up an image of everything they have manually searched for. Green techniques could be ones that no malicious presence has been discovered during a hunt, while red could show malicious presence has been detected. This all ties in with ‘threat detection’ which we cover below!

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/files/2d10ead89d1eaecba1886e6e2dcf14ce8087f8d37d7c003bc5d710b387eb9afbe73e62ee38c45bb0c16371239ebd.PNG)

# For Adversary Emulation

## **The Purpose of Adversary Emulation:**

Adversary Emulation is different from a standard penetration test and requires a lot more time and knowledge. Why? because the aim is to accurately imitate advanced threat actors attacking the organization by copying all of their known tactics and techniques. Organizations with mature security teams would likely conduct these events, and have the red or purple team members imitate the techniques of threat actors that are likely to target the organization based on previous attacks, motives, and industries the actor's target. This can help to tune detection rules and ensure that the security team would have visibility if that actor attacked them using the same or similar tactics.

## **How ATT&CK Navigator Can Help:**

On the [MITRE ATT&CK page for groups,](https://attack.mitre.org/groups/) it covers what techniques they have been known to use. From these lists we can create an instance of ATT&CK Navigator to visually map the techniques they have used, and refer to the diagram while conducting the red team engagement, effectively replicating an APT attack. But guess what! This is already built into ATT&CK Navigator! We can simply click on the “multi-select” tool, and then choose the threat actor we want to map.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/files/04abe843f99c1e4b28cc184a04321338dced955a7bb1a262e0268e953dc544fab6d6b4dddd1c462ab4b818e82a9e.png)

In the below screenshot you can see that we have mapped the techniques used by APT1 and then used the paint bucket tool to color them in red. If we were going to start a red team engagement, we would then look to actively use these techniques and once the engagement is over, work with the blue team to see if any of the actions were not detected. If they weren’t then rule tuning and additional emphasis on detection rules and monitoring should be raised so that in the future these techniques are properly alerted to security analysts.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/files/2c328a97f68fa7313dd8e6b8552c7f66599f12c81a2913831cc73701bf3e2f8821a4773c4e78743afc2eee539c3c.png)

# For Threat Detection

## **The Purpose of Threat Detection:**

Threat Detection is all about ensuring that the monitoring and detection capabilities of the defenders are as accurate as they can be. From tuning false positives to writing new rulesets, security teams are constantly adapting the way they detect malicious actors from a mountain of data.

## **How ATT&CK Navigator Can Help:**

Similar to how we can use ATT&CK Navigator for threat hunting, we can do the same for assessing detection capabilities. One-by-one we would select a technique and review existing detection rules to identify whether the security team would get an alert if that activity was conducted, such as [Dumping OS Credentials](https://attack.mitre.org/techniques/T1003/). One example would be; is the security team monitoring for processes that are interacting with lsass.exe? If not then a rule needs to be created in the SIEM or EDR solution to generate an alert when this activity is observed so analysts can investigate further. Using ATT&CK Navigator we could mark techniques that have been successfully tested against current capabilities and generated an alert (green), techniques that required a rule to be created or tuning of an existing rule (amber), and techniques that are currently not detectable and are pending a new rule or detection method (red).

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/files/65d9973525d1f944c83aead596fd75864bcffbc87ebaad47d8440460516a2b2b5a1b5eb0d38f6858cf1de91eebe7.PNG)

# Using ATT&CK Navigator

Now that you understand why ATT&CK Navigator can be a useful tool for both red and blue teams, let’s cover how to use it. You can access the tool online the MITRE Github page here – [https://mitre-attack.github.io/attack-navigator/enterprise/](https://mitre-attack.github.io/attack-navigator/enterprise/)

First things first, let’s create a new layer for our graph. Click ‘Create New Layer’ and then select ‘Enterprise’.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/files/24c4eff3e1ee70be31ee45bd9dff5391fb854db85e579a7c82c57d8c68af68e5ca9e325ad3775b26bc48806ccb34.png)

On the top left we have our current layer and the ability to add additional layers (similar to Photoshop if you’ve ever used it). On the top right we have all of the controls and tools we’ll need to customize our layer.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/files/ba548119836525cbf5b38f69585f039fd058dfc9e7eaff42c6b181830e585786da8d310696b0361b3cbe16d837fe.png)

We can see all of the techniques underneath the toolbar. Notice how some of them have grey bars next to them – these are techniques that have sub-techniques. We can expand them by clicking on the grey bar as shown below.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/files/f796515a1109fbcab16bce4a52074fb9481b60aa4c969e793f5d3b114905b34900fc878f50c5194c863d8cf4938c.png)

Next let’s cover how to colour fill different techniques, this could be used to highlight specific set of techniques for purposes such as:

- Marking off techniques that have been simulated and observed by a security team to see if they can detect the activity (red = not detected, orange = often detected, green = always detected)
- Highlighting which techniques will be emulated during a red team engagement

By default the selection control with the padlock icon will have the first option enabled. This will select the same technique across multiple columns, let’s demonstrate by selecting a single occurrence of ‘Scheduled Task/Job’:

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/files/d6a0f7c554eebd75c0765472d47953bd734ccc4539dbb5606bdc3eb677040535615a5fcfd0be786ae4c4054f429e.png)

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/files/bdf781349fbebe1b23581e8c20e86f769d27fb4349dccbf6a7083def2fd5db00a1b0f816bdf9f06c7f044177f0f2.png)

Now that we have these selected let's apply a color to them. Go to the ‘technique controls’ section of the toolbar and click the paint bucket tool, then select a fill color:

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/files/7395ac8f7edb5e745160f44eb41e8240cd7ba8f9f76637da7b81c709d717004b082ddd95bab56942eef6579f8052.png)

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/files/980bf740701a8bc00e759ac1bcecb155e31cc74a3be9a300d661971003a214293ed2c7a4ac69d6a20892fce28f30.png)

In the below example we’ve colored a few more techniques so we can show you how to export this layer to an image file, allowing you to use it in presentations, share online, and do whatever else you want!

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/files/65b3e8bd288df025f921f3261d632417da17dbcd18eac4578b4abdc77f35843aebe01132157eb57f3d0edc89f5a1.png)

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/files/4aa9b4c933a44c9a43a367451850c54937e7fbfa1efa647c113701c4c6de9d58a00fde62006e2ba78cae80cd03f4.png)

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/files/6b1a257021c9df379ff02334da02c573b9d18e866b78230d491aea04b86b5db37d749aa2dd09facaf9f9fee081f5.png)


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 23rd 2023 (11:36 am) 
Last Modified Date: June 23rd 2023 (11:36 am)
