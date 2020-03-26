# Sniffing

A packet sniffer is a utility that listens on a network for transferred data. Packet sniffing allows individuals to capture data as it is transmitted over a network. This technique is used by network professionals to diagnose network issues, and by malicious users to capture unencrypted data, like passwords and usernames.  Using sniffers attackers can gain knowledge of information that might be helpful on further attacks.

To be able to use sniffing techniques the promiscuous mode needs to be enabled in the network interface, this will allow the capture of all the traffic in the network, not just the traffic directed to the interface. Promiscuous mode is a mode of the interface in which the network interface card (NIC) respond for every package it receives. Using these techniques anyone can sniff traffic in a LAN.

There are two types of sniffing techniques:

* **Active sniffing**: Active sniffing is the sniffing type in which attackers have to send additional packets to the connected device such as a switch to start receiving packets. As it is known, a unicast packet from the switch is transmitted to a specific port only. Attackers use certain techniques such as _MAC Flooading_, _DHCP Attacks_, _DNS Poisoning_, _Sitch Port Stealing_, _ARP Poisoning_ and _Spoofing_ to monitor traffic passing through the switch.

* **Passive sniffing**: Passive sniffing is the sniffing type in which there is no need of sending additional packets or interfering the device such as a hub to receive packages. As it is known, a hab broadcast every packet to its port, which helps the attacker to monitor all traffic passing through the hub without any effort.

Two different types of network analysers can be found. Those based on hardware and those based on software.

* **Hardware Analysers**: These are physical pieces of equipment that can be plugged into a network and analyse the traffic without interfering with it. The mayor advantages they offer are that they are mobile, flexible and throughput.

* **Software Analyser**: So call switch port analysis (SPAN). Easy to configure and start, used to diagnose most of the network problems enterprises. And administrator can just run one if one of its users is having problems. The can be configured to monitor inbound, outbound traffic or both. They have some limitations, for example, some types of traffic can no be forwarded like BDPUs, CDP, DTP, VTP, STP. And, if a source port with higher bandwidth than the destination port is used, some of the traffic, if the link gets congested, can be dropped.

## Wiretapping

Wiretapping is a type of sniffing. This maybe sounds like an old fashion thing saw in films but, multiple governmental, security or enforcement agencies used to monitor third party conversations, and usually, it needs a court order or some kind of legal permission. But, attackers can do the same without the legal considerations. Wiretapping is basically electrical tap on the telephone line.

Wiretapping can be classified into its own two types:

* **Active wiretapping**: This type includes monitoring, recording and maybe alter a communication.

* **Passive wiretapping**: This type, just, includes monitoring and recording a communication.

When talking about active sniffing some techniques have been named to help attackers to generate traffic in a network and gather information. It is time to describe these techniques:

## MAC Attacks

 Stands for "Media Access Control Address and a MAC address is a hardware identification number that uniquely identifies each device on a network. The MAC address is manufactured into every network card, such as an Ethernet card or Wi-Fi card, and therefore cannot be changed.

Because there are millions of networkable devices in existence, and each device needs to have a unique MAC address, there must be a very wide range of possible addresses. For this reason, MAC addresses are made up of six two-digit hexadecimal numbers, separated by colons. For example, an Ethernet card may have a MAC address of 00:0d:83:b1:c0:8e.

All devices on the same network subnet have different MAC addresses. MAC addresses are very useful in diagnosing network issues, such as problems with IP addresses. MAC addresses are useful for network diagnosis because they never change, as opposed to a dynamic IP address, which can change from time to time. For a network administrator, that makes a MAC address a more reliable way to identify senders and receivers of data on the network.

### ARP Table

Address Resolution Protocol (ARP) is a protocol for mapping an Internet Protocol address (IP address) to a physical machine address that is recognized in the local network. A table is used to maintain a correlation between each MAC address and its corresponding IP address. ARP provides the protocol rules for making this correlation and providing address conversion in both directions.

### CAM Table

Content Addressable Memory (CAM) table is a system memory construct used by Ethernet switch logic which stores information such as MAC addresses available on physical ports with their associated VLAN Parameters. The CAM table, or content addressable memory table, is present in all switches for layer 2 switching. This allows switches to facilitate communications between connected stations at high speed and in full-duplex regardless of how many devices are connected to the switch. Switches learn MAC addresses from the source address of Ethernet frames on the ports, such as Address Resolution Protocol (ARP) response packets.

