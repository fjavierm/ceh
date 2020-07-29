# Denial of Service

Denial of Service (DoS) and Distributed Denial of Service (DDoS) are very common attacks nowadays.

The purpose of the attack is either denied access, reduce the functionality or prevent the access to resources even to the legitimate users.

The attack is based on the generation of large amounts of requests targeting a system. This large amount of incoming requests overloads the system capacity to respond resulting in a denial of services to all the users of that service.

There are a number of different ways that DoS attacks can be used. These include the following:

* **Buffer overflow attacks**: This type of attack is the most common DOS attack experienced. Under this attack the attacker overloads a network address with traffic so that it is put out of use.

* **Ping of Death or ICMP flood**: An ICMP flood attack is used to take unconfigured or misconfigured network devices and uses them to send spoof packets to ping every computer within the network. This is also known as a ping of death (POD) attack.

* **SYN flood**: SYN flood attacks send requests to connect to a server but don’t complete the handshake. The end result is that the network becomes inundated with connection requests that prevent anyone from connecting to the network.

* **Teardrop Attack**: During a teardrop DOS attack an attacker sends IP data packet fragments to a network. The network then attempts to recompile these fragments into their original packets. The process of compiling these fragments exhausts the system and it ends up crashing. It crashes because the fields are designed to confuse the system so that it can not put them back together.

During a DoS attack, multiple systems target a single system with a DoS attack. The targeted network is then bombarded with packets from multiple locations. By using multiple locations to attack the system attackers can put the system offline more easily. The reason for this is that there is a larger number of machines at the attackers’ disposal and it becomes difficult for the victim to pinpoint the origin of the attack.

The DDoS attack is the next step. A DDoS attack is one of the most common types of DoS attack in use today. The attackers use a network of devices called a botnet controlled by them (previously infected) to launch the attack. Botnets can be made up of anywhere between a handful of bots to hundreds of different bots. This can make extremely difficult for defenders to deal with this kind of attack.

## Attack Techniques

### Basic Categories

There are a number of broad categories that DOS/DDoS attacks fall into for taking networks offline:

* **Volumetric attacks**: Volumetric attacks are classified as any form of attack where a network's bandwidth resources are deliberately consumed by an attacker. Once network bandwidth has been consumed it is unavailable to legitimate devices and users within the network. Volumetric attacks occur when the attacker floods network devices with ICMP echo requests until there is no more bandwidth available.

* **Fragmentation attacks**: Fragmentation attacks are any kind of attack that forces a network to reassemble manipulated packets. During a fragmentation attack the attacker sends manipulated packets to a network so that once the network tries to reassemble them, they can’t be reassembled. This is because the packets have more packet header information than is permitted. The end result is packet headers which are too large to reassemble in bulk.

* **TCP-State exhaustion attacks**: In a TCP-State Exhaustion attack the attacker targets a web server or firewall in an attempt to limit the number of connections that they can make. The idea behind this style of attack is to push the device to the limit of the number of concurrent connections.

* **Application layer attacks**: Application layer or Layer 7 attacks are attacks that target applications or servers in an attempt to use up resources by creating as many processes and transactions possible. Application layer attacks are particularly difficult to detect and address because they don’t need many machines to launch an attack.

### Attack Techniques

* **Bandwidth attacks**: Bandwitch attacks require multiple sources to generate a request to overload the target. Using a single machine makes impossible to generate enough traffic to overwhelm a service, this is why a DDoS attack is necessary where, the more machines, called _Zombies_ or _bots_, are used, the more possibilities have the attack to succeed. The goal of a bandwidth attack is to consume the bandwidth completely.

* **Service request floods**: Similar to the previous one, attackers generate enough requests towards a service web to overload it and make the service to deny legitimate connections too.

* **SYN attack/Flooding**: In this attacks the three-way handshake is exploited. Attackers generate a lot of SYN request with a fake source IP. When the target machine responses, keeps waiting for the ACK to arrive but, because the IP was a fake one not reachable by the target, the waiting period ties up a connection "listen to queue" to the system. The waiting period can be up to 75 seconds.

* **ICMP flood attacks**: In this attack, attackers send ICMP packages and, all this requests and responses, without waiting for the responses, overflood the resources of the network device.

* **Peer-to-Peer attacks**: Peer to peer networks are deployed among a large number of hosts, once one of the network hubs is compromised it becomes easy for the attacker to launch a DDoS attack.

* **Permanent DoS attacks (PDoS)**: In this attack instead of focusing on services, attackers are going to focus on hardware sabotage, making necessary to replace or reinstall the hardware involved on the attack. Considering the difficult access or remote locations of this hardware, this can cause very permanent damage. PDoS attack method is known as 'Phlashing' or 'Bricking' with one sole purpose, to infect and permanently damage a device. Specifically, nowadays, phlashing attacks are targeting the Internet of Things (IoT) connected devices to exploit known vulnerabilities in IoT device security and software.

* **Application-level flood attacks**: This type of attack target applications servers or client computer running applications taking advantage of exiting vulnerabilities and exploiting them to bypass the access controls.

