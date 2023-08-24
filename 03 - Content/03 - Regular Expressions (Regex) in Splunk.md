---
creation date: June 23rd 2023
last modified date: June 23rd 2023
aliases: []
tags: #📖
---

Primary Categories: [[02 - Splunk]] | [[000 - Global Index]]
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Regular Expressions (Regex) in Splunk]]  
---

### Basic Regex Symbols

|Symbol|Meaning|
|---|---|
|`.`|Matches any single character (except newline `\n`).|
|`^`|Matches the start of the string.|
|`$`|Matches the end of the string.|
|`*`|Matches 0 or more repetitions of the preceding character or group.|
|`+`|Matches 1 or more repetitions of the preceding character or group.|
|`?`|Matches 0 or 1 repetitions of the preceding character or group.|
|`[abc]`|Matches any of the characters `a`, `b`, or `c`.|
|`[^abc]`|Matches any character except `a`, `b`, or `c`.|
|`(abc)`|Defines a group that matches the string `abc`.|
|`(a\|b)`|Matches `a` or `b`.|
|`\d`|Matches any decimal digit; equivalent to `[0-9]`.|
|`\D`|Matches any non-digit character; equivalent to `[^0-9]`.|
|`\s`|Matches any whitespace character (spaces, tabs, line breaks).|
|`\S`|Matches any non-whitespace character.|
|`\w`|Matches any alphanumeric character (letters and numbers) or underscore (`_`); equivalent to `[a-zA-Z0-9_]`.|
|`\W`|Matches any non-word character; equivalent to `[^a-zA-Z0-9_]`.|
|`(?<name>...)`|Defines a named group that can be referred to by `name`.|

### Splunk Commands

|Command|Description|
|---|---|
|`rex field=_raw "expression"`|Extracts data from a field using regular expressions.|
|`rex field=fieldName "expression"`|Extracts data from a specific field using regular expressions.|

### Practical Examples

#### Usernames

Usernames often consist of alphanumeric characters. The `\w` character class is perfect for this.

- Regex: `(?<username>\w+)`
- Splunk command: `rex field=_raw "username=(?<username>\w+)"`

#### Passwords

Passwords can contain a mix of alphanumeric and special characters. To capture passwords you might use a regex that captures one or more non-whitespace characters.

- Regex: `(?<password>[^\s]+)`
- Splunk command: `rex field=_raw "password=(?<password>[^\s]+)"`

#### Filenames

Files often have a name, followed by a dot, then an extension. You might use a regex that captures this pattern.

- Regex: `(?<filename>\w+\.\w+)`
- Splunk command: `rex field=_raw "filename=(?<filename>\w+\.\w+)"`

#### IP Addresses

An IP address is four numbers (0-255) separated by dots. The following regex can be used to capture these.

- Regex: `(?<ipaddress>\b\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}\b)`
- Splunk command: `rex field=_raw "ipaddress=(?<ipaddress>\b\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}\b)"`


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 23rd 2023 (05:19 pm) 
Last Modified Date: June 23rd 2023 (05:19 pm)
