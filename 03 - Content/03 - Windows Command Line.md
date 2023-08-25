---
creation date: August 24th 2023
last modified date: August 24th 2023
aliases: []
tags: #📖
---

Primary Categories: [[000 - Global Index]] | [[01 - Administration]] 
Secondary Categories: [[02 - Windows]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Windows Command Line]]  

### 📌 Index
- [1. Changing Directory (cd)](#1-changing-directory-cd)
- [2. Changing Drives](#2-changing-drives)
- [3. Viewing Directory Contents](#3-viewing-directory-contents)
- [4. Common Commands](#Common-Commands)

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
## 4. Common Commands

| Command  | Usage                                    | Example                   | Additional Notes                                        |
|----------|------------------------------------------|---------------------------|---------------------------------------------------------|
| `mkdir`  | Create a new directory.                   | `mkdir new_dir`           | Can create nested directories in one go.                |
| `copy`   | Copy files from source to destination.    | `copy file1.txt file2.txt`| Cannot copy directories, only files.                     |
| `robocopy`| Robust file copy including directories.  | `robocopy source_dir dest_dir /s`| Use `/S` for non-empty directories, `/E` for all.  |
| `move`   | Move files or directories.                | `move source_dir dest_dir`| Can move both files and directories.                    |
| `del`    | Delete files.                             | `del file1.txt`           | Use `/P` to prompt before deleting, can't delete directories.|
| `rmdir`  | Remove directories.                       | `rmdir directory_name`    | Use `/S` to remove non-empty directories.                |
| `more`   | Display file content one page at a time.  | `dir \| more`             | Good for paging through large outputs.                   |
| `find`   | Search inside files for text.             | `find "hello"`            | Can use wildcards, `2>nul` to hide errors.               |
| `where`  | Locate files on the system.               | `where "file*.txt"`       | Use `/R` to search in a directory and its subdirectories, checks PATH by default.|



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 24th 2023 (08:17 pm) 
Last Modified Date: August 24th 2023 (08:17 pm)