### MAC Flooding

The MAC Flooding is an attacking method intended to compromise the security of the network switches. Usually, the switches maintain a table structure called MAC Table. As it has been already seen, the hubs broadcast the data to the entire network allowing the data to reach all hosts on the network but switches send the data to the specific machines which the data is intended to be sent. This goal is achieved by the use of MAC tables.

 The aim of the MAC Flooding is to takedown this MAC Table. In a typical MAC Flooding attack, the attacker sends Ethernet Frames in a huge number. When sending many Ethernet Frames to the switch, these frames will have various sender addresses. The intention of the attacker is consuming the memory of the switch that is used to store the MAC address table. The MAC addresses of legitimate users will be pushed out of the MAC Table. Now the switch cannot deliver the incoming data to the destination system. So a considerable number of incoming frames will be flooded at all ports.

MAC Address Table is full and it is unable to save new MAC addresses. It will lead the switch to enter into a fail-open mode and the switch will now behave like a network hub. It will forward the incoming data to all ports broadcasting it.

As the attacker is a part of the network, the attacker will also get the data packets intended for the victim machine. So that the attacker will be able to steal sensitive data from the communication of the victim and other computers. Usually, a packet analyzer is used to capture these sensitive data.

### Switch Port Stealing

This attack uses MAC flooding to sniff traffic between two hosts. Switch port stealing works by stealing the switches port of the target host. Switches learn to bind MAC addresses to each port by seeing the source MAC addresses in the packets that arrive from each port. The user wanting to sniff the traffic steals the switches port to the target host so the traffic will go through it first, then to the target host.

The attack starts by having the attacker flood the switch with forged gratuitous ARP packets with the source MAC address being that of the target host and the destination MAC address being that of the attacker. The flooding process described here is different than the flooding process used in CAM table flooding. Since the destination MAC address of each flooding packet is the attacker's MAC address, the switch will not forward these packets to other ports, meaning they will not be seen by other hosts on the network. Now, a race condition exists because the target host will send packets too. The switch will see packets with the same source MAC address on two different ports and will constantly change the binding of the MAC address to the port. Remember that the switch binds a MAC address to a single port. If the attacker is fast enough, packets intended for the target host will be sent to the attacker's switch port and not the target host. The attacker has now stolen the target hosts' switch port. When a packet arrives at the attacker, the attacker performs an ARP request asking for the target hosts' IP address. Next, the attacker stops the flooding and waits for the ARP reply. When the attacker receives the reply, it means that the target hosts' switch port has been restored to its original binding. Now, the attacker can sniff the packet, then forward it to the target host and restart the flooding process waiting for new packets.

### Defence Against MAC Attacks

There are several ways to mitigate these packet sniffing attacks. The first of these actions is to enable port security on the switch. Port security is a feature found on high-end switches that ties a physical port to a MAC address. This allows you to either specify one or more MAC addresses for each port or learn a certain number of MAC addresses per port. A change in the specified MAC address for a port or flooding of a port can be controlled in many different ways through switch administration.

An important fact to know is that port security capabilities are dependant on the platform meaning that different switch manufacturers have different capabilities.

The second way to mitigate sniffing is through the use of static ARP entries. Static ARP entries are permanent entries that won’t time out from the ARP cache. This method does have a drawback though. Administrators have to create new entries on every host on the network every time a new host is connected, or when a network card is replaced.

The final method of defence is through detection. Intrusion detection systems can be configured to listen for high amounts of ARP traffic. There are also tools specifically designed to listen for ARP replies on networks. This method is prone to reporting false positives though. It should be remembered that detection is always an important step in mitigation.

## DHCP Attacks

### DHCP

Acronym of Dynamic Host Configuration Protocol. It is a network protocol used on IP networks where a DHCP server automatically assigns an IP address and other information to each host on the network so they can communicate efficiently with other endpoints.

In addition to the IP address, DHCP also assigns the subnet mask, a default gateway address, a domain name server (DNS) address and other pertinent configuration parameters. Request for Comments (RFC) 2131 and 2132 define DHCP as an Internet Engineering Task Force (IETF) - defined standard based on the BOOTP protocol.

