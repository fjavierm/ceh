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

## Enumeration Using Email Ids

Extraction of information using Email Ids can provide attackers with usernames, domain names, organisation divisions, etc. It depends on the format the emails has.

## Enumeration Using Default Passwords

Another way of enumeration is based on the use of default passwords. Devices and software usually come with a default configuration, including passwords. UnUnfortunately, unless the administrator or person in charge of their installation customises the configuration, a lot of them keep their defaults settings. It is not difficult for attackers to find this default setting and try to access devices under the target's supervision.

## Enumeration Using SNMP

[Simple Network Management Protocol](https://en.wikipedia.org/wiki/Simple_Network_Management_Protocol) (SNMP) is an Internet Protocol for collecting and organizing information about managed devices on IP networks and for modifying that information to change device behaviour. Devices that typically support SNMP include cable modems, routers, switches, servers, workstations, printers, and more.

SNMP is widely used in network management for network monitoring. SNMP exposes management data in the form of variables on the managed systems organized in a management information base (MIB) which describe the system status and configuration. These variables can then be remotely queried (and, in some circumstances, manipulated) by managing applications.

The attackers can use default connection strings or guessed strings to extract information about the devices.

## Brute Force Attack on Active Directory

[Active Directory](https://en.wikipedia.org/wiki/Active_Directory) (AD) is a directory service developed by Microsoft for Windows domain networks. It is included in most Windows Server operating systems as a set of processes and services. Initially, Active Directory was only in charge of centralized domain management. Starting with Windows Server 2008, however, Active Directory became an umbrella title for a broad range of directory-based identity-related services. It authenticates and authorizes all users and computers in a Windows domain type network—assigning and enforcing security policies for all computers and installing or updating software

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
