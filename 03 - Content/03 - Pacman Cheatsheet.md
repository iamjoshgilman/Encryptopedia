---
creation date: February 18th 2023
last modified date: February 18th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Administration]] 
Secondary Categories: [[]] 
Links: [[Pacman]] - [[Archlinux]]
Search Tag: #📖  

# [[03 - Pacman Cheatsheet]]  

## Common commands

Install (and update system)

```shell
pacman -Syu <pkg>
```

Uninstall package

```shell
pacman -Rsc <pkg>
```

Search

```shell
pacman -Ss <keywords>
```


## Query

List explictly-installed packages

```shell
pacman -Qe
```


What files does this package have?
```shell
pacman -Ql <pkg>
```

List information on package

```shell
pacman -Qii <pkg>
```

Search installed packages for keywords

```shell
pacman -Qs <query>
```

## Orphans

List unneeded packages

```shell
pacman -Qdt
```

Uninstall unneeded packages

```shell
pacman -Rns $(pacman -Qdtq)
```

Avoid orphans by using `pacman -Rsc` to remove packages, which will remove unneeded dependencies.

___

## Resources:

| Hyperlink | Info |
| --------- | ---- |
| https://devhints.io/pacman | Pacman CheatSheet |


Created Date: February 18th 2023 (08:07 pm) 
Last Modified Date: February 18th 2023 (08:07 pm)