When working with DHCP, it’s important to understand all of the components.  Below is a list of them and what they do:

* **DHCP server**: A networked device running the DCHP service that holds IP addresses and related configuration information. This is most typically a server or a router but could be anything that acts as a host, such as an SD-WAN appliance.

* **DHCP client**: The endpoint that receives configuration information from a DHCP server. This can be a computer, mobile device, IoT endpoint or anything else that requires connectivity to the network.  Most are configured to receive DHCP information by default.

* **IP address pool**: The range of addresses that are available to DHCP clients. Addresses are typically handed out sequentially from lowest to highest.

* **Subnet**: IP networks can be partitioned into segments known as subnets. Subnets help keep networks manageable.

* **Lease**: The length of time for which a DHCP client holds the IP address information. When a lease expires, the client must renew it.

* **DHCP relay**: A router or host that listens for client messages being broadcast on that network and then forwards them to a configured server. The server then sends responses back to the relay agent that passes them along to the client. This can be used to centralize DHCP servers instead of having a server on each subnet.

### DHCP Starvation Attack

DHCP starvation attack is an attack vector in which an attacker broadcasts a large number of DHCP requests packets with some spoofed MAC Address. DHCP starvation attack is called an attack on a computer network, in which the entire range of available and DHCP award IP addresses to a single client be registered. The automatic assignment of network addresses to other computers is thus made impossible. This is a sort of DHCP flooding attack or DHCP denial of service attack in which all the IP addresses of the IP pool will be consumed by the attacker and no new client will be able to connect to the DHCP server.

### Rogue DHCP Server Attack

A rogue DHCP server is a DHCP server which is on a network but is not authorized and permissible by a network administrator. This DHCP server is created by the attacker by which when all the IP addresses will be starved it will make the victim connect to its own malicious DHCP server into that same network.

### Preventing DHCP Starvation Attacks and Rogue Servers

Port security can currently prevent a DHCP starvation attack launched from a PC connected to a switch that is using a tool such as Gobbler. The inability of the attack to succeed is due more to a limitation of the tool than the mitigation offered by port security. The only reason such an attack fails is that Gobbler uses a different source MAC address to generate a different DHCP request and can be mitigated by port protection.

Rogue DHCP servers can be mitigated by the DHCP snooping feature. DHCP snooping is a feature available on switches. In order to defend against rogue DHCP servers, configure DHCP snooping on the port on which the valid DHCP server is connected. Once you configure DHCP snooping, it does not allow other ports on the switch to respond to DHCP discover packets sent by clients. Thus, even if an attacker manages to build a rogue DHCP server and connects to the switch, he or she cannot respond to DHCP discover packets.

## ARP Poisoning

### ARP

Address Resolution Protocol (ARP) is a network protocol used to find the hardware (MAC) address of a host from an IP address. ARP is used on Ethernet LANs because hosts that want to communicate with each other need to know their respective MAC addresses. It is a request-reply protocol; ARP request messages are used to request the MAC address, while ARP reply messages are used to send the requested MAC address.

### ARP Poisoning Attack

Address Resolution Protocol (ARP) poisoning or ARP spoofing is when an attacker sends falsified ARP messages over a local area network (LAN) to link an attacker's MAC address with the IP address of a legitimate computer or server on the network. Once the attacker's MAC address is linked to an authentic IP address, the attacker can receive any messages directed to the legitimate MAC address. As a result, the attacker can intercept, modify or block communicates to the legitimate MAC address.

ARP spoofing can be used for:

* Session Hijacking
* Denial-of-Service Attack
* Man-in-the-Middle Attack
* Package Sniffing
* Data Interception
* Connection Hijacking
* VoIP tapping
* Connection Reseting
* Stealing Passwords

### Preventing ARP spoofing Attack

* **Rely on Virtual Private Networks**: One way to prevent ARP spoofing from happening in the first place is to rely on Virtual Private Networks (VPNs). When you connect to the internet, you typically first connect to an Internet Service Provider (ISP) in order to connect to another website. However, when you use a VPN, you’re using an encrypted tunnel that largely blocks your activity from ARP spoofing hackers. Both the method by which you’re conducting the online activity and the data that goes through it is encrypted.

