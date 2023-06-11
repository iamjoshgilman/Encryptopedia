---
creation date: March 3rd 2023
last modified date: March 3rd 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Administration]] 
Secondary Categories: [[02 - Linux]] 
Links: [[GREP]] - [[Bash]]
Search Tag: #📖  

# [[03 - Linux GREP Cheatsheet]]  

| Command | Description |
| --- | --- |
| grep [options] search_string | Search standard output (i.e. a stream of text) |
| grep [options] search_string path/to/file | Search for an exact string in file |
| grep 'mellon' myfile.txt | Print lines in myfile.txt containing the string "mellon" |

| Command | Example | Description |
| --- | --- | --- |
| -i |	grep -i ^DA demo.txt |	Forgets about case sensitivity |
| -w |	grep -w "of" demo.txt |	Search only for the full word |
| -A | 	grep -A 3 'Exception' error.log |	Display 3 lines after matching string |
| -B |	grep -B 4 'Exception' error.log |	Display 4 lines before matching string |
| -C |	grep -C 5 'Exception' error.log |	Display 5 lines around matching string |
| -r |	grep -r 'quickref.me' /var/log/nginx/ |	Recursive search (within subdirs) |
| -v |	grep -v 'warning' /var/log/syslog |	Return all lines which don't match the pattern |
| -e |	grep -e '^al' filename |	Use regex (lines starting with 'al') |
| -E |	grep -E 'ja(s|cks)on' filename |	Extended regex (lines containing jason or jackson) |
| -c |	grep -c 'error' /var/log/syslog |	Count the number of matches |
| -l | 	grep -l 'robot' /var/log/* |	Print the name of the file(s) of matches |
| -o |	grep -o search_string filename |	Only show the matching part of the string |
| -n |	grep -n "go" demo.txt |	Show the line numbers of the matches |




___

## Resources:

| Hyperlink | Info |
| --------- | ---- |
| https://quickref.me/bash | Bash Cheatsheet |

Created Date: March 3rd 2023 (10:18 am) 
Last Modified Date: March 3rd 2023 (10:18 am)
