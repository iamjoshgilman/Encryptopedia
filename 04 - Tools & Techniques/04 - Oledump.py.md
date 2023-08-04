---
creation date: August 3rd 2023
last modified date: August 3rd 2023
aliases: []
tags: #🧰
---

Primary Categories: [[01 - Malware Analysis]] | [[000 - Cybersecurity Materials]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #🧰  

# [[04 - Oledump.py]]  
___

`oledump.py` is a Python tool developed by Didier Stevens. It's used for analyzing OLE files, which are often used by Microsoft Office to store documents. Malware authors frequently use these formats to deliver malware, so `oledump.py` can be a handy tool for examining suspicious Office files.

## Installation

`oledump.py` is a Python 2 script, but it's compatible with Python 3 as well. You can download it directly from [Didier Stevens's GitHub repository](https://github.com/DidierStevens/DidierStevensSuite/blob/master/oledump.py). 

Python and necessary dependencies (like `olefile`) should be installed first:

```bash
pip install olefile
```

Then, you can run the tool using Python:

```bash
python oledump.py <filename>
```

## Usage

Here are some common usages:

1. **List the streams in an OLE file**: Simply providing a file name to `oledump.py` will list the streams inside that file. It can help identify potential macros or other embedded data.
   
   ```bash
   python oledump.py document.doc
   ```

2. **Extract a stream from the file**: The `-s` option followed by the index of the stream will select that stream for further processing. The `-d` option will dump the content of that stream to stdout.

   ```bash
   python oledump.py -s <index> -d document.doc
   ```

3. **Decompress VBA macros**: The `-v` option decompresses the VBA macros and makes them easier to read.

   ```bash
   python oledump.py -v document.doc
   ```

4. **Detect Auto-executable Macros**: The `-a` option can be used to detect auto-executable macros (i.e., macros that will run automatically when the document is opened).
   
   ```bash
   python oledump.py -a document.doc
   ```

5. **Finding Strings in a Stream**: If you've found a stream that seems interesting and you'd like to extract human-readable strings from it, you can use the `-S` option to perform a strings operation on the selected stream:

   ```bash
   python oledump.py -s <index> -S document.doc
   ```

6. **Decompressing Corrupt VBA Macros**: Sometimes, the VBA macros might be compressed in a way that appears to be corrupt. The `-v` option normally decompresses VBA macros, but if it encounters what it thinks is corruption, it will stop. If you think the macros aren't actually corrupt, you can use the `--vbadecompresscorrupt` option to force decompression:

   ```bash
   python oledump.py -s <index> --vbadecompresscorrupt document.doc
   ```

7. **Applying a YARA Rule**: You can use `oledump.py` to apply a YARA rule to a document by using the `-y` option followed by the path to your rule:

   ```bash
   python oledump.py -y my_yara_rule.yara document.doc
   ```

8. **Selecting Multiple Streams**: If you're interested in more than one stream, you can select multiple by separating the stream indices with a `/`:

   ```bash
   python oledump.py -s <index1>/<index2> -d document.doc
   ```

9. **Creating an Analysis Report**: `oledump.py` has a built-in plug-in system. For example, the `plugin_http_heuristics` plugin can help identify URLs in a document by using `-p plugin_http_heuristics`:

   ```bash
   python oledump.py -p plugin_http_heuristics document.doc
   ```

## Example 

Assume we have a suspicious file named `suspicious.doc`.

1. **List the streams in the file**:

```bash
python oledump.py suspicious.doc
```

The output might look something like this:

```yaml
1:       114 '\x01CompObj'
2:      4096 '\x05DocumentSummaryInformation'
3:      4096 '\x05SummaryInformation'
4:       144 '1Table'
5:      7593 'Macros/PROJECT'
6:       108 'Macros/PROJECTwm'
7: M    4139 'Macros/VBA/Module1', vbaProject
8: M    5939 'Macros/VBA/ThisDocument', vbaProject
9:      2823 'Macros/VBA/_VBA_PROJECT'
10:     1912 'Macros/VBA/dir'
11:       97 'WordDocument'
```

Here, we can see that streams 7 and 8 are marked with `M`, which indicates they contain VBA macros.

2. **Extract and decompress the VBA macros**:

Now, let's dump and decompress the VBA macros from stream 7:

```bash
python oledump.py -s 7 -v suspicious.doc
```

This will output the VBA code for us to analyze. We might see something like this:

```vba
Sub autoopen()
    Call Document_Open
End Sub
```

This VBA script indicates that when the document is opened (`autoopen`), it runs another function `Document_Open`. This is often a sign of malicious activity.

3. **Investigate auto-executable macros**:

Using the `-a` option, we can verify if there are auto-executable macros:

```bash
python oledump.py -a suspicious.doc
```

If the document contains auto-executable macros, this command will highlight those streams.

From this point, we would need to examine the VBA code more thoroughly, possibly using additional tools or methods, depending on what the code does. This might include looking for obfuscated strings, shellcode, suspicious API calls, network communication, file operations, and so on.







___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 3rd 2023 (08:47 pm) 
Last Modified Date: August 3rd 2023 (08:47 pm)
