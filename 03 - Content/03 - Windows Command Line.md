---
creation date: August 24th 2023
last modified date: August 24th 2023
aliases: []
tags: #📖
---

Primary Categories: [[]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Windows Command Line]]  

### 📌 Index
- [1. Changing Directory (cd)](#1-changing-directory-cd)
- [2. Changing Drives](#2-changing-drives)
- [3. Viewing Directory Contents](#3-viewing-directory-contents)

---
### 1. Changing Directory (cd)
The `cd` command is used to change directories (move between folders). 

- To navigate to the root of the file system: 
    ```shell
    cd \
    ```

**Tips:**
- Use **tab completion** for directory names to ease typing.
- Command Prompt is **not case sensitive**: `CD`, `cd`, and `Cd` are all valid.

**Example:**
```
C:\Users\User\Documents>cd \
C:\>
```

---
### 2. Changing Drives
To switch between available drives on your machine:

- Input the drive letter followed by `:`. 
  ```shell
  d:
  ```

- If you know the directory on the new drive, navigate straight to it using `cd` with the `/D` switch. 
  ```shell
  cd /D C:\Windows
  ```

**Example:**
```
C:\Users\User\Documents>D:
D:\>
```
```
D:\>cd /D C:\Windows
C:\Windows>
```

---

### 3. Viewing Directory Contents
The `dir` command displays files and directories in the current directory, showing details like modification date, time, and file size.

- Basic use:
  ```shell
  dir
  ```

**Details:**
- By default, `dir` does not display hidden files and folders.
- To display hidden files/folders, use the `/A` switch.
  ```shell
  dir /A
  ```

**Example Output:**
```
C:\Users\User\Demo>dir
Volume in drive C has no label.
...
Directory of C:\Users\User\Demo
...
```

---




___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 24th 2023 (08:17 pm) 
Last Modified Date: August 24th 2023 (08:17 pm)
