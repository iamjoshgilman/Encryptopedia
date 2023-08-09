---
creation date: August 8th 2023
last modified date: August 8th 2023
aliases: []
tags: #📖
---

Primary Categories: [[]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - HTML Applications (HTA) - Wrapped Payloads, Scripted Delivery, & WMI]]  

# Introduction

On the subject of scripted malware delivery mechanisms, let’s examine a curious class of malware called the **HTML Application (HTA) file**. HTAs are commonly used as the payload of phishing attacks. By the end of this section, you’ll see why this is the case.

Locate and extract the sample located at **PMAT-labs/labs/3-3.OffScript-ScriptMalware/HTA/Dropper.hta.7z** an let’s get going!

# The Offensive Potential of HTML

It is no secret that HTML can be weaponized. Every time you visit a website, your web browser downloads and renders the code that is served out by that website. Your browser is really just an interpreter for the technologies that power the web: **HTML, CSS,** and **JavaScript.**

HTML provides the structure of the website. CSS applies color, fonts, presentation, and layouts of the website. And JavaScript can dynamically control behavior of elements of the website.

It’s that last one that we need to watch out for.

## JavaScript Is Dangerous

You may be familiar with the classic Cross-Site Scripting test that pops an alert box by injecting the `<script>` block into an HTML page. If you’ve seen this test before, you may have wondered “what is actually going on when this happens?”

