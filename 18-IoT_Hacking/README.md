# IoT Hacking

IoT is the concept of basically connecting any device with an on and off switch to the Internet (and/or to each other). This includes everything from cellphones, coffee makers, washing machines, headphones, lamps, wearable devices and almost anything else you can think of. This also applies to components of machines, for example a jet engine of an aeroplane or the drill of an oil rig. As I mentioned, if it has an on and off switch then chances are it can be a part of the IoT.

On a broader scale, the IoT can be applied to things like transportation networks: "smart cities" which can help us reduce waste and improve efficiency for things such as energy use; this helping us understand and improve how we work and live. Take a look at the visual below to see what something like that can look like.

The architecture of IoT depends upon five layers which are:

* **Application layer**: Layer responsible for delivering the data to the users at the application layer. This is the user interface to control, manage and command IoT devices.

* **Middleware layer**: It is for device and information management.

* **Internet layer**: It is responsible for end-points connectivity.

* **Access gateway layer**: It is responsible for protocol transmission and messaging.

* **Edge technology layer**: It covers IoT capable devices.

## IoT Communication Models

There are several ways in which IoT devices can communicate. The following are some of these models:

* **Device-to-Device Model**: It is a basic model where two devices talk to each other without interfering any other device. Communication is established using some kind of wireless connection. Wi-Fi, Bluetooth, NFC or RFID can be examples of this model.

* **Device-to-Cloud Model**: In this model, IoT devices communicate to each other communicating through an application server. For example, manufacturing environments where a usually big amount of sensors send information to a server. Application servers process the data and perform automated actions based on that analysis. 

* **Device-to-Gateway Model**: Similar to the Device-to-Cloud model, and IoT device gateway is added. The function of this gateway is to collect the data from the devices and send it to a remote application server. In addition, offers a consolidated point where checks that the data is flowing can be done. Plus, it can provide security and protocol translation functionalities.

* **Back-End Data-sharing Model**: This model extends the Device-to-Cloud model in a scalable scenario where multiple parties can access and control IoT devices and sensors. In this model, IoT devices communicate with an application server too.

## Understanding IoT Attacks

In addition to the traditional attacks ones, other major challenges can be found in IoT environments:

* Lack of security
* Vulnerable interfaces
* Physical security risk
* Lack of vendor support
* Difficulties to update firmware and OS
* Interoperability issues

The last version of the [OWASP top 10](https://owasp.org/www-pdf-archive/OWASP-IoT-Top-10-2018-final.pdf) define the next vulnerabilities:

* **Weak, Guessable, or Hardcoded Passwords**: Use of easily brute-forced, publicly available, or unchangeable credentials, including backdoors in firmware or client software that grants unauthorized access to deployed systems.

* **Insecure Network Services**: Unneeded or insecure network services running on the device itself, especially those exposed to the internet, that compromise the confidentiality, integrity/authenticity, or availability of information or allow unauthorized remote control.

* **Insecure Ecosystem Interfaces**: Insecure web, backend API, cloud, or mobile interfaces in the ecosystem outside of the device that allows compromise of the device or its related components. Common issues include a lack of authentication/authorization, lacking or weak encryption, and a lack of input and output filtering.
    
* **Lack of Secure Update Mechanism**: Lack of ability to securely update the device. This includes lack of firmware validation on devices, lack of secure delivery (un-encrypted in transit), lack of anti-rollback mechanisms, and lack of notifications of security changes due to updates.

* **Use of Insecure or Outdated Components**: Use of deprecated or insecure software components/libraries that could allow the device to be compromised. This includes insecure customization of operating system platforms, and the use of third-party software or hardware components from a compromised supply chain.

* **Insufficient Privacy Protection**: User's personal information stored on the device or in the ecosystem that is used insecurely, improperly, or without permission.

* **Insecure Data Transfer and Storage**: Lack of encryption or access control of sensitive data anywhere within the ecosystem, including at rest, in transit, or during processing.

* **Lack of Device Management**: Lack of security support on devices deployed in production, including asset management, update management, secure decommissioning, systems monitoring, and response capabilities.

* **Insecure Default Settings**: Devices or systems shipped with insecure default settings or lack the ability to make the system more secure by restricting operators from modifying configurations.

* **Lack of Physical Hardening**: Lack of physical hardening measures, allowing potential attackers to gain sensitive information that can help in a future remote attack or take local control of the device.

## IoT Attack Areas

The following are the most common attack areas for IoT networks:

* Device memory containing credentials
* Access control
* Firmware extraction
* Privileges escalation
* Resetting to an insecure state
* Removal of storage media
* Web attack
* Firmware attacks
* Network services attacks
* Unencrypted local data storage
* Confidentiality and integrity issues
* Cloud computing attacks
* Malicious updates
* Insecure APIs
* Mobile application threats

## IoT Attacks

* **DDoS attacks**: Using this technique all the services associated with an IoT network can be targeted, devices, gateways and application servers.

* **Rolling code attacks**: Rolling code or code hooping is another technique where attacker capture the code, sequence or signal coming from transmitter devices and simultaneously block the receivers. The code will be used later to gain unauthorised access. For example, the opening signal of a car that can be recorded and reproduce it later.

* **BlueBorne attacks**: It is the use of different techniques to exploit Bluetooth vulnerabilities to gain unauthorised access.

* **Jamming jack**: Jamming a signal to prevent devices communication.

* **Backdoor**: Deploying a backdoor on a computer of an employee or victim to gain access to the IoT network. Tricks do not always need to apply to de IoT devices.

Other general attacks are:

* Eavesdropping
* Sybil attack
* Exploit kits
* MitM attacks
* Replay attacks
* Forged malicious devices
* Side-channel attack
* Ransomware attack

## IoT Hacking Methodology

The methodology applied on IoT platforms is the same than the one is applied to other platforms.

* **Information gathering**: IP addresses, running protocols, open ports, type of devices, vendor's information, etc. Shodan, Censys and Thingful are search engines to find information about IoT devices. Shodan is a great tool for discovering and gathering information from IoT devices deployed around the world.

* **Vulnerability scanner**: Scanning network and devices looking for vulnerabilities, weak passwords, software and firmware bugs, default configurations, etc. Nmap and others are very helpful tools.

* **Launch attack**: Exploiting the vulnerabilities using different attacks like DDoS, Rolling code, jamming, etc. RFCrack, Attify Zigbee and HackRF One are popular tools for hacking.

* **Gain access**: Taking control over an IoT environment. Gaining access, escalating privileges, and backdoor installation are included in this phase among others.

* **Maintain attack**: Includes login out without being detected, clearing logs and covering tracks.

## Countermeasures

Countermeasures include:

* Firmware updates
* Block unnecessary ports
* Disable telnet
* Use encryption communication such as SSL/TLS
* Use strong passwords
* Use encryption in drivers
* User account lockout
* Periodic assessment of devices
* Secure password recovery
* Two-factor authentication
* Disable UPnP
