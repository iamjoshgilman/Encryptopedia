---
creation date: August 26th 2023
last modified date: August 26th 2023
aliases: []
tags: #📖
---

Primary Categories: [[000 - Global Index]] 
Secondary Categories: [[02 - Foundations]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Security Concepts]]  

# Defence in Depth

## Definition

**Defence in Depth** is a layered security approach aiming to defend a system against any potential vulnerabilities by implementing several layers of security measures. It assumes that any single defensive layer can potentially fail.
## Origin

- Originated as a military strategy during the **Roman empire**.
- Involved having defensive positions at multiple locations, forcing attackers to encounter multiple hurdles, thus eroding their momentum.
## Key Principles in Cybersecurity

1. **Multiple Layers**: Ensure that multiple layers of protection are employed. If one fails, others act as fallbacks.
2. **Prevention and Detection**: Incorporate both preventative measures (to stop a breach) and detection measures (to identify a breach). 
3. **Active Response**: Detecting a breach should be accompanied by a swift and effective response.
4. **Tailored Protection**: Instead of uniformly securing all system components, prioritize critical assets for heavier protection.
5. **Segmentation**: High-risk areas should be isolated from the main system and given additional protection.
6. **Barrier Implementation**: Introduce security controls between high-risk areas and the main system to limit breach propagation.
7. **Workarounds**: Implement alternative solutions for risks that can't be fully eliminated. Example: Removing USB ports to deter data theft via physical access.
## Advantages

1. **Redundancy**: Multiple security layers ensure that if one measure fails, others are in place.
2. **Adaptability**: The approach can be tailored to the specific needs and risks of a system or organization.
3. **Comprehensive Security**: Addresses various types of threats, from external hackers to malicious insiders.
## Implementation Suggestions

1. **Network Firewalls**: Control incoming and outgoing network traffic.
2. **Intrusion Detection Systems (IDS)**: Monitor network traffic for suspicious activity.
3. **Access Controls**: Regulate who can access specific data or systems.
4. **Encryption**: Ensure that data, both at rest and in transit, is encrypted.
5. **Regular Audits**: Regularly review and assess system logs and security measures.
6. **User Training**: Educate users about security best practices to prevent breaches via social engineering or simple errors.

---

# Risk Management

## Overview

**Risk Management** in cybersecurity focuses on understanding, evaluating, and taking appropriate measures to deal with risks associated with IT systems and data. The key is to strike a balance between security and functionality, ensuring that systems are protected but also usable.
## Risk Formula

\[ \text{Risk} = \text{Likelihood of Attack} \times \text{Potential Impact of Breach} \]
## Key Points

1. **Value-Based Protection**: Organizations typically allocate resources for protection proportional to the value of the asset. It's a balance between the cost of protection and the cost of potential loss.
2. **Impact of Breach**: The potential repercussions or consequences of a breach in security.

## Three Pillars of Risk

### 1. Confidentiality

- **Definition**: Ensuring that information is not disclosed to unauthorized individuals, entities, or processes.
- **Example**: Protecting credit card information, health records, or proprietary business data.
- **Potential Threats**: Eavesdropping, data leaks, unencrypted data transfers, insider threats.
### 2. Integrity

- **Definition**: Ensuring the accuracy and reliability of data and systems. Data should remain intact and unaltered unless a change is desired and authorized.
- **Example**: Ensuring software downloads aren't tampered with and replaced with malicious versions.
- **Potential Threats**: Malware, unauthorized data modifications, data tampering, man-in-the-middle attacks.
### 3. Availability

- **Definition**: Ensuring that authorized users have reliable and timely access to resources.
- **Example**: Preventing or mitigating the effects of Denial of Service (DoS) attacks.
- **Potential Threats**: DDoS attacks, hardware failures, natural disasters, misconfigured firewalls.
- **Consideration**: Overly stringent security measures might hinder availability for legitimate users.
## Risk Management Process

1. **Risk Identification**: Understand the assets that need protection and the potential threats they face.
2. **Risk Assessment**: Evaluate the likelihood and potential impact of the identified risks.
3. **Risk Mitigation**: Implement strategies to reduce or eliminate the identified risks. This might involve technical solutions, policy changes, or a combination.
4. **Risk Review**: Regularly revisit and evaluate the identified risks, considering changes in the environment, technology, or business requirements.
5. **Incident Response**: Have a clear plan in place to deal with breaches or security incidents when they occur.

---
# Critical Security Controls

## Overview

Critical Security Controls (CSC) serve as a foundational set of guidelines to bolster an organization's cybersecurity posture. Implementing these controls can dramatically enhance protection against a variety of cyber threats.
## The Top 20 Critical Security Controls

### 1. **Inventory of Devices**
   - Only authorized devices should access the network.
   - Track and manage all hardware devices.
