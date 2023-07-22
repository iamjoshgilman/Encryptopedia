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

# [[03 - Preventative - Marking External Emails]]  
---

# Marking External Emails to Raise Awareness

To help employees understand the risks associated with external emails, organizations can implement rules in platforms like Microsoft Exchange or Office 365 to mark incoming external emails. By altering the subject line or body text, recipients can be alerted that the email is from an external source and potentially malicious. This simple warning can make employees think twice before interacting with the email, such as opening attachments or clicking on hyperlinks.

A common approach is to append a short message, such as "[EXTERNAL]" or "[EXT]," to the subject line of any email coming from an external sender into the organization. This marking serves as a visual indicator to remind employees that the email originates from outside the organization.

Here's an example walkthrough of setting up such a rule in Office 365:

1. Access the Exchange admin center.
2. Click on "Mail flow" in the left-hand menu.
3. Create a new rule by clicking the "+" icon and selecting "Create a new rule..."
4. Name the rule, such as "Received from scope Outside the organization."
5. Set the condition for the rule: If the sender is outside the organization (e.g., securityblue.team domain) and the recipient is inside the organization.
6. Define the action to be taken when the conditions are met: Prepend the subject of the message with "[EXTERNAL]".
7. Save the rule.

By implementing this rule, any external email delivered to the organization's mailbox will have the subject line marked with "[EXTERNAL]." This marking serves as a visual reminder to employees that the email is from an external source.

Organizations can also consider adding warning messages to the start of the email's body content or applying additional styling, such as using red text, to make the warning more prominent. This ensures that employees are more likely to read the warning and proceed with caution when encountering external emails.

Marking external emails helps raise awareness among employees and encourages them to exercise caution and follow security best practices when interacting with potentially malicious content.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 18th 2023 (04:02 pm) 
Last Modified Date: June 18th 2023 (04:02 pm)
