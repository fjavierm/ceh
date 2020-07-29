# Enumeration

In the previous phases, attackers have gathered information about a target, by this point, they should have a very good picture and understanding of the target resources and an extensive knowledge about it but, at this point, it is not a very detailed picture, it is more like a sketch. Now, it is the time to add the details. Attackers need more concrete information about the different resources discovered, information that can help them to gain access to the systems. Examples of this sensitive information can be things like routing paths, DNS information, users information, groups information, deeper knowledge about the network resource and the network itself, protocol-related information, SNMP, etc.

To obtain all this extra information, in this phase, attackers will start to actively connect to the target systems and generating queries to the different systems to extract as much information as possible. As named before, information like the listed below can be obtained and it is desired:

* Routing information
* SNMP information
* DNS information
* Machine names
* User information
* Group information
* Application and banners
* Network sharing information
* Network resources

There are some points in the list that have been named in previous phases, the main difference here it is that, while before everything attackers have done was analysing passive information, now, they are actively contacting the target systems. This implies a big change, everything done till this point was not too concerned with any legal issue but, at this point, enumeration may cross some legal boundaries and there are some chances of being traced as attackers actively connecting with the target.

Multiple enumeration techniques can be used in this phase. Some of the most well know are going to be listed in this document.

One tool attacker can use to perform SNMP enumerations is [snmp-check](https://tools.kali.org/information-gathering/snmp-check) that allows them to enumerate the SNMP devices and places the output in a very human-readable friendly format. It could be useful for penetration testing or systems monitoring. 

## Enumeration Using Email Ids

Extraction of information using Email Ids can provide attackers with usernames, domain names, organisation divisions, etc. It depends on the format the emails has.

## Enumeration Using Default Passwords

Another way of enumeration is based on the use of default passwords. Devices and software usually come with a default configuration, including passwords. UnUnfortunately, unless the administrator or person in charge of their installation customises the configuration, a lot of them keep their defaults settings. It is not difficult for attackers to find this default setting and try to access devices under the target's supervision.

## Enumeration Using SNMP

[Simple Network Management Protocol](https://en.wikipedia.org/wiki/Simple_Network_Management_Protocol) (SNMP) is an Internet Protocol for collecting and organizing information about managed devices on IP networks and for modifying that information to change device behaviour. Devices that typically support SNMP include cable modems, routers, switches, servers, workstations, printers, and more.

SNMP is widely used in network management for network monitoring. SNMP exposes management data in the form of variables on the managed systems organized in a management information base (MIB) which describe the system status and configuration. These variables can then be remotely queried (and, in some circumstances, manipulated) by managing applications.

The attackers can use default community strings or guessed strings to extract information about the devices. This community string is in a different form in different versions of SNMP.

The features of available SNMP variants are:

* V1: No support for encryption and hashing. Plain text community string is used for authentication.
* V2: Get data in bulk from agents is implemented.
* V3: Support for both encryption (DES) and hashing (MD5 or SHA) is added.

## Brute Force Attack on Active Directory

[Active Directory](https://en.wikipedia.org/wiki/Active_Directory) (AD) is a directory service developed by Microsoft for Windows domain networks. It is included in most Windows Server operating systems as a set of processes and services. Initially, Active Directory was only in charge of centralized domain management. Starting with Windows Server 2008, however, Active Directory became an umbrella title for a broad range of directory-based identity-related services. It authenticates and authorizes all users and computers in a Windows domain type network—assigning and enforcing security policies for all computers and installing or updating software.

Targeting an active directory server can give the attackers access to usernames, addresses, credentials, privileged information, etc.

## Enumeration through DNS Zone Transfer

Zone transfer is the process of copying the contents of the zone file on a primary DNS server to a secondary DNS server. Using zone transfer provides fault tolerance by synchronizing the zone file in a primary DNS server with the zone file in a secondary DNS server.

UDP 53 is used for DNS request from DNS servers. TCP 53 is used for DNS zone transfers to ensure the transfer went through.

This can offer attackers information like the location of DNS servers, DNS records, and some other network information such as hostnames, IP addresses, usernames, etc.

Some interesting ports and services to enumerate are:

| Services | Ports |
|:-|:-|
| SMTP | TCP 25 |
| DNS zone transfer | TCP 53 |
| DNS queries | UDP 53 |
| Microsoft RPC Endpoint Mapper | TCP/UDP 135 |
| NBNS | UDP 137 |
| NetBIOS | TCP 139 |
| SNMP | UDP 161 |
| SNMP Trap | TCP/UDP 162 |
| LDAP | TCP/UDP 389 |
| Global catalogue service | TCP/UDP 3268 |

// TODO: Example of this: Ping sweep: nmap -sP 192.168.1.0/224, UDP port scanning: nmap -sU -p ip, Stealth: nmap -sS ip, Versions and OS: nmap -sSV -O ip

## NetBIOS Enumeration

NetBIOS (Network Basic Input/Output System) is a program that allows applications on different computers to communicate within a local area network (LAN). It does not in itself support a routing mechanism so applications communicating on a wide area network (WAN) must use another "transport mechanism" (such as Transmission Control Protocol) rather than or in addition to NetBIOS.

NetBIOS service uses a unique 16-ASCII character string to identify the network devices over TCP. First 15 characters identify the device and the character number 16th identifies the service. NetBIOS service uses the TCP port 139 and NetBIOS over TCP (NetBT) uses the following TCP and UPD ports:

* UDP port 137 - name services
* UDP port 138 - datagram services
* TCP port 139 - session services

Using NetBIOS attackers can discover:

* List of machines within a domain
* File sharing
* Printer sharing
* Usernames
* Group information
* Passwords
* Policies

One tool that serves atackers to perform NetBIOS enumeration is [nbstat](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/nbtstat) for Windows systems or [nbtscan](https://tools.kali.org/information-gathering/nbtscan-unixwiz) for GNU/Linux based systems.

For example, we can execute `nbtscan -v -s : 192.168.1.0/24` to execute scans on a C-class network and print the results in a script-friendly format using a colon as a field separator.

## LDAP Enumeration

[LDAP](https://ldap.com), the Lightweight Directory Access Protocol, is a mature, flexible, and well supported standards-based mechanism for interacting with directory servers. It is often used for authentication and storing information about users, groups, and applications, but an LDAP directory server is a fairly general-purpose data store and can be used in a wide variety of applications.

There are a lot of tools that allow attackers to execute LDAP enumeration, one of them been [enum4linux](https://tools.kali.org/information-gathering/enum4linux).

## NTP Enumeration

The [Network Time Protocol](http://www.ntp.org) (NTP) is used to synchronize the time of a computer client or server to another server or reference time source, such as a radio or satellite receiver or modem. It provides client accuracies typically within a millisecond on LANs and up to a few tens of milliseconds on WANs relative to a primary server synchronized to Coordinated Universal Time (UTC) via a Global Positioning Service (GPS) receiver, for example. Typical NTP configurations utilise multiple redundant servers and diverse network paths, in order to achieve high accuracy and reliability. Some configurations include cryptographic authentication to prevent accidental or malicious protocol attacks.

Multiple services rely on clock settings for login and logging purposes. NTP helps with the correlation of events occurred in a system.

There are two main concerns around NTP. The first one, it is that attackers can replace legitimate servers or introduce a new NTP server in a network to mislead forensic investigator when investigating an attack.

The second, it is that attackers can extract some useful information like host information from services using the NTP server, client IP addresses, machine names and operating systems, network information even internal IPs depending on network configurations.

Some tools are [ntpdc](http://doc.ntp.org/4.1.2/ntpdc.htm), used to query the `ntdd` daemon current state and request changes in state. Or others like [ntptrace](https://www.eecis.udel.edu/~mills/ntp/html/ntptrace.html) or [ntpq](http://doc.ntp.org/4.1.0/ntpq.htm).

In addition to these tools, `nmap` making use of its NSE script can execute NTP enumerations. As an example, the next command can be executed:

`nmap -sU -p 123 --script ntp-info <ip>`

## SMTP Enumeration

The [Simple Mail Transfer Protocol](https://en.wikipedia.org/wiki/Simple_Mail_Transfer_Protocol) (SMTP) is a communication protocol for electronic mail transmission. As an Internet standard, SMTP was first defined in 1982 by RFC 821 and updated in 2008 by RFC 5321 to Extended SMTP additions, which is the protocol variety in widespread use today. Mail servers and other message transfer agents use SMTP to send and receive mail messages. SMTP servers commonly use the Transmission Control Protocol on port number 25.

### SMTP Commands

SMTP has multiple commands to make possible communication between users. By inspecting the different responses to this command, attackers can figure out which user ar valid or invalid. Some of these commands are:

* HELO: To identify the domain name of the server.
* EXPN: Verify Mailbox on localhost.
* MAIL FROM: To identify the sender of the email.
* RCPT TO: Specify the message recipients.
* SIZE: To specify maximum supported size information.
* DATA: To define data.
* RSET: Reset the communication and buffer of SMTP.
* VRFY: Verify the availability of the mail server.
* HELP: Show help.
* QUIT: To terminate a session.

An interesting tool for SMTP enumeration is [smtp-user-enum](https://tools.kali.org/information-gathering/smtp-user-enum) been a username guessing tool primarily for the SMTP service.

## SMB Enumeration

The [Server Message Block](https://en.wikipedia.org/wiki/Server_Message_Block) (SMB) is a protocol for sharing files, printers, serial ports, and communications abstractions such as named pipes and mail slots between computers.

SMB is a client-server, request-response protocol. The only exception to the request-response nature of SMB is when the client has requested opportunistic locks (oplocks) and the server subsequently has to break an already granted oplock because another client has requested a file open with a mode that is incompatible with the granted oplock. In this case, the server sends an unsolicited message to the client signalling the oplock break.

Servers make file systems and other resources (printers, mailslots, named pipes, APIs) available to clients on the network. Client computers may have their own hard disks, but they also want access to the shared file systems and printers on the servers.

Clients connect to servers using TCP/IP (NetBIOS over TCP/IP), NetBEUI or IPX/SPX. Once they have established a connection, clients can then send commands (SMBs) to the server that allow them to access shares, open files, read and write files, and generally do all the sort of things that you want to do with a file system.

If found, a Samba server can give attackers extensive access to a hard drive in a server if the configuration has not been properly done.

## Enumeration Countermeasures

### SNMP

* Configure additional restrictions for anonymous connections.
* Upgrade SNMP to SNMPv3.
* Change default community string.

### DNS (Zone Transfer)

* Avoid publishing private addresses information in the zone files.
* Disable zone transfer for untrusted hosts.
* Hide sensitive information from the public.

### SMTP

* Remove sensitive information from mail responses.
* Disable open relay.
* Ignore email to unknown recipients.

### LDAP

* Configure different usernames and email addresses.
* Configure authentication.
* Configure SSL encryption.
* Configure password policy.
* Access control policy.
 
### NetBIOS

* Disable SMB (if not needed).
* Disable NetBIOS.
* Use a network firewall.
* Use a software firewall.
* Disable sharing.

### NTP

* Configure MD5 layer.
* Configure NTP authentication.
* Upgrade NTP version.
