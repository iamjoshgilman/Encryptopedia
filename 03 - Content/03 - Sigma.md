---
creation date: June 21st 2023
last modified date: June 21st 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Security Information and Event Management]] | [[000 - Global Index]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Sigma]]  
---

Sharing SIEM rules can be an extremely beneficial process for a security team, whether they’re sharing them or retrieving them, but SIEM rules are written in specific structures depending on the SIEM platform. While it’s possible to share the logic of the rule (how it works) in plain English, there is a better way to quickly share or ingest SIEM rules shared by teams around the world. In this lesson we’re going to introduce you to Sigma.

To ensure accuracy we’ve copied information directly from the Sigma Github page available [here](https://github.com/Neo23x0/sigma).

## **What is Sigma?**

Sigma is a generic and open signature format that allows you to describe relevant log events in a straightforward manner. The rule format is very flexible, easy to write, and applicable to any type of log file. The main purpose of this project is to provide a structured form in which researchers or analysts can describe their detection methods and make them shareable with others.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/03977171c62b3d50167cf173c1d3e6ae0af22c65dcd9f7fab0a1174228007d410bf1be317dae0e9bd6cbb7e70e54.png)

Rules can be written in the Sigma language and then using a converter (Sigmac) they can be exported as rules in the correct format for a number of different SIEM platforms. This process can also be reversed allowing security professionals to export rules from their vendor format to Sigma format so they can be used by teams with a different SIEM.

## **Which Platforms Support Sigma?**

- Splunk
- QRadar
- ArcSight
- Elasticsearch (Elastalert, Query strings, DSL, Watcher, & Kibana)
- Logpoint

## **Benefits of Using Sigma**

- Describe your detection method in Sigma to make it sharable
- Write your SIEM searches in Sigma to avoid vendor lock-in (meaning you can flexibly change the SIEM solution without having to lose all of your custom rules)
- Share the signature in the appendix of your analysis or research report along with IOCs and YARA rules to allow others to replicate your work and build detection rules
- Share the signature in threat intel communities (ISACs) – e.g. via MISP (which we covered in the Threat Intel domain!)

## **SIGMA Rule Example**

In this example we’re looking at a Sigma rule that can detect when a web server has been compromised and is running a web shell, allowing a malicious actor to visit a specific URL which will provide them with a console, allowing them to execute commands as if they are on the server. We’ll break down the rule below, even though it’s really human-readable!

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/33cb6db6d749401c108735754ea81e60f009a6f6cb4486e17dd1cf18b4b86736fd93c8c11198ef70851c6f0aca14.png)

  
On line 6 we can see that the ‘detection’ is declared, stating how this rule works. Line 7 states it is using the method of matching keywords against a URL string (mentioned on Line 2).

So if this rule was actively being used to monitor a web server and we had a web shell running on _https://example.com/13919595/asjkdasjdkasjvn/shell.php?_ , and we visited the interface and tried to use the command `whoami` this would be included in a GET HTTP request to the web server, meaning the URL will be changed to include ‘=whoami’. This activity would generate an alert for the security team to investigate, making them aware of the web shell. It is extremely unlikely that a normal visitor would ever need to include these operating system commands in a GET URL request so there is a low rate of false positives (but some scenarios are covered on lines 13 and 14).

There are some great real-world rules to take a look at on Florian Roth’s Github page [GitHub – Neo23x0/sigma: Generic Signature Format for SIEM Systems](https://github.com/Neo23x0/sigma). Additional rules are available at [https://github.com/SigmaHQ/sigma/tree/master/rules](https://github.com/SigmaHQ/sigma/tree/master/rules). We highly recommend taking a look at these to better understand how they function.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 21st 2023 (11:36 am) 
Last Modified Date: June 21st 2023 (11:36 am)
