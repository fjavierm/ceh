# Session Hijacking

Session hijacking is basically to hijack sessions by intercepting the communication between hosts. Attackers usually intercept the communication to obtain the roles of authenticated users or for the intention of Man-in-the-Middle attacks.

To be able to use restricted resources, legitimate users need to go through an authentication process. When the authentication is performed successfully a session is created allowing the users to interact with the system. At this point, attackers try to take advantage of this session placing themselves between the authenticated user and the system and hijacking the existing session. Upon successful hijacking, attackers can start monitoring traffic and get the role of the legitimate user.

Session hijacking becomes successful because of weak session IDs or non-blocking upon receiving an invalid session ID.

## Session Hijacking Techniques

The different hijacking techniques are classified as follows:

* **Stealing**: This category includes the different techniques of stealing session IDs, for example, using network sniffing, trojans or any other means.

* **Guessing**: This category includes tricks and techniques used to guess session IDs, like observing the variable part of a session trying to guess a pattern or calculating a valid session ID by figuring out the generation sequence.

* **Brute-Forcing**: This category covers all the brute-force guessings trying to figure out a valid session, it does not matter if they are done blindly or with some information about the session range.

## Session Hijacking Process

Obviously, there are as many ways of doing this as attacker are out there trying to do it but, all the attends has in common a series of actions:

* **Sniffing**: Attackers try to place themselves between the victim and the host in order to sniff packets.

* **Monitoring**: Monitoring the packet flow between the victim and the target.

* **Session desynchronisation**: The process of breaking the connection between the victim and the target.

* **Session ID**: Attackers take control of a session predicting the session ID.

* **Command injection**: After successfully taking control over the session, the attacker starts injecting commands.

## Types of Session Hijacking

* **Active Attack**: Active attacks are the ones where attackers interact with the victim's machines by sending some king of packets to interrupt the connection with the host and take advantage of this situation replacing the user.

* **Passive Attacks**: Passive attacks are the ones where attacker just stay around monitoring or sniffing the traffic in a network and they do not have interaction with the victim's machine.

## Session Hijacking and the OSI Model

* **Network-level attacks**: This kind of attacks hijack network-level sessions as TCP and UDP session. 

* **Application-level attacks**: This kind of attacks hijack application-level sessions like HTTPS sessions.

### Hijacking vs Spoofing

The major difference between spoofing and hijacking is the state of the session.

In spoofing, attackers do not have any active session, they create a new one taking advantage of the information they have been able to collect from different sources.

In hijacking, attackers take control of existing and active sessions belonging to legitimate users but, without initiating any new session.

## Application-Level Session Hijacking

In this type of hijacking, attackers try to focus on applications users have access to and are interacting with. In general, all the applications manage a type of session to keep track of what users are doing or to manage properly the access to the different resource the offer.

The purpose of attackers is to pass as legitimate users to achieve access to these resources and be able to use the application as if they were indeed the user they have supplanted.

### Compromising Session IDs Using Sniffing

Attackers can compromise a session just by sniffing a network and grabbing the session IDs or tokens in transit. Once found it, they can use it to supplant the legitimate user.

### Compromising Session IDs by Token Prediction

Token prediction is based on observability, attackers sit there capturing as much session IDs or tokens they can to infer how they are generated and should be the next one. This observation helps them to figure out the static and variable part of the sessions.

### Compromising Session IDs Using Man-in-the-Middle Attacks

The MitM attack places the attacker between the victim and the target with the attacker been able to utilise the victim's session.

### Compromising Session IDs Using Man-in-the-Browser Attacks

This attack requires a trojan already placed in the victim's computer to alter the proxy settings and redirecting the traffic or to intercept the process between the browser and its security mechanism.

### Compromising Session IDs Using Client-Side Attacks

A very vulnerable point where credentials can be compromised is the client-side i.e. JavaScript attacks.

#### Cross-site Scripting

Cross-Site Scripting (XSS) attacks are a type of injection, in which malicious scripts are injected into otherwise benign and trusted websites. XSS attacks occur when an attacker uses a web application to send malicious code, generally in the form of a browser side script, to a different end-user. Flaws that allow these attacks to succeed are quite widespread and occur anywhere a web application uses input from a user within the output it generates without validating or encoding it.

