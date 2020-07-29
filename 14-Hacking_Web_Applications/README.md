# Hacking Web Applications

Hundreds, thousands, millions, billions of systems are online nowadays, they offer services to their users and, in some cases, i.e. critical systems, they are indispensable. Some of these online services are web applications running on web servers. Organisations have embraced them and, they are not just used in the corporate sector to perform important and, some times, critical tasks, they have expanded globally for social and entertainment purposes.

Web applications present a great security challenge. They need high availability and smooth performance but, they are always exposed to a big number of users. For all these reasons, ensure security measures and eliminate vulnerabilities is crucial.

## Some Concepts

A web application is an application that runs on a remote server and it is available to clients over the Internet. This access is offered through clients, sometimes just the browser or specialised client software. These clients can be very complex having code or logic on their own or dummy clients where all the logic resides at the server.

### Server Administrator

It is the person who takes care of the webserver in terms of safety, security, functioning and performance. It is responsible for estimating security measures and deploying security models, finding and eliminating vulnerabilities.

### Application Administrator

It is the person responsible of the management and configuration required for the web application. It ensures the availability and high performance of the web application.

### Client

Clients are designed to interact with the web applications and they can range from simple dummy clients to very complex ones.

### Web Application Threats

Multiple different threats apply to web applications:

* **Insecure storage**: The software stores sensitive information without properly limiting read or write access by unauthorized actors.

* **Information leakage**: Information leakage happens whenever a system that is designed to be closed to an eavesdropper reveals some information to unauthorized parties nonetheless.

* **Directory traversal**: Directory traversal or Path Traversal is an HTTP attack which allows attackers to access restricted directories and execute commands outside of the web server's root directory.

* **Parameter/Form tampering**: Parameter tampering is a form of web-based attack in which certain parameters in the Uniform Resource Locator (URL) or web page form field data entered by a user are changed without that user's authorization.

* **DoS Attacks**: A denial-of-service attack (DoS attack) is a cyber-attack in which the perpetrator seeks to make a machine or network resource unavailable to its intended users by temporarily or indefinitely disrupting services of a host connected to the Internet.

* **Buffer overflow**: Buffer overflow is an anomaly that occurs when software writing data to a buffer overflows the buffer’s capacity, resulting in adjacent memory locations being overwritten. In other words, too much information is being passed into a container that does not have enough space, and that information ends up replacing data in adjacent containers.

* **Log tampering**: Weblogs tampering attacks involve an attacker injecting, deleting or otherwise tampering with the contents of web logs typically for the purposes of masking other malicious behaviour. Additionally, writing malicious data to log files may target jobs, filters, reports, and other agents that process the logs in an asynchronous attack pattern.

* **Injection**: Injection is the placement of malicious code via an input.

    * **SQL injection**: SQL injection is the placement of malicious code in SQL statements, via web page input.

    * **Command injection**: Command injection is an attack in which the goal is the execution of arbitrary commands on the host operating system via a vulnerable application.

    * **LDAP injection**: LDAP injection is a crafted query that can manipulate vulnerable LDAP servers, leading to serious cases of data and identity theft.

    * **SMTP injection**

    * **XPath injection**

    * **...**

* **Cross-site scripting**: Cross-site scripting (XSS) attacks are a type of injection, in which malicious scripts are injected into otherwise benign and trusted websites.

* **Cross-site request forgery**: Cross-site request forgery (CSRF) is an attack that forces an end user to execute unwanted actions on a web application in which they're currently authenticated.

* **Security misconfiguration**: Security misconfiguration is simply defined as failing to implement all the security controls for a server or web application, or implementing the security controls, but doing so with errors.

* **Broken session management**: Weakness of the session management systems like:

    * User authentication credentials are not protected when stored.
    * Predictable login credentials.
    * Session IDs are exposed in the URL.
    * Session IDs are vulnerable to session fixation attacks.
    * Session value does not timeout or does not get invalidated after logout.
    * Session IDs are not rotated after successful login.
    * Passwords, session IDs, and other credentials are sent over unencrypted connections.

* **DMZ attack**: Attack attempts to take down and bypass a DMZ.

* **Session Hijacking**: The Session Hijacking attack compromises the session token by stealing or predicting a valid session token to gain unauthorized access to the Web Server.

* **Network Access Attacks**: Everything that covers an attempt to access another user account or network device through improper means.

## Web Application Pentesting

One of the tools security professionals have to prevent attacks is pentesting. In a pentest, security professional tries to take the place of an attacker and break into systems to, posteriorly fix that problem before they get exploited. Pentest try to covert the same ground attacker would cover:

* Collection of information
* Configuration testing
* Authentication testing
* Session testing
* Authorisation testing
* Data validation
* DoS testing
* Web services testing
* Document findings

## Web Application Attack Methodology

* **Analyse web applications**: Observing the functionality and input parameters to identify vulnerabilities, entry points and server technologies that can be exploited. HTTP request and HTTP fingerprinting techniques are used to diagnose there parameters.

* **Attack authentication mechanism**: Trying to bypass authentication. Some attack mechanism are:

    * User enumeration
    * Cookie exploitation
    * Session attacks
    * Passwords attacks

* **Authorisation attack schemes**: Using different techniques to manipulate URLs, requests, POST data, query strings, cookies, parameters, HTTP headers, etc. to escalate privileges once low-level access has been achieved.

* **Session management attack**: There are different techniques that can be used to impersonate a legitimate user:

    * Session token prediction
    * Session token tampering
    * Man-in-the-middle attack
    * Session replay

* **Attack data connectivity**: Design to exploit the connection between a server and a database. It includes:

    * Connection string injection
    * Connection string parameters pollution (CSPP)
    * Connection Pool DoS

## Countermeasures

There are literally hundreds of things that can be done to try to mitigate web application attacks. They can not be just listed but, a great starting point could be the [OWASP Top 10 project](https://owasp.org/www-project-top-ten/) where are explained to top ten more common vulnerabilities, how they work and possible ways to mitigate them.

// TODO Review this chapter: Cloud, CI, DevOps practices, everything feels obsolete

// TODO re-sort, the way the information is exposed seems messy