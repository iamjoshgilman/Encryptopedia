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

# [[03 - Splunk Crash Course - Search Queries]]  
---

# Searching With Fields

To show you what Fields are in Splunk, we'll go to the Search and Reporting App, and enter in the following search query in the top bar:

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/6aec1ecea0d85629f43b3b5164910fb81f671e6bdc67997873d6692ccb0bddcd07c8529ef81b58061e494ef0a78c.png)

What does this search query actually mean?

- **index=”botsv1″ —** We want to search against the botsv1 dataset. Alternatively if we had multiple datasets and wanted to search across all of them, we'd use index=*
- **earliest=0 —** If we didn’t use this argument, which tells Splunk to start looking at the first event in the dataset, we would need to change the date range (on the far left) to All Time, this way is just easier

Now this dataset still contains hundreds of thousands of events, and Splunk will take a little while to search through all of them to find any that meet our search criteria, in this case, all of them. To make things easier now, we will change the Sampling value (under the search bar on the left) from No Event Sampling (all events) to 1:100. This will show 1 out of every 100 events - yes, we'll miss events, but we can fine tune of our search query then turn event sampling off!

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/48c41cce87cfe53c9db4f659a7e3f8494becaf8c7f5540ca0736ab2f8bc0b857f434c51fc6588ee82ecb2d209c1f.png)

Okay, now we’re working with a sample of the full dataset, so let’s cover what Fields are. On the left-hand side of Splunk we can see “SELECTED FIELDS” and “INTERESTING FIELDS”. This is information that has been extracted from the raw data, and sorted by Splunk. In the below screenshot we have listed some of the interesting fields, let’s click on the bottom one, “ComputerName”.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/fa5474bd3804b7a97a450fed647fe21af84ecbda4ea54ec264509a77e0b7b16efb3debe885c0f0397233c6802b7f.png)

In the below screenshot you can see that Splunk has now pulled the information in this field from all of the raw events in our sample (1:100). We can see lots of different hostnames, and how many events this name is featured in. For example, the top value we9748srv.waynecorpinc.local is featured in 1473 events.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/de55ad3592e4416f03dd0a7a47f1c4f8a1a284ea4f2c92bfc1939e7c300abad2c6b4b67ed25cc9e97eff213552b8.png)

Let’s move back up to the “SELECTED FIELDS” section, where we can see the number of hosts in our event sample (100+), the number of event sources (18), and the different sourcetypes of where data has come from (17).

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/2f47052d9131f0034daadd9809690667ebf2d0baab279c535e78b804c1132740a1f1e4f5fb5fd11c6c96f752396b.png)

Clicking on the host option will show us the 10 hosts that have had the most traffic. We can see that the “noisiest” host is 192.168.250.1, and the below that is splunk-02, and then suricata IDS.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/0e8a71491b1b90120b2f0796c275404311b06e7acf4d1b83a701007a9f5cff193436662c4e19117c4f94b535e760.png)

Next let’s look at the ‘source’ option to see where the data we’re dealing with is coming from. In the below screenshot we can see that the number one source of logs in our event sample is Windows Event Logs, specifically security logs, making up 42%. Next is udp:514, which you should recognise as syslog! Followed by Suricata IDS logs as third in the top 10 list.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/415f6196f082c23f8a53a1c69a4fc25e82f55a8f7e6c691b13d561ebd19a98dc53139d46a2affbb9a8492092d81f.png)

Below ‘source’ we have ‘sourcetype’ which shows us the type of data we have, which shows expectedly similar results to the ‘source’ field.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/6584e4a29c4c3240a51396fe68740c58ec7915baafdf13c2edeea72d6e76bafb9f48527a29b45e41d36d67b77805.png)

If we wanted to look at one of these log types in particular, such as ‘wineventlog’, we can simply click on it and Splunk will change our search query, as shown below.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/079db565739d19f59a2cbac89e8a88f2b631d1b2bb123dbfa0a6300bd5f05c84e0cbbedbd2af4d5651648259cd4e.gif)

This can be a great way to find specific information quickly, for example if we wanted to look at intrusion detection system logs, we’d filter on Suricata as our sourcetype. Let’s say we want to look at network traffic – we select fgt_traffic from the ‘sourcetype’ field menu, to see logs associated with Fortigate Firewalls (fgt).

