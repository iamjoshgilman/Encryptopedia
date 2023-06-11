---
creation date: April 5th 2023
last modified date: April 5th 2023
aliases: []
tags: #📖
---

Primary Categories: [[02 - Linux]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[[03 - Linux Permissions Cheatsheet]]  

# Linux Permissions Cheat Sheet

| Permission | Octal Value | Description                               |
|------------|-------------|-------------------------------------------|
| ---        | 0           | No permissions                            |
| --x        | 1           | Execute only                              |
| -w-        | 2           | Write only                                |
| -wx        | 3           | Write and execute                         |
| r--        | 4           | Read only                                 |
| r-x        | 5           | Read and execute                          |
| rw-        | 6           | Read and write                            |
| rwx        | 7           | Read, write, and execute                  |
ch
## Usage

- To set permissions using octal values:
  ```chmod <permissions> <file/directory>```

  Example: ```chmod 755 myfile.txt```

- To set permissions for user (u), group (g), and others (o) separately:
  ```chmod u=<permissions>,g=<permissions>,o=<permissions> <file/directory>```

  Example: ```chmod u=rwx,g=rx,o=r myfile.txt```

- To add (+) or remove (-) specific permissions:
  ```chmod <who><operator><permissions> <file/directory>```

  Example: ```chmod u+x myfile.txt``` (Add execute permission for user)

## Recursive Permissions

- To set permissions recursively for directories and their contents:
  ```chmod -R <permissions> <directory>```

  Example: ```chmod -R 755 mydir```




___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: April 5th 2023 (08:00 pm) 
Last Modified Date: April 5th 2023 (08:00 pm)
