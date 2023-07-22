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

# [[03 - Writing Sigma Rules]]  
---

In this activity you’re going to be taking a look at some Sigma rules and writing your own by editing a pre-built rule. The purpose of this activity is to get you familiar with a vendor-agnostic detection format that can be applied to major SIEM providers, but also to develop your ability to think logically about detections.

First, you’ll need to go [download the Sigma master ZIP file from the Github](https://github.com/SigmaHQ/sigma):

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/0a52cc9ca27bf063b29c5c1d3142a286242114261a4bafa5648680379102c7990fb4ebfb67bbb85b876f94c04ece.png)

Once you have the .ZIP file we need to extract the contents. To make things easier create a folder on your Desktop called ‘BTL1-SIGMA’, move the downloaded ZIP file to this folder, then extract it.

  
![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/8e01fa2cbe0393bd7447bc795c342f280f6cac7f5cd08f9b258b8df534ff9782ec13f876c2a6833db65bf890bc2a.png)

Open the ‘rules’ folder – we’re presented with a number of sub-folders that contain some basic rules:

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/002b12c46f92f32a1c55e787ef650aaf351270b6275a7c2ce24bba79ed04e55efab7e1585464703f64f476c41b3a.png)

Now go into the ‘network folder’ and then open ‘net_dns_c2_detection.yml’ in Sublime Text 2 (or your text editor of choice):

  
![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/0ece554701bed77bfb768b549ba15e5937835e31e0ee03c0ed50dedf3be0d77eba495c6440c61e685d39f4a6a2e2.png)

Before we start customing this rule to suit our own needs, let’s recap exactly what this rule is doing and how it’s formatted. Take note of the different rows explained below, as you’ll be editing some of these very soon!

  
![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/d97132c3bbe6159245a025b0212ac1cc8ffcce7bc16330d3c0fa40dfff2d59fd4c0ac724f92642752d2ff54fcda7.png)

| Term              | Definition                                                                                                                                                                                    |
|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **title**         | A custom descriptive value that provides a very brief explanation of what the rule is looking for.                                                                                           |
| **id**            | A unique identifier used for this rule.                                                                                                                                                       |
| **status**        | A custom descriptive value used to explain the state of the rule, such as "incomplete," "experimental," or "production."                                                                      |
| **description**   | A custom descriptive value providing a more detailed explanation of what the rule is trying to detect and how.                                                                               |
| **author**        | A custom value that holds the author(s) of this SIGMA rule.                                                                                                                                   |
| **date**          | A custom value indicating the date the rule was first created.                                                                                                                                |
| **modified**      | A custom value indicating the date when the rule was last edited by an author.                                                                                                                |
| **references**    | A custom list holding URLs that help explain what the rule is trying to detect.                                                                                                              |
| **logsource**     | Explains the logs required in the SIEM for the rule to function.                                                                                                                             |
| **logsource category** | In this case, it is "dns," indicating that the security team needs to pull DNS logs into their SIEM for the rule to work.                                                                 |
| **detection**     | Explains the logic behind the rule, including conditions that, when met, can generate an alert.                                                                                             |
| **selection**     | States that something must be selected from the DNS logs. In this case, it's the parent domain or root domain (e.g., Google.com).                                                          |
| **parent_domain** | Specifies the log field that should be selected. The * symbol represents a wildcard, meaning that any value can be used. This means that ANY domain should be selected.                     |
| **condition**     | States the actual detection logic. For this rule, it retrieves all parent_domain values and counts the number of queries to that domain. If the count is over 1000 (> 1000), it will generate an alert. |
| **falsepositives**    | A custom list stating how false positives could occur.                                                                                                                                        |
| **falsepositives 2**  | The author explains that legitimate software using DNS to transfer data could generate an alert, even though it is not malicious activity.                                                  |
| **level**         | A custom descriptive value indicating the urgency of this alert.                                                                                                                             |
| **tags**          | A custom list including different MITRE ATT&CK techniques that can be detected using this rule.                                                                                            |

So, we know that this rule is used to detect potential [DNS tunneling](https://attack.mitre.org/techniques/T1071/004/) for command-and-control communication by looking for a large number of queries to domains, and will alert when 1001 or more requests have been observed by looking at DNS logs.

Now it’s your turn to make some changes, allowing us to detect some specific activity. Read the intelligence briefing below and try to make changes to this existing rule file to reflect the information provided.

## **Intelligence Briefing**

We’ve recently observed a new type of malware that we have named ‘TRANSPORTER’ which uses DNS tunneling to provide a command-and-control channel across the internet, allowing an attacker to send commands to infected systems. As DNS traffic is extremely common in environments this traffic blends in and does not immediately look suspicious. DNS packets contain many fields and headers in which data can be concealed.

At the time of writing, we have only observed one domain name that is being used to send and receive C2 traffic, which we have included below. Speaking with one victim we observed that their SIEM did not detect this activity as they were not monitoring for excessive DNS queries to domains.

**Domain Name:** redhunt.net  
**Average Number of Requests:** 500  
**MITRE ATT&CK Techniques Used:** T1071.004 (Application Layer Protocol: DNS)

**Tips**

- You can remove the ‘id’ and ‘modified’ lines from the existing rule as they are not required.
- Use the ‘title’ and ‘description’ lines to include information from the above intel briefing.
- Consider the average number of requests, we should alert on something that is lower than this to catch any infections where the traffic count falls below this average.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |
| https://www.elastic.co/guide/en/security/current/rules-ui-create.html | Create Detection Rules, Elastic

Created Date: June 21st 2023 (11:11 am) 
Last Modified Date: June 21st 2023 (11:11 am)
