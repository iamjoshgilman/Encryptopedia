---
creation date: June 1st 2023
last modified date: June 1st 2023
aliases: []
tags: #🧰
---

Primary Categories: [[04 - Tools & Techniques]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #🧰  

# [[04 - PowerView]]  
___

## Description:


## Installation

The most up-to-date version of PowerView can be found in the dev branch of PowerSploit: [PowerView.ps1](https://github.com/PowerShellMafia/PowerSploit/blob/dev/Recon/PowerView.ps1)

| Verb | Description |
|---|---|
| Get | Retrieve full raw data sets |
| Find | 'Find' specific data entries in a data set |
| Add | Add a new object to a destination |
| Set | Modify a given object |
| Invoke | Lazy catch-all |

| Noun | Description |
|---|---|
| Verb-Domain* | Indicates that LDAP/.NET querying methods are being executed |
| Verb-WMI* | Indicates that WMI is being used under the hood to execute enumeration |
| Verb-Net* | Indicates that Win32 API access is being used under the hood |

| PowerShell Commands | Description |
|---|---|
| `Get-DomainGroup -MemberIdentity <User/Group>` | Get all the groups a user is effectively a member of, 'recursing up' using tokenGroups. |
| `Get-DomainGroupMember -Identity "Domain Admins" -Recurse` | Get all the effective members of a group, 'recursing down'. |
| `Get-DomainUser -Credential $Cred` | Use an alternate credential for any function. |
| `Get-DomainOU -GPLink '<GPP_GUID>'`<br>`| % {Get-DomainComputer -SearchBase $_.distinguishedname -Properties dnshostname}` | Retrieve all the computer DNS host names a GPP password applies to. |
| `Get-DomainUser -LDAPFilter "(pwdlastset<=$Date)"`<br>`-Properties samaccountname,pwdlastset` | Get all users with passwords changed > 1 year ago, returning SAM account names and password last set times. |
| `Get-DomainUser -LDAPFilter "(!userAccountControl:1.2.840.113556.1.4.803:=2)"`<br>`-Properties distinguishedname` | Get all enabled users, returning distinguished names. |
| `Get-DomainUser -UACFilter NOT_ACCOUNTDISABLE`<br>`-Properties distinguishedname` | Get all enabled users, returning distinguished names. |
| `Get-DomainUser -LDAPFilter "(userAccountControl:1.2.840.113556.1.4.803:=2)"` | Get all disabled users. |
| `Get-DomainUser -UACFilter ACCOUNTDISABLE` | Get all disabled users. |
| `Get-DomainUser -LDAPFilter "(useraccountcontrol:1.2.840.113556.1.4.803:=262144)"` | Get all users that require smart card authentication. |
| `Get-DomainUser -UACFilter SMARTCARD_REQUIRED` | Get all users that require smart card authentication. |
| `Get-DomainUser -LDAPFilter



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 1st 2023 (08:12 pm) 
Last Modified Date: June 1st 2023 (08:12 pm)
