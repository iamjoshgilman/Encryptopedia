---
creation date: June 18th 2023
last modified date: June 18th 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Phishing Analysis]] | [[000 - Global Index]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Hyperlinks]]  
---

A hyperlink is a webpage URL that is embedded into text, a button, or an image. When clicked, it will open the recipient’s default browser, and navigate to the webpage for them.
- Hyperlinks are used when the attacker wants to direct the target to web resources, such as a malicious file download, a page with a fake login portal acting as a credential harvester, or other content as part of their phishing attack. 
- Hyperlinks can be coupled with additional techniques such as redirected targets to a typo squatted domain or using URL shortening services to disguise the true destination of the link.

## Example
- Looking at another PayPal-themed phishing email, we can see that the hyperlinked button definitely isn’t taking us to PayPal.com.
![[Pasted image 20230618132038.png]]

- Opening this email in a text editor, we can find the HTML body content, and identify where the hyperlink is. Below we will explain how hyperlinks actually work using HTML anchor tags.

![[Pasted image 20230618132329.png]]

- If we wanted to use HTML to hyperlink the word Google to Google.com, we could use the following HTML code:

`<p> Need to access Google? <a href="https://www.google.com"> Just click this text! </a></p>`
	- `<p>` Paragraph tag declares that we want to print text to the screen.
	- **“Need to access Google?”** Non-hyperlinked text.
	- `<a href=”www.google.com”>` Anchor tag used to hyperlink anything between the opening anchor tag and the closing tag </a>, and states the address to link.
	- “**Just click this text!**” Hyperlinked text.
	- `</a>` Closes the hyperlink.
	- `</p>` Closes the paragraph.





___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 18th 2023 (01:14 pm) 
Last Modified Date: June 18th 2023 (01:14 pm)