* **Use a Static ARP**: Creating a static ARP entry in your server can help reduce the risk of spoofing. If you have two hosts that regularly communicate with one another, setting up a static ARP entry creates a permanent entry in your ARP cache that can help add a layer of protection from spoofing.

* **Get a Detection Tool**: Even with ARP knowledge and techniques in place, it is not always possible to detect a spoofing attack. Hackers are becoming increasingly stealthy at remaining undetected and use new technologies and tools to stay ahead of their victims. Instead of strictly focusing on prevention, make sure you have a detection method in place. Using a third-party detection tool can help you see when a spoofing attack is happening so you can work on stopping it in its tracks.

* **Avoid Trust Relationships**: Some systems rely on IP trust relationships that will automatically connect to other devices in order to transmit and share information. However, you should completely avoid relying on IP trust relationships in your business. When your devices use IP addresses only to verify another machine or user's identity, it is easy for a hacker to infiltrate and spoof your ARP.

* **Set-Up Packet Filtering**: Some ARP attackers will send ARP packets across the LAN that contain an attacker’s MAC address and the victim’s IP address. Once the packets have been sent, an attacker can start receiving data or wait and remain relatively undetected as they ramp up to launch a follow-up attack. And when a malicious packet has infiltrated your system, it can be difficult to stop a follow-up attack and ensure your system is clean.

* **Look at Your Malware Monitoring Settings**: The antivirus and malware tools you already use may offer some recourse against ARP spoofing. Look at your malware monitoring settings and look for categories and selections that monitor for suspicious ARP traffic from endpoints. You should also enable any ARP spoofing prevention options and stop any endpoint processes that send suspicious ARP traffic.

* **Run Spoofing Attacks**: Identification and prevention are key to preventing spoofing attacks. However, you can increase your chances of staying safe and protecting your data by running your own spoofing attacks. Work with your security officer or IT team to run a spoofing attack to see if the techniques you’re using are enough to keep your system and data safe.

## Spoofing Attack

A MAC spoofing attack is where the intruder sniffs the network for valid MAC addresses and attempts to act as one of the valid MAC addresses. The intruder then presents itself as the default gateway and copies all of the data forwarded to the default gateway without being detected. This provides the intruder valuable details about applications in use and destination host IP addresses. This enables the spoofed CAM entry on the switch to be overwritten as well.

MAC address spoofing is used to impersonate legitimate devices, circumvent existing security mechanisms and to hide malicious intent. It can be an effective attack on defensive strategies where user and device identity provide a basis for access control policies.

In a typical MAC spoofing sequence, the attacker:

1. Identifies the MAC address of a device with authorized access to the network.
2. Connects a computer to the network, changing its MAC address to match (impersonate) that of the authorized device.
3. Exploits security controls based on static MAC addresses to access network segments, applications and sensitive information.

* **Non-Legitimate uses of MAC spoofing**: An example of an illegitimate use is when an attacker changes the MAC address of his station to enter a target network as an authorized user-taking over a computer’s identity that is authorized to function on the network. With this new identity, an attacker can wreak havoc: for example to launch denial of service attacks or to bypass access control mechanisms to advance more intrusion. An attacker might choose to change one’s MAC address in an attempt to evade network intrusion detection systems, to become invisible to security measures, allowing more time to act without detection.

* **Legitimate uses of MAC spoofing**: An example of a legitimate use of MAC spoofing is changing the function of a single computer from router to computer and back to router through MAC spoofing. If you only have a single public IP, you can only hook up one unit directly (PC or router). If one has two WAN IPs, the MAC address of the two devices must be different.

### How to Defend it

There are many tools and practices that organizations can employ to reduce the threat of spoofing attacks. Common measures that organizations can take for spoofing attack prevention include:

* **Packet filtering**: Packet filters inspect packets as they are transmitted across a network. Packet filters are useful in IP address spoofing attack prevention because they are capable of filtering out and blocking packets with conflicting source address information (packets from outside the network that show source addresses from inside the network and vice-versa).

* **Avoid trust relationships**: Organizations should develop protocols that rely on trust relationships as little as possible. It is significantly easier for attackers to run spoofing attacks when trust relationships are in place because trust relationships only use IP addresses for authentication.

* **Use spoofing detection software**: There are many programs available that help organizations detect spoofing attacks, particularly ARP Spoofing. These programs work by inspecting and certifying data before it is transmitted and blocking data that appears to be spoofed.

