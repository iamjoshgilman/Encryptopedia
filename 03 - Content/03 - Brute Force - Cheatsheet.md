---
creation date: May 28th 2023
last modified date: May 28th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Red Team]] | [[01 - Cheat Sheets]]
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Brute Force - Cheatsheet]]  
---
## Default Credentials
- Search in Google for default credentials of the technology that is being used, or try these links:
  - [DefaultCreds-cheat-sheet](https://github.com/ihebski/DefaultCreds-cheat-sheet)
  - [Phenoelit - Default Password List](http://www.phenoelit.org/dpl/dpl.html)
  - [Vulnerability Assessment - Default Passwords](http://www.vulnerabilityassessment.co.uk/passwordsC.htm)
  - [Default Router Passwords List](https://192-168-1-1ip.mobi/default-router-passwords-list/)
  - [Data Recovery - Default Passwords](https://datarecovery.com/rd/default-passwords/)
  - [Bizuns - Default Passwords List](https://bizuns.com/default-passwords-list)
  - [SecLists - Default Passwords CSV](https://github.com/danielmiessler/SecLists/blob/master/Passwords/Default-Credentials/default-passwords.csv)
  - [WordList-Compendium](https://github.com/Dormidera/WordList-Compendium)
  - [CIRT.net - Passwords](https://www.cirt.net/passwords)
  - [Passwords Database](http://www.passwordsdatabase.com/)
  - [Many Passwords](https://many-passwords.github.io/)
  - [The Infocentric](https://theinfocentric.com/)

## Create your own Dictionaries
- Find as much information about the target as you can and generate a custom dictionary. Tools that may help:
  - Crunch
    ```bash
    crunch 4 6 0123456789ABCDEF -o crunch1.txt # From length 4 to 6 using that alphabet
    crunch 4 4 -f /usr/share/crunch/charset.lst mixalpha # Only length 4 using charset mixalpha (inside file charset.lst)
    ```
    - @ Lower case alpha characters
    - , Upper case alpha characters
    - % Numeric characters
    - ^ Special characters including space
    - crunch 6 8 -t ,@@^^%%

  - Cewl
    ```
    cewl example.com -m 5 -w words.txt
    ```

  - CUPP
    - Generate passwords based on your knowledge of the victim (names, dates...)
    ```
    python3 cupp.py -h
    ```

  - Wister
    - A wordlist generator tool that allows you to supply a set of words, giving you the possibility to craft multiple variations from the given words, creating a unique and ideal wordlist to use regarding a specific target.
    ```
    python3 wister.py -w jane doe 2022 summer madrid 1998 -c 1 2 3 4 5 -o wordlist.lst
    ```

```
 __          _______  _____ _______ ______ _____  
 \ \        / /_   _|/ ____|__   __|  ____|  __ \ 
  \ \  /\  / /  | | | (___    | |  | |__  | |__) |
   \ \/  \/ /   | |  \___ \   | |  |  __| |  _  / 
    \  /\  /   _| |_ ____) |  | |  | |____| | \ \ 
     \/  \/   |_____|_____/   |_|  |______|_|  \_\

      Version 1.0.3                    Cycurity    
      
Generating wordlist...
[########################################] 100%
Generated 67885 lines.

Finished in 0.920s.
```




___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: May 28th 2023 (02:49 am) 
Last Modified Date: May 28th 2023 (02:49 am)