### 2. **Inventory of Software**
   - Ensure only approved software runs on the network.
   - Track all software installations and updates.
### 3. **Secure Configurations**
   - Properly configure all devices and software.
   - Limit vulnerable services and settings.
### 4. **Vulnerability Assessment & Remediation**
   - Regularly identify and patch vulnerabilities.
   - Minimize exposure to known threats.
### 5. **Administrative Privilege Control**
   - Strictly manage and monitor administrative rights.
   - Avoid providing administrative access to regular users.
### 6. **Log Maintenance & Analysis**
   - Collect and review log files.
   - Detect anomalies and potential breaches.
### 7. **Email & Browser Protections**
   - Minimize the risks from phishing and malware.
   - Update and secure web browsers and email clients.
### 8. **Malware Defenses**
   - Implement strong defenses against malware.
   - Monitor for signs of malicious activity.
### 9. **Port, Protocol & Service Control**
   - Manage network ports, protocols, and services.
   - Disable unnecessary services.
### 10. **Data Recovery**
   - Regularly back up essential data.
   - Test data recovery processes.
### 11. **Network Device Configurations**
   - Securely configure network devices.
   - Monitor and update settings as required.
### 12. **Boundary Defense**
   - Control data flow across network boundaries.
   - Ensure sensitive data remains within trusted networks
### 13. **Data Protection**
   - Secure sensitive data against exfiltration.
   - Monitor for unauthorized data access and transfer.
### 14. **Access Control**
   - Limit access based on need-to-know.
   - Monitor and review access rights regularly.
### 15. **Wireless Access Control**
   - Securely manage wireless networks.
   - Regularly review and update wireless configurations.
### 16. **Account Monitoring & Control**
   - Manage account lifecycles effectively.
   - Remove redundant or old accounts.
### 17. **Security Skills Assessment & Training**
   - Identify and address skill gaps.
   - Provide regular security training to staff.
### 18. **Application Software Security**
   - Ensure security throughout the software lifecycle.
   - Patch and update software regularly.
### 19. **Incident Response & Management**
   - Develop a robust response plan for security incidents.
   - Train staff on response procedures.
### 20. **Penetration Testing**
   - Regularly test security measures.
   - Simulate potential attacks to identify weaknesses.

---
# Stages of an Attack

## Overview

Cyber attacks are not spontaneous. They usually follow a structured sequence of events that, when understood, can be used to better protect an organization. Recognizing these stages can help in early detection and mitigation of the threat.
## The Five Main Stages:

### 1. **Reconnaissance**
   - **Goal**: Gather intel about the target.
   - **Methods**:
     - Social engineering.
     - Network mapping.
     - Identifying exposed services.
     - OSINT (Open Source Intelligence).
   - **Outcome**: Comprehensive understanding of the target, its vulnerabilities, and potential entry points.
### 2. **Initial Exploitation**
   - **Goal**: Gain initial access.
   - **Methods**:
     - Exploiting known vulnerabilities.
     - Zero-day attacks.
     - Phishing, baiting, tailgating, etc.
     - Impersonating an employee.
   - **Outcome**: Attacker has a preliminary foothold but lacks stable and broad access.
### 3. **Establish Persistence & Escalate Privileges**
   - **Goal**: Ensure long-term access and gain higher privileges.
   - **Methods**:
     - Installing backdoors.
     - Elevating user privileges.
     - Password cracking or capturing.
   - **Outcome**: Attacker gains administrative access and can return even after initial access methods are closed.
### 4. **Move Laterally**
   - **Goal**: Access other parts of the network.
   - **Methods**:
     - Exploiting internal vulnerabilities.
     - Leveraging stolen credentials.
     - Man-in-the-middle attacks.
   - **Outcome**: Attacker gains access to key systems holding valuable data or resources.
### 5. **Exfiltration**
   - **Goal**: Extract the desired data or achieve the end goal.
   - **Methods**:
     - Data compression and encryption.
     - Use of covert channels.
     - Timing and size-based methods to avoid detection.
   - **Outcome**: The attacker successfully retrieves the target data or achieves their intended disruption.
## Countermeasures:

To counter these stages:
- **Reconnaissance**: Minimize public information, regularly check exposed details, and train employees.
- **Initial Exploitation**: Keep systems updated, invest in intrusion detection systems, and conduct regular training.
- **Establish Persistence & Escalate Privileges**: Limit user privileges, use multi-factor authentication, and monitor for unusual activities.
- **Move Laterally**: Segment the network, apply strict access controls, and monitor internal traffic.
- **Exfiltration**: Monitor outbound traffic, use Data Loss Prevention (DLP) tools, and encrypt sensitive data.


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 26th 2023 (03:53 pm) 
Last Modified Date: August 26th 2023 (03:53 pm)