* **Use cryptographic network protocols**: Transport Layer Security (TLS), Secure Shell (SSH), HTTP Secure (HTTPS) and other secure communications protocols bolster spoofing attack prevention efforts by encrypting data before it is sent and authenticating data as it is received.

## DNS Poisoning

Attackers can poison a DNS cache by tricking DNS resolvers into caching false information, with the result that the resolver sends the wrong IP address to clients, and users attempting to navigate to a website will be directed to the wrong place.

DNS cache poisoning is the act of entering false information into a DNS cache so that DNS queries return an incorrect response and users are directed to the wrong websites. DNS cache poisoning is also known as 'DNS spoofing.' IP addresses are the 'room numbers' of the Internet, enabling web traffic to arrive in the right places. DNS resolver caches are the 'campus directory,' and when they store faulty information, traffic goes to the wrong places until the cached information is corrected. (Note that this does not actually disconnect the real websites from their real IP addresses.)

Because there is typically no way for DNS resolvers to verify the data in their caches, incorrect DNS information remains in the cache until the time to live (TTL) expires, or until it is removed manually. A number of vulnerabilities make DNS poisoning possible, but the chief problem is that DNS was built for a much smaller Internet and based on a principle of trust (much like BGP). A more secure DNS protocol called DNSSEC aims to solve some of these problems, but it has not been widely adopted yet.

Attackers can poison DNS caches by impersonating DNS nameservers, making a request to a DNS resolver, and then forging the reply when the DNS resolver queries a nameserver. This is possible because DNS servers use UDP instead of TCP, and because currently there is no verification for DNS information.

### Types of DNS Spoofing

#### Intranet DNS Spoofing

Intranet DSN spoofing is normally performed over a switched LAN by attackers with the help of ARP poisoning techniques. Attackers sniff the packets, extract the ID of DNS requests and reply with the fake IP translation directing the traffic to the malicious site. Attackers must be quick enough to respond before the legitimate DSN server resolves the query.

#### Internet DNS Spoofing

Internet DSN spoofing is performed by replacing the DNS configuration on the target machine. All DNS queries will be directed to a malicious DSN server controlled by the attacker, directing the traffic to malicious sites. Usually, internet DNS spoofing is performed by deploying a trojan or infecting the target.

#### Proxy Server DNS Poisoning

Similar to the previous one, proxy server DNS poisoning is performed by replacing the DNS configuration from the web browser of a target. All web queries will be directed to a malicious proxy server controlled by the attacker.

#### DNS Cache Poisoning

Users tend to use the DSN servers provided by Internet Service Providers (ISP) but, organisations tend to have their own servers to improve performance by caching frequently or previously generated queries. Attackers can add or alter entries in the DNS record cache to redirect users to malicious sites. When an internal DNS server is unable to validate a DNS response from an authoritative DSN server, it updates the entry locally to entertain the user requests.

### How to Defend it

#### Audit your DNS zones

First things first. The most important thing you will have to review apart from the DNS server main configuration is your DNS zone.

As time passes, we tend to forget about test domain names or subdomains that sometimes run outdated software or unrestricted areas vulnerable to attack, or if an A record is showing an internal/reserved intranet area by mistake.

Start exploring all your DNS public records using SecurityTrails: review all your zones, records and IPs. Audit your A, CNAME and MX records today. It is easy, as we have seen in past blog posts, like when we explored Google DNS or Microsoft subdomains.

#### Keep your DNS servers up-to-date

Running your own Name Servers gives you the ability to configure, test and try things that you may not be able to on private DNS servers like the ones your hosting provider gives you, or when you sign up for an account at Cloudflare.

When you decide to run your own DNS servers, probably using software like BIND, PowerDNS, NSD, or Microsoft DNS, and as the rest of the operating system software, it is crucial to keep these packages up-to-date in order to prevent service exploits targeting bugs and vulnerabilities.

Latest versions of all popular DNS servers include patches against known vulnerabilities, as well as support for security technologies like DNSSec and RRL (Response Rate Limiting) that are pretty useful in preventing DNS reflection attacks.

#### Hide BIND version

While some people cannot consider this as a security practice, security through obscurity is just another way to hide information from attackers when they are performing their initial security audit against your server.

#### Restrict Zone Transfers

