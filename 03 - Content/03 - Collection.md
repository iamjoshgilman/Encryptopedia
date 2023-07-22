---
creation date: June 23rd 2023
last modified date: June 23rd 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Incident Response]] | [[000 - Global Index]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Collection]]  
---

- Collection is the ninth stage in the MITRE ATT&CK framework.
- Adversaries identify important files or information, collect them, and prepare them for data exfiltration.
- Collection techniques involve gathering data from various sources.
- This lesson focuses on the following techniques: Email Collection (T1114), Audio Capture (T1123), Screen Capture (T1133), and Data From Local System (T1005).

### Email Collection (MITRE Technique T1114)

- Adversaries target and collect emails from systems.
- Sub-techniques:
    - Local Email Collection: Targeting emails on the local system.
    - Remote Email Collection: Pivoting to an Exchange server or Office 365.
    - Email Forwarding Rule: Setting up rules to forward emails to an attacker's address.
- Mitigations:
    - Use multi-factor authentication (MFA) to prevent unauthorized access.
    - Encrypt emails and sensitive documents.
    - Monitor auto-forwarding rules in enterprise-grade email solutions.
- Detection suggestions:
    - Monitor for unusual processes accessing email servers or applications.
    - Monitor for unusual PowerShell, WMI, and CMD commands executed from user accounts.

### Audio Capture (MITRE Technique T1123)

- Attackers capture audio using peripheral devices like microphones and webcams.
- Audio capture can include conversations via VOIP applications.
- Mitigation: Focus on detection, as it is not feasible to completely mitigate this technique.
- Detection suggestions:
    - Monitor API calls related to audio capture.
    - Monitor unusual processes attempting to access the microphone.
    - Monitor audio-related file creation.

### Screen Capture (MITRE Technique T1133)

- Attackers take screen captures to gather information or monitor user activities.
- Native utilities or API calls are used for screen capture.
- Mitigation: Focus on detection, as legitimate purposes exist for screen capture.
- Detection suggestions:
    - Monitor unusual API calls related to taking screenshots.
    - Link screen capture activity with other malicious behavior for stronger detection.

### Data From Local System (MITRE Technique T1005)

- Attackers search for files of interest and sensitive data on local or networked drives.
- Interpreters and automated collection tools are used for data identification.
- Procedure examples involve exfiltration of internal documents, stealing specific file extensions, and more.
- Mitigation: Difficult to differentiate between legitimate and malicious activity.
- Detection suggestions:
    - Monitor for excessive usage of commands in CMD and PowerShell related to file access and changes.

## Key Points and Practices

- Collection involves identifying, gathering, and preparing important files or information.
- Email collection techniques target emails for various purposes.
- Audio capture involves recording audio from peripheral devices.
- Screen capture is used to gather information or monitor user activities.
- Data from the local system refers to searching for files of interest.
- Mitigate collection through MFA, encryption, and monitoring.
- Detect collection through monitoring processes, API calls, and suspicious file access.

## References

- [MITRE ATT&CK Framework](https://attack.mitre.org/)


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 23rd 2023 (10:45 am) 
Last Modified Date: June 23rd 2023 (10:45 am)