Some recommendations to prevent this type of attacks can be found at the [OWASP](https://owasp.org) project [here](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html).

#### Cross-site Request Forgery Attack

Cross-Site Request Forgery (CSRF) is an attack that forces an end user to execute unwanted actions on a web application in which they are currently authenticated. CSRF attacks specifically target state-changing requests, not theft of data, since the attacker has no way to see the response to the forged request. With a little help of social engineering (such as sending a link via email or chat), an attacker may trick the users of a web application into executing actions of the attacker’s choosing. If the victim is a normal user, a successful CSRF attack can force the user to perform state-changing requests like transferring funds, changing their email address, and so forth. If the victim is an administrative account, CSRF can compromise the entire web application.

### Session Replay Attack

A replay attack occurs when cybercriminals eavesdrop on secure network communication, intercept it, and then fraudulently delay or resend it to misdirect receivers into doing what attackers want. The added danger of replay attacks is that an attacker does not even need advanced skills to decrypt a message after capturing it from the network. The attack could be successful simply by resending the whole thing.

### Session Fixation Attack

Session fixation is a web attack technique. Attackers trick users into using a specific session ID. After users log in to the web application using the provided session ID, attackers use this valid session ID to gain access to the user accounts.

A typical session fixation attack is performed as follows:

1. An attacker accesses the web application login page and receives a session identifier generated by the web application. This step is not necessary if the web application accepts arbitrary session IDs.

2. An attacker uses an additional technique such as CRLF Injection, man-in-the-middle attack, social engineering, etc., and gets the victim to use the provided session identifier. This depends on how the web application handles session IDs. It may be as simple as sending a malicious URL but may also require the attacker to create a fake website.

3. A victim accesses the web application login page and logs in to the application. After authenticating, the web application treats anyone who uses this session ID as if they were this user.

4. An attacker uses the session identifier to access the web application, take over the user session, and impersonate the victim. Further actions depend on the attacker and web application functionality.

## Network-Level Session Hijacking

In this type of hijacking, attackers try to focus on the transport layer and internet layer protocols.

### TCP/IP Hijacking

TCP/IP hijacking is a type of man-in-the-middle attack. Attackers can determine the IP addresses of the two-session participants, make one of them inaccessible using a DoS attack, and connect to the other by spoofing the network ID of the former.

### Source Routing

Normally, the route a packet takes from its source to its destination is determined by the routers between the source and destination. The packet itself only says where it wants to go, the destination address, and nothing about how it expects to get there.

There is an optional way for the sender of a packet to include information in the packet that tells the route the packet should take to get to its destination.

Source routing can be strict or loose. Strict source routing lets a manager specify the path through all the routers to the destination. Return responses use the same path in reverse. Loose source routing lets managers specify an address that the packet must pass through on its way to the destination. It is loose source routing that aids an attacker.

A remote attacker might seek to access a Unix system protected with TCP wrappers, or a Windows NT Internet Information Server (IIS) protected by an access list based on source addresses. If the attacker simply spoofs one of the permitted source addresses, the attacker may never get a response. However, if the attacker both spoofs an address and sets the loose-source-routing option to force the response to return to the attacker's network, the attack can succeed.

### RST Hijacking

RST hijacking involves injecting an authentic-looking reset (RST) packet using a spoofed source address and predicting the acknowledgement number. Attackers can reset the victim's connection if it uses an accurate acknowledgement number. The victim believes that the source actually sent the reset packet and resets the connection.

RST Hijacking can be carried out using a packet crafting tool and TCP/IP analysis tool. 

### Blind Hijacking

In this type of session hijacking, attackers do not see the target host's response to the transmitted requests. Attacker, being in a man-in-the-middle position, can only introduce malicious injections into the victim's data packets, blindly guessing their sequence numbers and without receiving confirmation of success. Nevertheless, blind hijacking can be used, for instance, to send a command to change/reset a password.

### Force ICMP and ARP Spoofing

A man-in-the-middle attack can also be performed by using forced ICMP packets and ARP spoofing techniques. Forced ICMP packets such as destination unavailable or high latency messages are sent to fool the victim.

### UDP Hijacking

Since UDP does not use packet sequencing and synchronizing; it is easier than TCP to hijack UDP session. 

Attackers have simply to forge a server reply to a client UDP request before the server can respond. If sniffing is used then it will be easier to control the traffic generating from the side of the server and thus restricting the server's reply to the client in the first place.

## Countermeasures

The mitigation of these types of attacks involves the combination of different manual and automatic techniques, procedures or tools.

Deployment of defence-in-depth technologies, network monitoring devices like intrusion detection systems (IDSs) and intrusion prevention systems (IPSs) are part of the automated solutions.

On the other side, packet sniffing tools can be used to manually analyse the traffic and detect anomalies and possible attacks.

One of the most important things to protect environments and users would be to encrypt sessions and communications using SSH, using HTTPS instead of HTTP, using random lengthy strings as session IDs, session timeouts and strong authentication systems as Kerberos.

A very standard solution is the use of IPSec and SSL to establish strong protection against session hijacking.

### IPSec

IPsec is a framework of related protocols that secure communications at the network or packet processing layer. It can be used to protect one or more data flows between peers. IPsec enables data confidentiality, integrity, origin authentication and anti-replay.

* **Confidentiality**: IPSec uses encryption protocols namely AES, DES, and 3DESfor providing confidentiality.

* **Integrity**: IPSec uses hashing protocols (MD5 and SHA) to provide integrity. Hashed Message Authentication (HMAC) can also be used for checking the data integrity.

* **Authentication algorithms**: RSA digital signatures and pre-shared keys (PSK) are two methods used for authentication purposes.

IPsec makes use of tunnelling. The data packets that we define sensitive or interesting are sent through the tunnel securely. By defining the characteristics of the tunnel, the security protection measures of sensitive packets are defined. IPsec offers numerous technologies and encryption modes. But its working can be broken into five major steps. A brief overview is given below:

* **Interesting traffic initiation**: The sensitive traffic that needs to be monitored is deemed interesting. After deciding about the traffic, the security policy is implemented on the configuration interface for the peers. For example, in Cisco routers, access lists can be used to make decisions about encryption of packets by way of crypto map sets. The lists can be assigned to the policy stating that if the packets are permitted then they must be encrypted else send the unencrypted data packet. When this traffic transits the IPsec client, the IKE phase one is triggered.

* **IKE phase one**: In this step, first the IPsec peers are authenticated thus protecting the identities of the peers. Then the Internet Key Exchange (IKE) Security Associations (SA) policy is negotiated among the peers. This results in both the parties to have a shared secret matching key that helps in the IKE phase two. Also, in this phase, there is setting up of a secure tunnel through which the exchange of information for phase two will occur. This phase has two operating modes:

    * **Main mode**: There are three exchanges among the initiator and the receiver. In the first exchange, algorithms and hashes are exchanged. The second exchange is responsible for generations of shared secret keying using Diffie-Hellman exchange. The last exchange is for the verification of the other side’s identity. All three of these exchanges are bi-directional.

    * **Aggressive mode**: There are fewer exchanges in this mode. All the required information is squeezed making it faster to use. The only trouble is that information is shared before there is a secure channel making this mode vulnerable.

* **IKE phase two**: This phase negotiates information for IPsec SA parameters through the IKE SA. Here as well IPsec policies are shared and then establish IPsec SAs. There is only a single-mode (quick mode) in this phase. It exchanges nonce providing replay protection. These nonces generate new shared secret key material. If the lifetime for IPsec expires, it can renegotiate a new SA.

* **Data transfer**: Here the data is safely and securely transmitted through the IPsec tunnel. The sent packets are encrypted and decrypted using the specified encryption in the IPsec SAs.

* **Tunnel termination**: The tunnel may terminate by either deletion or by time out. Time out occurs when the specified time (sec) has passed or when a specified number of bytes will have passed through the tunnel.

IPSec consists of two main protocols:

#### Authentication Header

In the Authentication Header (AH) protocol, IP headers and data payloads are hashed. From this hash, a new AH header is built which is appended to the packet. This new packet is transmitted via router where the router hashes the header and the payload. Both the hashes need to be exactly matched. Even a single bit is changed, the AH header will not match.

#### Encapsulating Security Payload

This Encapsulating Security Payload (ESP) protocol provides encryption and integrity to the data packets. The ESP is added after the standard IP header. As it contains the standard IP header, it can be routed easily with standard IP devices. This makes it backwards-compatible with IP routers and even those devices that were not designed to operate with IPsec. ESP is performed at the IP packet layer. It contains six parts of which two parts are only authenticated (Security Parameter Index, Sequence Number) whereas the rest of the four parts are encrypted during transmission (Payload Data, Padding, Pad Length and Next Header). It supports multiple encryption protocols and is up to the user to decide which one to opt.

#### Encryption Technologies

There are two encryption modes available for IPsec. Both modes have their own uses and should be used with caution depending upon the solution.

* **Tunnel mode**: This encrypts both the payload and the header. IPsec in tunnel mode is used when the destination of the packet is different than the security termination point. The most common use of this mode is between gateways or from end station to gateway. The gateway serves as a proxy for the hosts. So when the origin of the packets differs from the device that is providing security, tunnel mode is used.

* **Transport mode**: In this encryption mode, only the data portion of each packet is encrypted. This mode is applicable between end stations or between end station and gateway.