A DNS zone transfer is just a copy of the DNS zone, and while this technique is often used by slave name servers to query master DNS servers, sometimes attackers can try to perform a DNS zone transfer in order to have a better understanding of your network topology.

One of the things that can be done to prevent these kinds of tricks is to restrict which DNS servers are allowed to perform a zone transfer or at least limit the allowed IP addresses that can make such requests.

That's why limiting zone transfers are one of the best ways to protect your precious DNS zone information.

####  Disable DNS recursion to prevent DNS poisoning attacks

DNS recursion is enabled by default on most Bind servers on all major Linux distributions, and this can lead to serious security issues, like DNS poisoning attacks, among others.

When DNS recursion is enabled on your server configuration, the DNS server allows recursive queries for other domains that are actually not real master zones located on the same name server, this simply allows third-party hosts to query the name servers as they want.

This setting can also increase your exposure to DNS amplification attacks, that is why you should always disable DNS recursion on your DNS servers if your plan is not to receive recursive DNS queries.

#### Use isolated DNS servers

Running your own DNS server is possible using a dedicated server or cloud where you host the rest of the web services like an application server, HTTP server or database server.

This is a common practice among small companies who often store all their server services in a single cPanel or Plesk box.

If you decide to put all your eggs in one basket, you must ensure that this box has a pretty solid server hardening for each daemon you are running, as well as for the applications running inside of the operating system.

Although the best you can do is to use your own dedicated DNS server environment, it does not matter if it is based on Cloud or Dedicated servers as long as it is 100% dedicated to DNS services only.

Having this DNS server isolated from the rest of your application servers will help to reduce the chance of getting hit by web application attacks.

Close all unneeded server ports, stop unwanted OS services, filter your traffic using a firewall, and only allow basic services such as SSH and the DNS server itself. This will help a lot to mitigate the chances of a DNS attack.

#### Use a DDOS mitigation provider

While small and midsize DOS and DDOS can be mitigated by tweaking network filters, HTTP services, and kernel response from the operating system, when a big DDOS comes after you, only a few Data Centers will be able to help their customers with a real anti-DDOS service.

If you run your own DNS servers and you are under massive DDOS attack, your usage in terms of bandwidth usage or packets per second will probably cause you a big downtime, if your service provider does not apply a null route to your IP addresses first.

That is why the best thing you can do is to hire an anti-DDOS specialized service like Cloudflare, Incapsula or Akamai to mitigate DDOS in the best possible way and keep your DNS servers secure and responding well at all times.

#### Two-Factor Authentication

If you are not running your own DNS servers and decide to use a third party DNS managed service like Cloudflare DNS or DNSMadeEasy, you can be sure their servers are pretty well secured.

However, none (not even their CEO) is safe from getting an account compromise, but the probabilities are very low, to be honest.

And, even in the worst case, an attacker can gain access to your username and password, but you can still have your account under control if you are using two-factor authentication.

## Sniffing Tools

There are som sniffers out there but, probably, the most well know is [Wireshark](https://www.wireshark.org). It is what is called a _network protocol analyser_. It is a free and open-source tool. And it allows multiple filter options when capturing traffic.

## Countermeasures

Best practices against sniffing include the following approaches to protect the network traffic:

* Using HTTPS instead of HTTP
* Using SFTP instead of FTP
* Use switch instead of hub
* Configure port-security
* Configure DHCP snooping
* Configure Dynamic ARP inspection
* Configure source guard
* Use sniffing detection tools to detect NIC functioning in a promiscuous mode
* Use strong encryption protocols

## Sniffing Detection Techniques

* **Ping method**: Ping technique can be used to detect sniffers but, been an older technique is not very reliable. A ping request is sent to the suspicious IP address, if it is running in promiscuous mode it will respond.

* **ARP method**: Using ARP, sniffers can be detected with the help of the cache. By sending a non-broadcast ARP package to the suspect, the MAC address will be cached if the NIC is running in promiscuous mode. Next step is to send a broadcast ping with spoofed address. If the machine is running in promiscuous mode, it will be able to reply to the packet only as it has already learned the actual MAC from the sniffed non-broadcast ARP packet.

* **Promiscuous Detection Tool**: Promiscuous detection tools like Nmap can also be used to detect NIC running in promiscuous mode.
