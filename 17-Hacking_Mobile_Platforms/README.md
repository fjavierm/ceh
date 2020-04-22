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

Rooting is basically the process of gaining privileged control over a device, commonly know as Root access. As in one other Linux kernel-based system, root access gives _superuser_ permissions. These permissions allow to modify the system settings and configurations and overcome limitations and restrictions. The rooting process can be used for malicious intentions such as the installation of malicious applications, analysing custom firmware of given unnecessary permission to applications.

![Android Stack](img/01_android-stack.png)

### Android Phone Security Tools

There are multiple Android security tools that can be found in the stores but, when installing them, users need to keep in mind and be sure of their authenticity and that the companies or developers behind them are legitimate.

// TODO Add some tools maybe

## Hacking iOS

iOS is the operative system developed by Apple for their iPhones and nowadays it can be found in other devices of the company like iPads and iPods. Together with Android, they are the two most popular operative systems for mobile devices.

Major versions of the operative system tend to be released yearly. Two of the major security improvements that iOS brings to the table are hardware-accelerated encryption and application isolation where, one application cannot access another application's data.

### iOS Jailbreak

A jailbreak is a form of rooting resulting in privilege scalation. Jailbreak is usually done to remove or bypass the factory default restrictions by using kernel patches or device customisation. Jailbreak allows root access to the device what allows users to install unofficial applications.

#### Types of Jailbreak

* **Userland exploit**: This jailbreak allows _user-level_ access without scaling to about-level access.

* **iBoot exploit**: This jailbreak allows _user-level_ and _boot-level_ access.

* **Bootrom exploit**: This jailbreak allows _user-level_ and _boot-level_ access.

#### Jailbreak Techniques

* **Tethered Jailbreak**: A tethered jailbreak is one that temporarily pwns a handset for a single boot. After the device is turned off (or the battery dies), it cannot complete a boot cycle without the help of a computer-based jailbreak application and a physical cable connection between the device and the computer in question.

* **Semi-Tethered Jailbreak**: A semi-tethered jailbreak is one that permits a handset to complete a boot cycle after being pwned, but jailbreak extensions will not load until a computer-based jailbreak application is deployed over a physical cable connection between the device and the computer in question.

* **Semi-Untethered Jailbreak**: A semi-untethered jailbreak is one that permits a handset to complete a boot cycle after being pwned, but jailbreak extensions will not load until a side-loaded jailbreak app on the device itself is deployed.

* **Untethered Jailbreak**: An untethered jailbreak is one that permits a handset to complete a boot cycle after being pwned without any interruption to jailbreak-oriented functionality.

#### Jailbreak Tools

There are multiple jailbreak tools such as:

* Pangu
* evasi0n7
* LimeRaln
* BlackRaln

## Hacking Windows Phone OS

Windows Phone OS is another mobile operative system developed by Microsoft. Windows Phone 8 is the second generation of the Windows Phone mobile operating system from Microsoft. It was released on October 29, 2012, and, like its predecessor, it features a flat user interface based on the Metro design language. It was succeeded by Windows Phone 8.1, which was unveiled on April 2, 2014.

Windows Phone 8 replaces the Windows CE-based architecture used in Windows Phone 7 with the Windows NT kernel found in Windows 8. Current Windows Phone 7 devices cannot run or update to Windows Phone 8, and new applications compiled specifically for Windows Phone 8 are not made available for Windows Phone 7 devices. Developers can make their apps available on both Windows Phone 7 and Windows Phone 8 devices by targeting both platforms via the proper SDKs in Visual Studio.

Windows Phone 8 devices are manufactured by Microsoft Mobile (formerly Nokia), HTC, Samsung and Huawei.

Some features supported are:

* Native code support (C++)
* NFC
* Remote device management
* VoIP and video chat integration
* UEFI and firmware over the air for windows phone update
* App sandboxing

## Hacking BlackBerry

BlackBerry OS is a proprietary mobile operating system designed specifically for Research In Motion's (RIM) BlackBerry devices. The BlackBerry OS runs on Blackberry variant phones.

The BlackBerry OS is designed for smartphone environments and is best known for its robust support for push Internet email and was considered as the most prominent and secure mobile phones.