![](https://cdn.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/https://www.filepicker.io/api/file/utmUIMIwSFpFrha4V6dC)

HTML pages can define the `<script>` tag to include code that can run different scripting languages. In most cases, the language is JavaScript. JavaScript can execute code within the browser to move components around on the page, change colors and fonts, pop that alert box, and do many other functions. Think of JavaScript as the programmatic engine of HTML.

The [W3 Schools demo for JavaScript’s alert() box method](https://www.w3schools.com/jsref/met_win_alert.asp) demonstrates this well.

Try saving this code to `index.html` and running it locally by opening it in a web browser:

<html>
<body>

<h1>The Window Object</h1>
<h2>The alert() Method</h2>

<p>Click the button to display an alert box.</p>

<button onclick="myFunction()">Try it</button>

<script>
function myFunction() {
  alert("Hello! I am an alert box!");
}
</script>

</body>
</html>

The takeaway here is that **JavaScript executes code within the browser.** But when JavaScript executes within a web browser, the code execution is confined to the web browser itself. That is to say, the code runs in the context of the browser, manipulates the document model of the web page, and can manipulate cookies, but can’t reach the operating system of the host unless there is some kind of browser based code execution vulnerability.

When used in an offensive capacity, JavaScript can perform activities like hooking the client’s browser (see the [BeEF Framework](https://beefproject.com/) for an example of this) and downloading files via [HTML Smuggling](https://attack.mitre.org/techniques/T1027/006/). The offensive potential of JavaScript is apparent, but if it’s usually limited to the browser of the victim, then that doesn’t sound so bad, right?

Wrong!

### Enter, HTML Applications

Imagine that a developer needs to design a compact, portable HTML site that can be easily sent to anyone who needs it. Maybe it’s a company survey. Maybe it’s a presentation of some sort. The developer can create an HTML Application (HTA) file for this purpose.

HTAs are Windows-executable, packaged HTML files that run HTML, CSS, and Windows native scripting languages from a single file outside of the context of the web browser. The last part of that sentence is the really scary thing here: **HTAs do not run in the context of the Windows web browser, but instead run as a trusted application on the operating system.**

An HTML Application is not much different from a normal HTML page in terms of construction. In fact, you can use the exact same code from an HTML page to make an HTA.

Try it out yourself — take the W3 Schools code for the JavaScript alert() method that we just used, open a new text file, write that HTML code into the file, and save it as `test.hta` on your FLARE-VM host. Then, double click on the file:

![](https://cdn.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/https://www.filepicker.io/api/file/9awo3NI2TvOrgCIPCzaV)

The window that spawns is a self contained Windows application that renders and runs the HTML, CSS, and/or scripting code that is packaged inside of it. If we click on the Try it button, we see that this application can execute the embedded JavaScript code:

![](https://cdn.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/https://www.filepicker.io/api/file/VIjJOOqSvWIazLmda9kg)

The scripting languages we can use here are not limited to JavaScript (or JScript in the context of Windows). We can embed any Windows-native scripting language inside of an HTA and it will execute the provided code. This includes JavaScript/JScript, VBScript, and both together in the same file.

In the previous section, we saw how VBScript can be weaponized. So the thought of a self contained HTML application that can execute code dynamically and have it run on the operating system of the victim should spark our concern.

## Analyzing HTAs

Let’s examine a weaponized HTA and unravel its functionality to demonstrate how to analyze these files.

The sample in the **PMAT-labs/labs/3-3.OffScript-ScriptMalware/HTA/Dropper.hta.7z** archive is called `Dropper.hta.malz`. Let’s rename this to `Dropper.hta`. When we do this, notice that Windows changes the file icon to an application icon:

![](https://cdn.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/https://www.filepicker.io/api/file/sXUt59vcQoqK80APP8z6)

### Static Analysis

Recall that an HTA is still, under the hood, HTML in a single file. Let’s open this file in Visual Studio Code to examine the HTML located within it:

```html
<html>
<head>
<title></title>
<body>
<script language="JavaScript" type="text/javascript">
document.write(unescape('%3c%68%74%6d%6c....[snip]......'));
</script>
</body>
</html>
```

Take note of the contents of this file. The actual HTML of the application is barren but has one notable feature. The `<script>` tag wraps a call to the JavaScript `document.write()` method. This call to `document.write()` has a block of characters that are delimited by percent signs inside of the `unescape()` method. Let’s examine both methods to identify what they do:

- `document.write()`: The `write()` method writes directly to an open (HTML) document stream.
- `unescape():` The `**unescape()**` function computes a new string in which hexadecimal escape sequences are replaced with the characters that they represent.

Immediately, we have an idea of what’s going on here:

- The block of characters inside the `unescape()` method is a bunch of hexadecimal bytes that are interpreted and replaced by the character that they represent.
- Then, the interpreted characters are written to the document of the page.

We can decode the block of hex characters in CyberChef by using the `From Hex` item and delimiting by percent sign. FLARE-VM installs a local instance of CyberChef in the C:\Tools\cyberchef directory. An online instance of CyberChef is also running at the following link:

[CyberChef](https://gchq.github.io/CyberChef/)

Using CyberChef, we add the `From Hex` decoder and change the delimiter to `Percent`. Then, we copy the block of hex bytes into the Input section:

![](https://cdn.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/https://www.filepicker.io/api/file/UV5gAirPTuO0br9zW8Kj)

The Output section now contains the following:

![](https://cdn.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/https://www.filepicker.io/api/file/3gHEtgtxSkOah1adNfFH)

Several things are concerning about this!

When the HTA is executed, it decodes and writes this HTML to the page. This block of HTML contains another script block that invokes VBScript to run code. But what does the code do?

### Invoking WMI & Executing PowerShell

The VBScript code starts by setting up the required parameters to invoke Windows Management Instrumentation (WMI) to execute a process. WMI is a part of the Windows operating system that acts as an interface for management purposes. It is extremely powerful and complicated and most of its functionality is outside the scope of this course, but it can do a few things that make it relevant for malware analysis.

WMI can start and run processes through the Win32_Process namespace. Effectively, this means that anything that can access WMI can execute a process.

In our sample, the VBScript code is setting WMI up to be able to execute a process:

![](https://cdn.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/https://www.filepicker.io/api/file/pEgx5vrtRYSONgRFjDN4)

The VBScript then performs the following:

![](https://cdn.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/https://www.filepicker.io/api/file/ulRL40IRWbK16Jbr9U4A)

This line executes a process through the WMI service and returns the results to the `Error` variable.

The process argument here runs a command shell which, in turn, runs PowerShell in a hidden window. When PowerShell is executed, it performs the following:

![](https://cdn.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/https://www.filepicker.io/api/file/phgcpMtQd2r3xAduvKEu)  

The VBScript then calls `window.close()` to close out of the HTA window.

If we take a step back, we now have a clear idea of the execution chain here:

- HTA is opened and runs the embedded JavaScript.
- The JavaScript decodes the hex bytes of an inner HTML document and writes it into the HTA.
- The inner HTML document invokes VBScript to execute WMI.
- WMI runs a process to call a command shell.
- The command shell, in turn, runs PowerShell in a hidden window.
- PowerShell runs a download cradle command to reach out to `[http://tailofawhale.local/TellAndSentFor.exe](http://tailofawhale.local/TellAndSentFor.exe)`, write it to the %temp% directory as `jLoader.exe` and then execute `jLoader.exe`.

With a good understanding of the payload, let’s move onto dynamic analysis to see it in action!

### Dynamic Analysis

When we open the HTA program, a window flashes for a moment and then disappears. If we are running INetSim at the time of detonation, we see the default INetSim binary spawn. Take note of the location where the binary is running from:

![](https://cdn.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/https://www.filepicker.io/api/file/MlXLcQEOSKHhv8c79w7d)

Dropper.hta has clearly succeeded in downloading and executing something. Let’s examine the network signatures.

In WireShark, we see the outbound DNS request for `tailofawhale.local` and its DNS resolution:

![](https://cdn.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/https://www.filepicker.io/api/file/sUoloX1OTJOjxQjg0KCe)

We can also see the HTTP request to the malicious domain and response in Wireshark:

![](https://cdn.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/https://www.filepicker.io/api/file/CQmEvkyNTr2PfVM43ksK)

If we go to examine host-based indicators, we run into a small snag. There is no process called “Dropper.hta” anywhere in the list of running processes on the host. Where does this process execute?

HTAs do not execute directly. When double-clicked, they are passed to the native Windows binary `mshta.exe` which executes them on its behalf. `mshta.exe` acts as an HTML interpreter and loads the HTML from the HTA along with any DLLs that deal with script execution and then executes the program all at once.

If we look in the Procmon process tree after detonation, we see an invocation of `mshta.exe` that takes the path to our HTA sample as its argument:

![](https://cdn.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/https://www.filepicker.io/api/file/VWSy84OfSbWrWqn7qIix)

![](https://cdn.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/https://www.filepicker.io/api/file/uC8LXt1rQkeGaHcqbodw)

We’ve accounted for the execution of the HTA, but we haven’t accounted for the other parts of the payload yet. Where is the call to PowerShell and the command shell?

Higher up in the process list, there is an instance of `svchost.exe` that is executing a process called `wmiprvse.exe`. This is the way that Windows invokes WMI to execute processes:

![](https://cdn.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/https://www.filepicker.io/api/file/RFd8DRgDRYSgdxFvUm5x)

We can follow the `wmiprvse.exe` process all the way down through the call to PowerShell and, eventually, the execution of the `jLoader.exe` program. In this case, this was our INetSim default binary that spawned the message box, but in real life this is likely a second stage payload.

After annotating these details, we have effectively analyzed the HTA dropper sample.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 8th 2023 (08:33 am) 
Last Modified Date: August 8th 2023 (08:33 am)