**Please note, as we are using an event sample, you may get different results than us, and that’s fine! It just means you’re looking at a different group of events. If you don’t see the sourcetype ‘fgt_traffic’ then try refreshing your search for** `**index="botsv1" earliest=0**` **to get a new 1:100 sample.**

In the below screenshot you can see our search query has changed to include sourcetype=fgt_traffic at the end, and the first example shows a firewall log. We have highlighted the source ip, source port, source interface, destination ip, destination port, and destination interface values. These are also log fields, so the field ‘srcip’ holds the value of the source IP address. Remember from the previous SIEM domain lessons, where we mentioned that logs are not universal, and while this firewall log uses ‘srcip’, another log could use the field name ‘source_ip’ instead.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/586012c1035d5b7e96ac58983f78fde2e68fa8a65b289a735a7510f9c69e69ee15900cc4aca9d941dc85c784183d.png)

You should now understand that fields are property and value pairs from raw logs, and that we can use them to quickly narrow down our searches to look at specific log types, log sources, or quickly gather important information like hostnames and IP addresses.


---

# Field / Value Pairs

The simplest search we can conduct is for a field and a value, for example, searching against our data for the source IP field (src) and the IP address value 10.10.10.50.

```plaintext
search src="10.10.10.50"
```

With the above query, we’re looking for any logs where the source IP is listed as 10.10.10.50. If we wanted to look for any logs or network traffic associated with this IP, we could also search for logs where the destination IP is stated as 10.10.10.50:

```plaintext
search src="10.10.10.50" OR dst="10.10.10.50"
```

Let’s go through a simple scenario together. The Customer Support team have received a number of complaints that the company website is extremely slow, and some customers aren’t able to access the site. The security team believes this may be a distributed denial-of-service attack, where multiple remote systems attempt to crash or use up all of the server’s resources so that legitimate clients can’t access it. Using the following simple query we could see what traffic is being directed towards the web server:

```plaintext
search dst="10.10.100.5"
```

While this would show us any logs where the destination IP is the web server, it will also show any other logs or traffic going to that server, which could result in a lot of logs that we are not interested in. We can apply additional arguments in our search query to perform actions such as filtering on HTTP traffic only.

---

# Wildcards

What is a wildcard? A wildcard operator is the asterisk character (*) that can be used to mean **anything**. To explain what we mean, let’s go through another example. Security analysts determine that the host 10.10.10.73 has been compromised by a malicious actor, and that the next likely step in their plan is to search for other systems in that network (10.10.10.0/24). Using Splunk, we could see if the infected host has communicated with any of the other hosts using the query:

```plaintext
search src="10.10.10.73" dst="10.10.10.*"
```

In the above example, the wildcard **dst=”10.10.10.*”** is being used to represent any IP address that begins with “10.10.10.”. We could also use this to look for words that may have different versions, such as “pass” and “password”. For example, we could search for logs that contain information about login failures with the following:

```plaintext
search pass* AND fail*
```

So with this query, it will return any logs that contain the following:

- “pass” “fail”
- “password” “fail”
- “pass” “failure”
- “password” “failure”

---

# Searching For Processes

`**index="botsv1" earliest=0 Image="*\\cmd.exe" | stats values(CommandLine) by host**`

The above search query is using a new parameter, “Image=”. This is derived from Sysmon logs, such as Event ID 1, ‘New Process Created’. The Image field in Sysmon events shows the executable that has generated the process, in this example, cmd.exe, which should be located at C:\Windows\System32\cmd.exe (but we can wildcard the path). After the search for cmd.exe, we’re retrieving the events using values(CommandLine) to show what commands were used, and finally sorting it per host. Let’s see how this search looks once it has been run (with no event sampling):

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/e769d2394e05ece7ccc73b229e13117a89bc6255a983029465e56b42c0d6ff976cf0689928de6655361ff12cda59.png)  
 

---

# Additional Resources

  
If you want to learn more about searching in Splunk, we highly recommend you read the documentation on searching here – [https://docs.splunk.com/Documentation/Splunk/9.0.1/SearchTutorial/Startsearching](https://docs.splunk.com/Documentation/Splunk/9.0.1/SearchTutorial/Startsearching)

Or watch this great YouTube video created by the team at Splunk – [https://www.youtube.com/watch?v=xtyH_6iMxwA](https://www.youtube.com/watch?v=xtyH_6iMxwA)


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 21st 2023 (11:51 am) 
Last Modified Date: June 21st 2023 (11:51 am)