Traditionally, BlackBerry applications are written using Java, particularly the Java Micro Edition (Java ME) platform. However, RIM introduced the BlackBerry Web development platform in 2010, which makes use of the widget software development kit (SDK) to create small standalone Web apps made up of HTML, CSS and JavaScript code.

### BlackBerry Attack Vectors

* **Malicious code signing**: It the process where attacker after obtaining a code-signing key from the code-signing service sign a malicious application and uploads it to the BlackBerry App Store to be distributed to users.

* **JAD file exploit**: 

JAD stands for Java Application Descriptor file. Files with the _.jad_ extension are descriptor files that are commonly used to describe the contents of a MIDlet that are created for the Java ME virtual machine. Attackers can trick users to install malicious _.jad_ files pointing to malicious download links to obtain an application or, even, they can be crafted to run DoS attacks.

## Mobile Device Management (MDM)

Mobile device management (MDM), is the process of managing everything about a mobile device. MDM includes storing essential information about mobile devices, deciding which apps can be present on the devices, locating devices, and securing devices if lost or stolen. Many businesses use a third-party mobile device management software such as Mobile Device Manager Plus to manage mobile devices. Mobile Device Management has expanded its horizons to evolve into Enterprise Mobility Management (EMM). 

Mobile devices now have more capabilities than ever before, which has ultimately led to many enterprises adopting a mobile-only or mobile-first workforce. In these types of environments, both personal (BYOD) and corporate-owned mobile devices are the primary devices used for accessing or interacting with corporate data.

Mobile Device Management (MDM) is important for enterprises focussing on improving productivity and security. They allow:

* Ease deployments
* Efficient Integrations
* Manage multiple device types
* Achieve compliance
* Enhanced security
* Remote management

And provide some functions such as:

* Enforcing a device to be locked after certain login failures.
* Enforcement of strong password policies for all BYOD devices.
* MDM can detect any attempt of hacking on BYOD devices and limit their network access for those affected devices.
* Enforcing confidentiality by using encryption as per organizations policy.
* Administration and implementation of _DAta Loss Prevention (DLP)_ for BYOD devices. 

### MDM Deployment Methods

Generally, there are two types of deployments:

#### On-site MDM Deployment

Involves the installation of MDM applications on local servers inside the corporate data centres or offices and its managed by local staff available on-premises.

The major advantage is the granular control over the management of the BYOD devices, which, in some extend, extends the security.

The on-site MDM deployment has the next components or areas:

* **Data centre**: All the necessary services and serves to manage the infrastructure, connectivity, access and security policies.

* **Internet edge**: Its basic purpose is to provide connectivity to the public internet. Firewalls, filters, monitors for ingress and egress traffic and, wireless controllers and access points for guest users.

* **Services layer**: Contain wireless controllers and access points used by users in the corporate environment. And sometimes services like NTP or other support services.

* **Core layer**: Just like every other design, the core is the focal point of the whole network regarding routing of traffic in a corporate network environment.

* **Campus Building**: A distribution layer that acts as ingress/egress point for all traffic in a campus building, where users can connect using switches or wireless access points.

#### Cloud-based MDM deployment

In this type of deployment the MDM software is installed and managed by a third-party service and, this is one of the best advantages of this type due to the maintenance and troubleshooting been responsibility of the service provider.

The cloud-based MDM deployment has the next components or areas:

* **Data centre**: All the necessary services and serves to manage the infrastructure, connectivity, access and security policies.

* **Internet edge**: Its basic purpose is to provide connectivity to the public internet. Firewalls, filters, monitors for ingress and egress traffic and, wireless controllers and access points for guest users.

* **WAN**: Provides VPN connectivity from branch offices to the corporate office, internet access from branch offices and connectivity to cloud-based MDM application software. MAintain policies and configurations for BYOD devices connected to the corporate network.

* **WAN edge**: This component act as a focal point for all ingress/egress WAN traffic from and going to branch offices.

* **Services layer**: Contain wireless controllers and access points used by users in the corporate environment. And sometimes services like NTP or other support services.

* **Core layer**: Just like every other design, the core is the focal point of the whole network regarding routing of traffic in a corporate network environment.

* **Branch offices**: This component is compromised of few routers acting as the focal point of ingress and egress traffic out of branch offices. USer can connect using access switches or wireless access points.

## Bring Your Own Device (BYOD)

