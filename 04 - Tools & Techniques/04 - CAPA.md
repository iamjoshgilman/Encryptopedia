---
creation date: July 23rd 2023
last modified date: July 23rd 2023
aliases: []
tags: #🧰
---

Primary Categories: [[]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #🧰  

# [[04 - CAPA]]  
___

Our goal during basic static analysis is to triage correctly and as quickly as possible. Now that we've learned a bit about how to perform basic static analysis and how to correlate static indicators, let's deploy another tool that can assist in this phase and hopefully speed things up.

Introducing, Capa: [https://github.com/mandiant/capa](https://github.com/mandiant/capa)

![](https://cdn.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/https://www.filepicker.io/api/file/JVQItNYhQmivzBdVLZcp)

**Capa** is a program that detects malicious capabilities in suspicious programs by using a set of rules. These rules are meant to be as high-level and human readable as possible. For example, Capa will examine a binary, identify an API call or string of interest, and match this piece of information against a rule that is called "receive data" or "connect to a URL". It translates the technical information in a binary into a simple, human-readable piece of information.

The program's primary strength is how it leverages rules. Capa has a default rule set, but also has an open-source repository of rules where anyone can contribute. You can see the Capa rule repository here: [https://github.com/mandiant/capa-rules](https://github.com/mandiant/capa-rules)

Let's learn more about this tool by using it on the binary we've already performed static analysis on, **Malware.Unknown.exe.malz.**

On FLAREVM, run `capa -h` to see the usage menu:

```bash
C:\Users\husky\Desktop
λ capa -h
usage: capa.exe [-h] [--version] [-v] [-vv] [-d] [-q] [--color {auto,always,never}] [-f {auto,pe,sc32,sc64,freeze}] [-b {vivisect,smda}] [-r RULES] [-t TAG] [-j] sample

The FLARE team's open-source tool to identify capabilities in executable files.

positional arguments:
  sample                path to sample to analyze

optional arguments:
  -h, --help            show this help message and exit
  --version             show program's version number and exit
  -v, --verbose         enable verbose result document (no effect with --json)
  -vv, --vverbose       enable very verbose result document (no effect with --json)
  -d, --debug           enable debugging output on STDERR
  -q, --quiet           disable all output but errors
  --color {auto,always,never}
                        enable ANSI color codes in results, default: only during interactive session
  -f {auto,pe,sc32,sc64,freeze}, --format {auto,pe,sc32,sc64,freeze}
                        select sample format, auto: (default) detect file type automatically, pe: Windows PE file, sc32: 32-bit shellcode, sc64: 64-bit shellcode, freeze: features previously frozen by capa
  -b {vivisect,smda}, --backend {vivisect,smda}
                        select the backend to use
  -r RULES, --rules RULES
                        path to rule file or directory, use embedded rules by default
  -t TAG, --tag TAG     filter on rule meta field values
  -j, --json            emit JSON instead of text

By default, capa uses a default set of embedded rules.
You can see the rule set here:
  <https://github.com/fireeye/capa-rules>

To provide your own rule set, use the `-r` flag:
  capa  --rules /path/to/rules  suspicious.exe
  capa  -r      /path/to/rules  suspicious.exe

examples:
  identify capabilities in a binary
    capa suspicious.exe

  identify capabilities in 32-bit shellcode, see `-f` for all supported formats
    capa -f sc32 shellcode.bin

  report match locations
    capa -v suspicious.exe

  report all feature match details
    capa -vv suspicious.exe

  filter rules by meta fields, e.g. rule name or namespace
    capa -t "create TCP socket" suspicious.exe
```

**Note:** if Capa is not installed and accessible by running `capa` from the command line, please install the release binary for the program located at [https://github.com/mandiant/capa/releases/tag/v4.0.1](https://github.com/mandiant/capa/releases/tag/v4.0.1)

Capa has lots of command line options, but let's run it against Malware.Unknown.exe.malz with no arguments to see what the program looks like by default.

Run `capa [C:\path\to\Malware.Unknown.exe.malz]` to execute the program. Because I am in the Desktop directory, the command is `capa Malware.Unknown.exe.malz` in my example below:

![](https://cdn.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/https://www.filepicker.io/api/file/O0uF7m1iSU68OHjtQz1r)

Let's examine the results. Immediately, we see some boiler-plate information about the binary, like its hashes. But then, we get some interesting high-level information about the program.

The first block in the output labeled "ATT&CK Tactic - ATT&CK Technique" is worth examining in depth.

![](https://cdn.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/https://www.filepicker.io/api/file/KvMxudm5SKGaLXT19Gbz)![](https://cdn.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/https://www.filepicker.io/api/file/KvMxudm5SKGaLXT19Gbz)

What is ATT&CK?

## **MITRE Adversary Tactics, Techniques & Common Knowledge (ATT&CK)**

![](https://cdn.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/https://www.filepicker.io/api/file/wPkhR2W3RRa4jxF0hGC4)

  

[https://attack.mitre.org/](https://attack.mitre.org/)

The MITRE ATT&CK Framework is a standard knowledge base of adversary tactics, techniques, and procedures (TTPs). MITRE ATT&CK seeks to define and classify cyber adversary activity into groups based on what the activity seeks to accomplish and how the activity is carried out.

In my professional life, no other standard set of definitions has seen more use than MITRE ATT&CK. It is an industry standard just about everywhere you go.

For example, let's say you want high-level information about the types of tactics that adversaries use to gain initial access to a target network. The MITRE ATT&CK Framework has a grouped list of items classified under TA0001 - Initial Access, that you can view in list form:

[https://attack.mitre.org/tactics/TA0001/](https://attack.mitre.org/tactics/TA0001)

Then, if you want more information about a specific initial access technique, like phishing, you can view the technique page for T1566 - Phishing:

[https://attack.mitre.org/techniques/T1566/](https://attack.mitre.org/techniques/T1566)

And then, if you want an example of a more specific sub-technique of phishing, like spearphishing with an attachment, you can view the subtechnique T1566.001 - Spearphisning Attachment:

[https://attack.mitre.org/techniques/T1566/001/](https://attack.mitre.org/techniques/T1566/001)

The pages in the ATT&CK matrix have information about the specific tactic/technique, tools that can deploy this technique, mitigations, and detections. For example, T1566.001 - Spearphishing Attachments lists the known adversary groups that use this technique (which, for Spearphishing, is probably most adversaries!):

![](https://cdn.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/https://www.filepicker.io/api/file/qi7FKFTfqrzthgOdQs1g)

I highly recommend perusing the MITRE ATT&CK matrix items. I can get lost in that website for hours learning about new tactics, techniques, and procedures. I also highly recommend becoming fluent in the ATT&CK framework for report writing as it can be an exceptionally useful way to frame findings and information in industry common terms.

## Capa Output

Now, back to Capa! Capa has examined the binary, pulled out interesting information from the binary, matched it against its default rule set, and matched some suspected capabilities to items from the MITRE ATT&CK Framework. This time, we don't have much to go on. We get a match for the ATT&CK item "T1129 - Shared Modules".

If we examine the matrix item for Shared Modules, we don't get a lot of useful information:

[https://attack.mitre.org/techniques/T1129/](https://attack.mitre.org/techniques/T1129)

> Adversaries may execute malicious payloads via loading shared modules. The Windows module loader can be instructed to load DLLs from arbitrary local paths and arbitrary Universal Naming Convention (UNC) network paths. This functionality resides in NTDLL.dll and is part of the Windows [Native API](https://attack.mitre.org/techniques/T1106) which is called from functions like `CreateProcess`, `LoadLibrary`, etc. of the Win32 API.

This basically means that the malware is loading DLLs to perform malicious activity. That's not particularly revealing! Let's keep moving.

_Instructor's Note: it seems that the Shared Modules technique wasn't too useful at all and the Capa developers have removed the default rule for it! If you run Capa against this sample, there's a chance you will not see this as a listed technique. It's not particularly useful for our analysis, so please feel free to move on to the next section._

_If you want to see an example of how Capa can identify techniques, also feel free to run Capa against the WannaCry sample that we detonated earlier in the course._

### Malware Behavioral Catalog (MBC)

The next output is the Malware Behavioral Catalog (MBC) Objectives and Behaviors. This is a similar classification system to MITRE ATT&CK but focuses on malware specifically.

The full MBC Matrix can be found here: [https://github.com/MBCProject/mbc-markdown#malware-objective-descriptions](https://github.com/MBCProject/mbc-markdown#malware-objective-descriptions)

MBC translates MITRE ATT&CK items into terms that focus on the malware analysis use case. So understandably, we do get some useful output from this section:

![](https://cdn.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/https://www.filepicker.io/api/file/JgUVBPgQdSUswZv0fbjw)

Here, Capa has identified items of interest in the binary, matched them to rules based on MBC items, and returned the results. We've accurately identified that the Malware.Unknown.exe.malz sample has the capability to

- Send and receive data
- Do so over HTTP
- Create and terminate processes

For a preliminary round of triage, that's pretty good! But let's keep going; the best is yet to come.

### Capa Rule Output

The final block identifies Capa rule matches against the default Capa rule set. This is the most specific of the three outputs and gives us the best information for triage:

![](https://cdn.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/https://www.filepicker.io/api/file/YyaBwcaQ3GHWvDp2QoUX)

Like in the MBC output, the Capa rule output identifies that the malware can connect to a URL, send and receive data, and manipulate processes. At surface, there isn't much more information here than what we already have. But we do see the number of matches and the namespace for the rules in this output.

Is there more going on under the hood of Capa? Yes, yes there is!

Let's rerun Capa with the verbose flag. Run capa [C:\path\to\Malware.Unknown.exe.malz] -v and examine the output:

![](https://cdn.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/https://www.filepicker.io/api/file/oCwzSNdTwKYxXisdiDZw)

There's a lot more output here! Capa identifies the rule that is triggered for the binary, the type of rule, and even the **location in the binary where the rule is triggered in hex form**! We can start to see the mechanism here for how Capa identifies things that trigger the rules - it uses the [Vivisect](https://github.com/vivisect/vivisect) parser to examine interesting strings and byte patterns and matches them against the rules.

Finally, let's run Capa one more time with a double verbose output. Run capa [C:\path\to\Malware.Unknown.exe.malz] -vv and examine the output:

![](https://cdn.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/https://www.filepicker.io/api/file/ZlpNotMxQVa1U5gcz8qT)

There is tons of incredible information here and we can clearly see how Capa is now triggering the rules for this binary. For example:

download URL to file
namespace  communication/http/client
author     matthew.williams@fireeye.com
scope      function
mbc        Communication::HTTP Communication::Download URL [C0002.006]
examples   F5C93AC768C8206E87544DDD76B3277C:0x100020F0, Practical Malware Analysis Lab 20-01.exe_:0x401040
function @ 0x401080
  or:
    api: urlmon.URLDownloadToFile @ 0x4010D9

The output for the "download URL to file" rule indicates that this rule triggers when the `urlmon.URLDownloadToFile` API call is located in the binary. It has identified this API call, provides the location in the binary where it is called, and provides some examples of where this kind of malware behavior has been seen before.

Notice that for some rules, there are conditionals that can trigger the rule based on multiple criteria. For example:

create process (2 matches)
namespace  host-interaction/process/create
author     moritz.raabe@fireeye.com
scope      basic block
mbc        Process::Create Process [C0017]
examples   9324D1A8AE37A36AE560C37448C9705A:0x406DB0, Practical Malware Analysis Lab 01-04.exe_:0x4011FC
basic block @ 0x4010E3
  or:
    api: shell32.ShellExecute @ 0x401128
basic block @ 0x401142
  or:
    api: kernel32.CreateProcess @ 0x4011AD

This rule identifies process creation based on the existence of the `ShellExecute` API call located in `shell32.dll` or the `CreateProcess` API call located in `kernel32.dll`.

The documentation on Capa rule generation is located here: [https://github.com/mandiant/capa-rules/blob/master/doc/format.md](https://github.com/mandiant/capa-rules/blob/master/doc/format.md#yaml)

## Summary

Now that we understand the specifics of basic static analysis, we can turn to a tool like Capa to do a lot of the heavy lifting for us during triage. Capa can give us high-level information about what may be going on in the sample of interest. It's usually never enough information to draw a definitive conclusion, but it's a start! More analysis is necessary to uncover the ground truth for any given sample.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: July 23rd 2023 (02:23 pm) 
Last Modified Date: July 23rd 2023 (02:23 pm)
