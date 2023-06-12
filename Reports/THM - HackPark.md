
1. Starting with going to the website
	1. FLAG : Pennywise : is who is on the front page
2. Next we are attacking the login page with hydra
	1. hydra kinda sucks so we used Burp instead with intruder module
	2. FLAG : 1qaz2wsx : admin password to website
3. Gaining a shell
	1. BlogEnginge 3.3.6.0 is running this website
		1. FLAG : 3.3.6.0
	2. This is vuln to CVE-2019-6714
		1. FLAG : CVE-2019-6714
		2. Following directions on the CVE;
			1. Edit code with out machine IP and listening port
			2. Edit a post on website, upload the this file
			3. setup `nc -lvnp <port>` so we can capture the next step
			4. Visit `http://10.10.21.252/?theme=../../App_Data/files` we have a shell!
4. PrivEsc
	1. 