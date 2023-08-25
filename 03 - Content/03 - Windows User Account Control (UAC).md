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

# [[03 - Windows User Account Control (UAC)]]  

___
# Introduction
- **User Account Control (UAC)** enhances security in the Windows Operating System.
- It operates via 'tokens' assigned to users during login.
- All users initially receive a standard token granting limited access.

## Working of UAC
1. **Administrative Token**:
   - When system changes are initiated, administrators see a dimmed screen and a UAC prompt.
   - Acceptance of the prompt releases the administrative token, granting full privileges.
   - The token and its permissions are temporary and expire once the task is completed.
## UAC Prompts
1. **For Administrators**:
   - Prompt Title: "Do you want to allow this app to make changes to your device?"
   - Information: Application name (e.g., Windows PowerShell) and publisher (e.g., Microsoft Windows).
   - Actions: Links to view more details and the "Yes" or "No" response buttons.

2. **For Standard Users**:
   - Displays the same prompt as for administrators.
   - Additionally, requires input of an admin username and password.
   - This step is necessary as standard users lack the administrative token.
## UAC Levels
Adjusting UAC sensitivity is possible. To access UAC settings:

- Search "UAC" in the start menu.
- Choose "Change User Account Control Settings".
### UAC Settings Options:
1. **Always notify**:
   - UAC prompts appear for software installations, changes to the computer, and when altering Windows settings.
   - Desktop dims during a UAC prompt.

2. **Notify me only when apps try to make changes to my computer** (Default):
   - UAC prompts appear for software installations or "run as administrator" attempts.
   - Changes to Windows settings do not trigger a UAC prompt.
   - Desktop dims during a UAC prompt.

3. **Notify me only when apps try to make changes to my computer (do not dim my desktop)**:
   - Same as the previous setting, but the desktop remains undimmed during a UAC prompt.

4. **Never notify**:
   - UAC is essentially inactive.
   - Administrator requests are auto-approved.
   - Standard user requests are auto-denied.
   - No UAC prompt appears in either scenario.
## Key Takeaways
- **UAC** enhances security by controlling user access to high-privilege tasks.
- **Tokens** determine the access level for users, with an administrative token granting full rights.
- **UAC prompts** vary based on user type: administrators simply approve, while standard users require an admin's credentials.
- UAC sensitivity can be adjusted with four settings, ranging from always notifying to never notifying.
## Best Practices
- Retain UAC at its default setting or higher to maintain optimal security.
- Use administrative privileges judiciously.
- Avoid setting UAC to "Never notify" unless in controlled and secure environments, as it poses a security risk.




___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 24th 2023 (07:48 pm) 
Last Modified Date: August 24th 2023 (07:48 pm)
