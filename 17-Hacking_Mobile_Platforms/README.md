# Hacking Mobile Platforms

Mobile phones, they are nowadays everywhere. They are used for entertainment, work, personal finances and services, almost anything we can imagine. In addition, there are a in the market a big variety of systems running on these mobile devices such as iOS, Blackberry OS, Android, Symbian, Windows, etc.

For all these reasons, these mobile devices must have strong security and not just a feeling of been secure to protect their users and all the private information they store. Plus, with the _Bring Your Own Device_ philosophy, devices can cause multiple problems in corporate environments and networks.

## Mobile Platform Attack Vectors

The OWAS project publishes an unbiased and practical list of the top 10 most common attacks on mobile platforms:

| Top 10 (2016) | Top 10 (2014) |
|:-|:-|
| Improper Platform Usage | Weak Server Side Controls |
| Insecure Data Storage | Insecure Data Storage |
| Insecure Communication | Insufficient Transport Layer Protection |
| Insecure Authentication | Unintended Data Leakage |
| Insufficient Cryptography | Poor Authorization and Authentication |
| Insecure Authorization | Broken Cryptography |
| Client Code Quality | Client Side Injection |
| Code Tampering | Security Decisions Via Untrusted Inputs |
| Reverse Engineering | Improper Session Handling |
| Extraneous Functionality | Lack of Binary Protections |

More information can be found at the project's page [OWASP Mobile Top 10](https://owasp.org/www-project-mobile-top-10/)

### Mobile Attack Vector

There are several threads and attacks on mobile devices. Some of the most basics examples are malware, data loss, integrity attacks, social engineering attacks, etc. Mobile attack vectors include:

* Malware
* Data loss
* Data Tampering
* Data Exfiltration

### Vulnerabilities and Risks on Mobile Platforms

Some of the risks for mobile platforms are:

* Malicious third-party applications
* Malicious applications on Store
* Malware and rootkits
* Application vulnerabilities
* Data security
* Excessive permissions
* Weak encryption
* Operative system update issues
* Application updates issues
* Jailbreak and rooting
* Physical attacks

### Application Sandbox Issue

Application sandboxing, also called application containerization, is an approach to software development and mobile application management (MAM) that limits the environments in which certain code can execute.

The goal of sandboxing is to improve security by isolating an application to prevent outside malware, intruders, system resources or other applications from interacting with the protected app. The term sandboxing comes from the idea of a child's sandbox, in which the sand and toys are kept inside a small container or walled area.

Application sandboxing is controversial because its complexity can cause more security problems than the sandbox was originally designed to prevent. The sandbox has to contain all the files the application needs to execute, which can also create problems between applications that need to interact with one another. Still, it is one of the best security methods to be used when developing for mobile devices.

However, advance malicious applications can be designed to bypass the sandbox technology. Fragmented codes and sleep timers are common techniques adopted by attackers to bypass the inspection process.

### Mobile Spam and Phishing

Mobile devices and technologies are just another path attackers can choose to send emails or messages spamming users or trying to convince them to click and access malicious links searching for credentials or information.

### Open Wi-Fi and Bluetooth Networks

Public or unencrypted Wi-Fi or Bluetooth networks are another easy way for attackers to intercept communications and reveal information.

## Hacking Android OS

Android is an operative system developed by Google for smartphones. But, it is not only present in smartphones, it can be found in other devices like gaming consoles, PCs and IoT devices. Android OS brings flexible features with an open-source platform.

Android OS has very wide support for and integration with different hardware and services what is one of its major features, and receives periodically updates.

On of the most successful features is also one of the major security flows for Android devices been this the flexibility to install third-party apps not just from trusted stores by applications (APKs) from other sources of the Internet.

### Device Administration API

In version 2.2 of the Android SO the Device Administration API was introduced to ensure the administration of the device at the system level and offering control over Android devices within a corporate network. Using this security-aware API, administrators can perform several actions including wiping the device remotely or manage installed applications.

### Root Access / Android Rooting


