---
creation date: June 22nd 2023
last modified date: June 22nd 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Incident Response]] | [[000 - Global Index]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - CMD and PowerShell For Incident Response]]  
---

## **Why do we use CMD?**

Although using it requires the memorization of many different commands, it can allow us to complete tasks faster than interacting with the Windows graphical user interface, and also allows us to automate tasks using batch scripts. This can help in incident response scenarios, as we can query the system for information about almost anything, from users to running processes!

## **CMD For Incident Response**

Below we’re going to cover a number of commands that may be useful for security investigations and incident response. We will also include examples so you can see what the input could look like, and how to interpret the information that is printed to the terminal. These commands should be run as an administrator to function correctly.

## `ipconfig /all`

**Description:** This command will get network configuration information from the local system, including the assigned IP address and the device’s MAC address.

**Example:** In this example we can see that we have the hostname “**`MSEDGEWIN10`**“, a MAC address of “**`00-0C-29-AA-02-FA`**“, and IPv4 address of “**`192.168.125.129`**” . We can also see that the DNS server being used for name resolution is currently “**`192.168.125.2`**“.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/14847d805a0d38e67490eb2e75c82dd93209fe5d7ee211d1e08262afbd0cfafa805786899cb61ad98be391b0fe55.png)

## `tasklist`

**Description:** This command will check running processes and programs and print a list to the terminal.

**Example:** In the below screenshot we are presented with a list of running processes, their process identifiers (PIDs), and the memory usage in the final column. This can be helpful to identify processes that are running in the background and how many system resources they are consuming. This can be a good way to identify malware such as crypto miners which will work silently, but consume a lot of system memory to work.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/b7ce06f11ace9fa50046e1ed6ac35acfac93461e58f01b11b3dbc9b9487b09adde303644c48f7c26210b2805b9d0.png)

## `wmic process get description, executablepath`

**Description:** This command will display running processes and the associated binary file that was executed to create the process.

**Example:** As the description states we are able to view running processes and the executable file that initiated them. Look just below halfway down the list and you’ll find Discord.exe on the left-hand side (process name). To the right on the same row we can see that Discord was launched from C:\Users\IEUser\AppData\Local\Discord\app-0.0.307\Discord.exe – we now have the full file path! We can use this command to identify unusual process names and identify where the executable file is so we can analyze it. Processes that are running out of unusual locations such as /tmp/ and /Downloads/ are definitely worth investigating further!

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/f1fb37891788dd468653e80b2a1c33e6210b34aae18de7b4b1e167b5443d9c33f3d9131452d601b40dd955084a83.png)

## `net user`

**Description:** This command will print a list of all system users to the terminal.

**Example:** Using this cmd command we have printed all local system users, regardless of usergroup, to the terminal, in this case we can see:

- Administrator
- DefaultAccount
- Guest
- Jeff S
- MarkA
- sshd
- SteveE
- WDAGUtilityAccount

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/38597dff88aa442f0e97a1639040f331f3bb0db325b7b4cfe67d1e95cd15a107c2f8ddf43edd70b06d9ab0320d89.png)

## `net localgroup administrators`

**Description:** This command will list all users that are in the administrators user group.

**Example:** In the below screenshot we can see all administrator accounts on this system. In this case it is the following:

- Administrator
- Jeff S
- MarkA
- SteveE

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/36de2e89e9156913dde61b5bf16e571888fa4c5a69fa1dbe9f58aeb476cfdd2fc6a7f066122cf59adb6cd7d4f7d9.png)

We can replace “administrators” with any local group that we want to enumerate. To see a list of all groups, use the command **`net localgroup`**. If you want to search for users in a group that includes spaces, you’ll need to run your commands like this: **`net localgroup "Remote Desktop Users"`**.

## `sc query | more`

**Description:** This command will list all services and detailed information about each one.

## `netstat -ab`

**Description:** This command will list open ports on a system, which could show the presence of a backdoor.

---

# PowerShell

## **Why do we use PowerShell?**

PowerShell is amazing, and chances are you’ll use it a lot while working in the security industry. We can automate complex tasks, use it for offensive security purposes, or during security investigations to get more information about a user or system. For incident response, we can use it similarly to CMD, but we can often retrieve much more information.

## `Get-NetIPConfiguration` and `Get-NetIPAddress`

**Description:** Similar to ifconfig in CMD, we can use the two above commands to get network-related information from the system.  
**Example:**

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/c2843edae26ec276eec5b5fb1f16778f4b0f026d50b6409b5566fbc5e8d3b334f443bb45792811e75b2b5be06146.png)

## `Get-LocalUser`

**Description:** Using the above command we can list all local users on the system.  
**Example:**  
![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/e6ca98e4d82266fdac36ddc5c3ce0b9d48dfe91d694ba84974f32f0b106c7c2c8947964100dfc289761da3cffe6d.png)

## `Get-LocalUser -Name BTLO | select *`

**Description:** We can provide a specific user to the command to only get information about them. Piping ( | ) the results to a “select” with a wildcard ( * ) will give us all of the properties for the command, providing us with valuable information about the account. This can be extremely useful for us as incident responders, especially when we find local accounts that do not expire or have passwords that don’t expire.  
**Example:**

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/699dd62b14b5b29cea9c745c32a4d03e03ce4b0bee43c5e976ec17e3ded5be894fede0336d838e5be327fe03909a.png)

## `Get-Service | Where Status -eq "Running" | Out-GridView`

**Description:** The above command let’s us quickly identify running services on the system. By piping ( | ) the command to Out-GridView, we are telling PowerShell to show us the results in a nice windows, which is much easier to work with than outputting the results to the PowerShell window.  
**Example:**

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/e3db71b7bbe22eca2cfaabbbb276c5993cb4770a6ceae12c78f7b48604fe82b0bf650d2c62feec700110c1430674.png)

## `Get-Process | Format-Table -View priority`

**Description:** Another great command is the ability to group running processes by their priority value. Using the above command we can see the process name, the process ID (PID), and other information, where different priority ratings are grouped into tables.  
**Example:**

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/333e5c799e7061439580422c78c6329b134a99dd1542dc778a45b7ee3a7c90d16f438dc9cfe00966875e78b01e6c.png)

## `Get-Process -Id 'idhere' | Select *`

**Description:** We can collect specific information from a service by including the name in the command (-Name ‘namehere’) or the Id, as shown above and below. Piping to Select * provides us with all the properties.  
**Example:**

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/e77b3ec90c70a64a433fd5bb45488d72742abf1fef5d1d1ce21a60d1007783f03072459f951380c64d75ada67a4f.png)

## `Get-ScheduledTask`

**Description:** Similar to Services, Scheduled Tasks are often abused and utilized a common persistence technique. With the above command we can list tasks that are set to run after certain conditions are met.  
**Example:**

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/00f6722c4ac78127e8c36c4244ae6e1e1aaa413789a820bc251eedd2384ed59532d72d3a769f9826a595c96f096f.png)

## `Get-ScheduledTask -TaskName 'PutANameHere' | Select *`

**Description:** We can dig deeper by specifying the task we’re interested in, and retrieving all properties for it.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 22nd 2023 (12:15 pm) 
Last Modified Date: June 22nd 2023 (12:15 pm)