* **Distributed reflection DoS (DRDoS)**: Using spoofing mechanisms attackers involve intermediary or secondary victims in the process of the attack.

## Botnets

A botnet refers to a group of computers which have been infected by malware and have come under the control of a malicious actor. The term botnet is a portmanteau from the words robot and network and each infected device is called a bot. Botnets can be designed to accomplish illegal or malicious tasks including sending spam, stealing data, ransomware, fraudulently clicking on ads or distributed denial-of-service (DDoS) attacks.

The barrier to creating a botnet is also low enough to make it a lucrative business for some software developers, especially in geographic locations where regulation and law enforcement are limited. This combination has led to a proliferation of online services offering attack-for-hire.

A core characteristic of a botnet is the ability to receive updated instructions from the bot master (_attackers system_). The ability to communicate with each bot in the network allows the attacker to alternate attack vectors, change the targeted IP address, terminate an attack, and other customized actions. Botnet designs vary, but the control structures can be broken down into two general categories:

### The client/server botnet model

The client/server model mimics the traditional remote workstation workflow where each individual machine connects to a centralized server (or a small number of centralized servers) in order to access information. In this model each bot will connect to a command-and-control centre (CnC) resource like a web domain or an IRC channel in order to receive instructions. By using these centralized repositories to serve up new commands for the botnet, an attacker simply needs to modify the source material that each botnet consumes from a command centre in order to update instructions to the infected machines. The centralized server in control of the botnet may be a device owned and operated by the attacker, or it may be an infected device.

A number of popular centralized botnet topologies have been observed, including:

* Star Network Topology
* Multi-Server Network Topology
* Hierarchical Network Topology

### The peer-to-peer botnet model

To circumvent the vulnerabilities of the client/server model, botnets have more recently been designed using components of decentralized peer-to-peer filesharing. Embedding the control structure inside the botnet eliminates the single-point-of-failure present in a botnet with a centralized server, making mitigation efforts more difficult. P2P bots can be both clients and command centres, working hand-in-hand with their neighbouring nodes to propagate data.

Peer to peer botnets maintain a list of trusted computers with which they can give and receive communications and update their malware. By limiting the number of other machines the bot connects to, each bot is only exposed to adjacent devices, making it harder to track and more difficult to mitigate. Lacking a centralized command server makes a peer-to-peer botnet more vulnerable to control by someone other than the botnet’s creator.

### Propagation of Malicious Code

There are three most common ways to propagate malicious code. These methods are:

* **Central source propagation**: Requires a central source where the attack toolkit is installed. When an attacker gains access to a machine, it connects to this central system and transfers the toolkit.

* **Back-Chaining Propagation**: In this case the attack toolkit is installed in the attacker's machine and when they gain access to a machine, they just connect back and download the toolkit to the vulnerable machine.

* **Autonomous propagation**: In this case, attackers send malicious code to the vulnerable machine, this malicious code installs the attack toolkit and search for other vulnerable machines.

There are numerous bot toolkits and attack tools out there.

## Countermeasures

There are several ways to detect and prevent DoS/DDoS attacks. The following are common security techniques:

### Activity Profiling

Monitoring a profiling a network is a very easy way of detecting these types of attacks due to the traffic increment that we can compare with the average traffic seen usually.

### Wavelet Analysis

Wavelet-based signal analysis is an automated process of detecting attacks by analysing input signals. This automated detection is used to detect volume-based anomalies. Wavelet analysis evaluates the traffic and filters on a certain scale whereas adaptative threshold techniques are used to detect the attacks.

### Sequencial Change-Point Detection

Change-Point detection is an algorithm which is used to detect DoS attacks. The detection technique uses non-parametric algorithms to detect traffic patterns. This method required very low computational overhead hence efficient and immune to attacks resulting in high accuracy.

### Attack Countermeasures

* Protect secondary victims
* Detect and neutralise handlers
* Enable ingress and egress filtering
* Deflect attacks by diverting it to honeypots
* Mitigate attacks by load balancing
* Mitigate attacks disabling unnecessary services
* Using anti-malware
* Enable router throttling
* Using a reverse proxy
* Absorbing the attack
* Intrusion detection systems

### Techniques to Defend Against Botnets

* **RFC 3704 filtering**: RFC 3704 is designed for _ingress_ filtering for multi-homed networks to limit DDoS attacks. It denies the traffic with a spoofed address to access the network and ensure the trace to its source.

* **Cisco IPS Source IP Reputation Filtering**: Ensured by Cisco devices, filter traffic based on a reputation score and other factors. Devices collect real-time information and, in addition, they receive threat intelligence updates from Cisco.

* **Black Hole Filtering**: This process silently drops incoming or outcoming traffic so that the source is not notified about discarding of the packet. Remote Triggered Black Hole Filtering is a routing technique to mitigate DoS attacks by using Border Gateway Protocol. 

* **Enabling TCP Intercept on Cisco IOS Software**: TCP Intercept command is used to protect TCP servers from TCP SYN flooding attacks. It prevents the attack by intercepting and validating TPC connections. These connections are matched against extended access lists avoiding the connection to reach the destination server.
