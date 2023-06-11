---
creation date: March 30th 2023
last modified date: March 30th 2023
aliases: []
tags: #📖
---

Primary Categories: [[05 - INE eJPT Notes]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[Website Recon and Footprinting]]  

### What are we looking for
	IP Address
	Directories hidden from search engines
	Names
	Emails
	Phones numbers
	Web Technologies

---

How to find IP Address using CLI and website address

```Bash
host website.com
```

Output will give IPv4 and IPv6 along with Mail server

---

### General information from website

Good place to start when looking for information on webiste is robots.txt

```
website.com/robots.txt
```

This is a text file used by search engines to hide things from public view, files or folders for example; /wp-admin/

```
website.com/sitemap.xml
```

This is a file to provide search engines a easy way to catorgize the website

---

### Gather information on web technology footprinting

Browser Add-Ons

	Builtwith - Extension shows what type of tech is used, wordpress, google analytics, widgets, etc.
	Wappalyzer - Similar type of program to builtwith 

Kali method

```bash
whatweb website.com
```

Whatweb will gives similar to extensions, but its not as easy to read. using pipes or greps may make this better when needed

---

### Download entire website

httrack.com - Free tool to download a website to local directory.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: March 30th 2023 (12:17 pm) 
Last Modified Date: March 30th 2023 (12:13 pm)
