# Hacking Web Servers

A web server is server software, or hardware dedicated to running this software, that can satisfy client requests on the World Wide Web. A web server can, in general, contain one or more websites. A web server processes incoming network requests over HTTP and several other related protocols. The primary function of a web server is to store, process and deliver web pages to clients.

On the hardware side, a web server is a computer that stores web server software and a website's component files (e.g. HTML documents, images, CSS stylesheets, and JavaScript files). It is connected to the Internet and supports physical data interchange with other devices connected to the web.

On the software side, a web server includes several parts that control how web users access hosted files, at a minimum an HTTP server. An HTTP server is a piece of software that understands URLs and HTTP. It can be accessed through the domain names of websites it stores, and delivers their content to the end-user's device.

## Some Concepts

### Web Server Security Issue

Security issues for web server may include network-level and operative system-level attacks. Usually, attackers target vulnerabilities or mistakes in the configuration and exploit them. These vulnerabilities may include:

* Improper permissions of file directories
* Default configurations
* Unnecessary services enabled
* Lack of security
* Bugs
* Misconfigured SSL certificates
* Enabled debugging

Once a web server has been compromised it can result in compromising all user accounts, DoS offered by the server, defacement, launching further attacks using the compromised web server and access to resources and data.

### Open Source Web Servers

They are servers where the code is available to the public and maintained by communities like open source. they can be hosted on-premises or by third-party companies. Example are:

* Apache HTTP Server
* NGINX
* Apache Tomcat
* Lighttpd
* Node.js

### IIS Web Server

Internet Information Service (IIS) is a windows-based service which provides a request processing architecture. IIS contains multiple components which are responsible for several functions such as listening to the request, managing processes, reading configuration files, etc. Some of these components are:

* **Protocol listener**: Protocol listeners are responsible for receiving protocol-specific requests. They forward these requests to IIS for processing and then return responses to requestors.

* **HTTP.sys**: HTTP listeners are implemented as a kernel-mode service device driver called the HTTP protocol stack (HTTP.sys). HTTP.sys is responsible for listening HTTP requests, forwarding these requests to IIS for processing and then, return processed responses to client browsers.

* **WWW Service and WAS**: World Wide Web Publishing Service (WWW Service) and Windows Processing Activation Service (WAS) run _svchost.exe_ on the local system and share same binaries. WWW Service was used previously to version 7, whereas in version 7 and later WAS is used.

![IIS](img/01_iis.png)

### Web Server Attacks

A lot of attack techniques can be found for web serves, some of them are listed below:

* **DoS/DDoS attack**: Used to flood fake requests toward the web server resulting in the crashing, unavailability or denial of service for all users.

* **DNS server hijacking**: By compromising the DNS configuration, attackers can redirect request targeting a web server to a malicious server owned or controlled by them.

* **DNS amplification attack**: Using the DSN recursive method, attackers can, by spoofing the lookup requests and amplifying the size of the request, originate DDoS attacks.

* **Directory traversal attacks**: Using trial and error methods, attackers ca access restricted directories using dots and slashes sequences revealing sensitive information.

* **Man-in-the-middle/sniffing attacks**: Attacker can extract and intercept sentivie informationor altering packets.

* **Phishing attacks**: Using phishing attacks, attackers can compromise legitimate user credentials to compromise a web server.

* **Website defacement**: After a successful intrusion, attackers can alter or modify the content or appearance of a website.

* **Web server misconfiguration**: Default features or credentials, misconfigurations, default certificates, active debugging capabilities, unnecessary services running, etc. All of this can help attackers to compromise a web server.

* **HTTP response splitting attacks**: HTTP response splitting is a form of web application vulnerability, resulting from the failure of the application or its environment to properly sanitize input values. The attack consists of making the server print a carriage return (CR, ASCII 0x0D) line feed (LF, ASCII 0x0A) sequence followed by content supplied by the attacker in the header section of its response, typically by including them in input fields sent to the application. Per the HTTP standard, headers are separated by one CRLF and the response's headers are separated from its body by two. Therefore, the failure to remove CRs and LFs allows the attacker to set arbitrary headers, take control of the body, or break the response into two or more separate responses—hence the name.

* **Web cache poisoning attacks**: In this attack, attackers wipe the cache of the web server and store fake entries by sending crafted requests into the cache to redirect users to malicious websites.

* **SSH brute-force attacks**: Obtaining access to unauthorised systems by forcing the brute-forcing the access to an available SSH tunnel.

* **Web application attacks** Web servers run web application among others. A vulnerability in any pf the application can be used or affect a web server.

## Web Server Attack Methodology

* **Web server footprinting**: It includes footprinting focused on a web server using different tools like Maltego, Netcraft, Httprecon, etc. Usually, allows discovering server name, type, operative system,  running applications and other interesting information about the target.

* **Mirroring a website**: Download a copy of an entire website to explore it and try to find vulnerabilities avoiding the constant contact with the web server.

* **Vulnerability scanner**: Vulnerability scanner are automated tools specially designed and built to find vulnerabilities, weakness, problems and holes on the operative system, network, software or applications. These tools perform a deep inspection of scripts, open ports, banners, running services, configuration and other areas.

* **Session Hijacking**: As established before, steal some legitimate session to access the web server.

* **Hacking web passwords**: Password cracking is one very common technique where attackers to break the security of the credentials using different methods like:

* Non-electronic attacks
* Active online attacks
* Passive online attacks
* Default passwords
* Offline attacks

## Countermeasures

The basic recommendation is to place the web servers on a secure zone protected by appropriate tools like we have seen in previous chapters, IDS, firewalls. Placing the server into an isolated zone like a DMZ can protect them from threats.

A few specific measures can be:

* Auditing ports
* Disabling insecure and unnecessary ports
* Using port 443 HTTPS over 80 HTTP
* Encrypted traffic
* Server certificates
* Code access security policies
* Disable tracing
* Disable debug compiles

### Patch Management

A very important action to be taken to maintain web servers secure is to have a patch management policy to be able to incorporate updates or hot fixes fixing known security problems.

This process can be manual or automatic, with a preference for the second one. A patch management system should perform the next tasks:

1. Detect missing security patches
2. Find out the solution
3. Download the patch
4. Test the patch in an isolated environment
5. Deploy the patch into the rest of the systems
