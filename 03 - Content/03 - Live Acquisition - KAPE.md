---
creation date: June 19th 2023
last modified date: June 19th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Digital Forensics]] | [[000 - Global Index]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Live Acquisition - KAPE]]  
---

In this lesson, we’re going to look at the forensic tool KAPE: the Kroll Artifact Parser and Extractor. KAPE is an efficient and highly configurable triage program that will target essentially any device or storage location, find forensically useful artifacts, and parse them within a few minutes. It is suggested that during a digital investigation a disk imager should be initialized to collect a full disk image of the target system, and KAPE should be run alongside to immediately collect important evidence, even before the full disk image has been acquired. This means that law enforcement and security teams can get results extremely quickly, which can generate new leads for investigation.

It is possible to deploy KAPE on a large scale using PowerShell to download, run, and send the results from KAPE back to the security team, making it an incredibly useful digital forensics and incident response triage tool.

Below we’re going to show you KAPE in action, performing live acquisition against our own running system just to demonstrate some of the functionality and information that this tool can retrieve in an extremely short space of time.

Looking in the KAPE folder, there are two executable files, kape.exe, and gkape.exe. We’ll be using gkape.exe, which is the graphical version of this tool. Let’s run it. We can split the interface into three sections:

- **Top Left –** Targets are how we can choose exactly what information we want to retrieve from the target system, so we can get it as quickly as possible. This can be anything from system memory to web browser data.
- **Top Right –** Modules provide additional functionality and allow operations to be conducted with the retrieved data, such as analysis of information collected from the target system. These build on the Target options and allow us to fine-tune the information we want to collect.
- **Bottom –** The Command-Line section builds up the query which is passed to KAPE for execution.

  
![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/8c3e09e8343034128158ebed1654453d17c06e49232cd7d98423acd6e5332fd9e2972bbd45b06ecc051b96c181e6.png)

When we click the checkbox to enable Targets in the top left we first need to provide the target source. This would typically be a disk image, but for this walkthrough, we’re going to use our host system’s C drive.

  
![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/becab6a7e2586f4d056ec4a5027ea0341d2c99bd84d27ae9affb201287835584703e75e94a3f519c6a636a37fc4d.png)

Next, we need to set a location for where files collected by KAPE will be saved. We’ve set it to a new folder in our Documents called KAPE Output.

  
![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/6df632c3be344227ebc38a11f14baea985d52bf8859dae448e388cb7e2fcc9b5e4c1ea291973e3c735426266df53.png)

Next, we can select our targets. For the first example, let’s collect information from the most popular web browsers out there; Chrome, Edge, and Firefox. We can scroll down the Targets box and find them.  
 

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/86fd20b0d23a3dce3f3740db925b46db879000e3e155198bf010166e2f791f873c58af3a3065856c0f800e79b90b.png)

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/853dee97f608ff6fd08c5ef69c95cb9a55b0f3b5df521b088e2190f4479347b0d57076e01c6af9be4610704c7442.png)

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/e152803c6ea10414967d0428713ab6dd7508dbe354b283a92f57f87f4fe3c9a6a1f2a6c915223b31a2d36ead21ca.png)

Once we have all of our Targets selected, we can click the Execute button at the bottom right to start KAPE.

  
![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/ee74ebd5dc5ca5e5de11798fd64681e89ebff663892d77caaf994818fab10c5b1bbf694bb21112a146175f90ee8b.png)

KAPE will open a terminal and start retrieving copies of the files we have requested.

  
![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/7a4128714ec8bfe04c12aaab9fbc8be34c5f94c353514cb2626cbf7c0e67e85d9e3df9fc4e930b25700e30eccf7f.gif)

Let’s see what KAPE found by navigating to the directory we set as our Target destination earlier. We can see that there are a number of logs, telling us exactly what KAPE did during the acquisition. We also have a folder named “C” after our host system’s C drive.

  
![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/7cbce1a9606ed0dfd1064e9043c31cbf45b6ab00db65b3608041f9361a02fb764b0bd82ca51142d9ef20bc510258.png)

At the following file path, we can see that KAPE found some interesting files regarding activity conducted using the Firefox browser on this system, including cookies (which can tell us what sites the user has visited) and form history which could include personal information such as addresses, names, date of birth, and more.

  
![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/e65860cf1997552f9ef6def5015e8808e7aa49dc5fa3b28e59b59308ab8e1f8ec08c6d532fae2f35234b73aa5f64.png)

In the below screenshot we can see that KAPE has also retrieved some really useful information regarding Google Chrome.

  
![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/ba971f8b0c24834667dbeebef6a028b99c11f75f63cd418d1353bd0e1e1e5dc1e7a790639062701eba014ad81b10.png)

And finally, we have some files from Internet Explorer/Edge such as web caches.

  
![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/f984921f4546fedebab2395b78cdecdd80954bb7a563130f5a3061c30d22517db512ed960d9a2923f350f9f085ec.png)

KAPE can be used to quickly retrieve tons of information, such as; Windows event logs, antivirus logs, file system metadata, log files, deleted files, emails, and absolutely tons more. We strongly recommend that students install KAPE and use it to analyze their own systems to become more familiar with using this tool. You can download KAPE for free here – [https://www.kroll.com/en/services/cyber-risk/investigate-and-respond/kroll-artifact-parser-extractor-kape](https://www.kroll.com/en/services/cyber-risk/investigate-and-respond/kroll-artifact-parser-extractor-kape)


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 19th 2023 (07:01 pm) 
Last Modified Date: June 19th 2023 (07:01 pm)
