# CEH v10 - Certified Ethical Hacker

## 0. Disclaimer

This disclaimer is mainly designed to cover the content explained in this document Ethical Hacking.

> Any actions and or activities related to the material contained within this document is solely your responsibility. The misuse of the information in this document can result in criminal charges brought against the persons in question. The author will not be held responsible in the event any criminal charges be brought against any individuals misusing the information in this document to break the law.

> This document contains materials that can be potentially damaging or dangerous. If you do not fully understand something on this document, then do not use it or ask for proper advice! Refer to the laws in your province/country before accessing, using, or in any other way utilizing these materials. These materials are for educational and research purposes only. Do not attempt to violate the law with anything contained here. Neither the author of this material or anyone else affiliated in any way is going to accept responsibility for your actions.

> Any linked sites are not under the control of the author and the author is not responsible for the contents of any linked site or any link contained in a linked site, or any changes or updates to such sites. I am providing these links to you only as a convenience, and the inclusion of any link does not imply endorsement by me.

> The intention of the document is to provide a free, safe and legal training to the readers, for this reason, a user terms and services agreement has been set in place.

> Your usage of this document constitutes your agreement to the following terms.

> 1. All the information provided on this document is for educational purposes only. The document is no way responsible for any misuse of the information.

> 2. This document is related to Computer Security and not a site that promotes hacking /cracking/software piracy.

> 3. This document is meant for providing information on “Computer Security” and other related topics and is no way related to the terms “CRACKING” or “HACKING” (Unethical).

> 4. Few parts on this document may contain the information related to “Hacking Passwords” or “Hacking Email Accounts” (Or Similar terms). These are not the GUIDES of Hacking. They only provide information about the legal ways of retrieving the passwords. You shall not misuse the information to gain unauthorised access. However, you may try out these hacks on your computer at your own risk. Performing hack attempts (without permission) on computers that you do not own is illegal.

> 5. Any of the virus creation parts on this document provide a demonstration on coding simple viruses using high-level programming languages. These viruses are simple ones and cause no serious damage to the computer. However, I strongly insist that this information shall only be used to expand programming knowledge and not for causing malicious attacks.

> 6. All the information on this document is meant for developing Hacker Defense attitude among the users and help to prevent the hack attacks. I insist that this information shall not be used for causing any kind of damage directly or indirectly. However, you may try these codes on your computer at your own risk.

> 7. The word “Hack” or “Hacking” that is used on this site shall be regarded as “Ethical Hack” or “Ethical Hacking” respectively.

> 8. I am in favour of exploration, learning and testing always inside the law and I condemn any actions outside the law.

> 9. Some of the tricks provided by me may no longer work due to fixture in the bugs that enabled the exploits. I am not responsible for any direct or indirect damage caused due to the usage of the hacks provided on this site.

> 10. The document holds no responsibility for the contents found in the user comments since I do not monitor them. However, I may remove any sensitive information present in the user comments upon request.

> 11. I reserve the right to modify the Disclaimer at any time without notice.

> 12. I am not the vendors of any products (software, books etc.) that I recommend on this document. Hence I do not have any liability related to the products recommend by me. It is the responsibility of the buyers to contact the respective vendors for any queries related to the products.

## 1. Introduction to Ethical Hacking

TODO - Give an introduction and list the phase of an ethical hacking test. Some terminology and concepts. Maybe some description of security risks. TBD

## 2. Footprinting & Reconnaissance

The footprinting phase allows an attacker to gather information regarding internal and external security architectures. The collection of information also helps to:

* Identify possible vulnerabilities within a system.
* Reduce the focus of the attack.
* Discover obvious and non-obvious resources available.
* Identify possible vulnerabilities.
* Draw a network map.

This is the first phase of an ethical hacking test. The person performing the test is going to gather as much information as possible regarding the target or its infrastructure.

Possible sources of information or techniques can be:

* Publicly available information like social networks, newspapers or enterprise online resources like webpages.
* Employees' social and/or professional networks.
* Social engineering.
* Search engines.
* WHOIS and DNS registers.
* Competitive intelligence.
* Google hacking techniques.
* Emails.

The overall objective of this phase is to keep the interaction with the target at minimum levels and gathering information without any detection or alerting.

A step by step methodology can be:

1. Authorisation and scope definition of the assessment.
2. Footprinting using search engines.
3. Google hacking.
4. Footprinting using social network sites.
5. Website footprinting.
6. Email footprinting.
7. Competitive intelligence.
8. WHOIS footprinting.
9. Network footprinting.
10. Social engineering.
11. Document all findings.

### Footprinting using search engines

Search engines are an amazing tool to find information about a target and, also, they allow to gather this information without having real contact with the target. Pages like Google or Bing allow to search for any information and find and collect it from every available place on the Internet. Information like office addresses, founders, employee names, employee information, partners, competitors, websites and much more. Also, sometimes a good resource is the cache information these search engines store.

Once we have found the official websites, we can explore them to obtain multiple good information accessing the public parts of the webpages. But, we can explore the restricted parts of the webpages, this can be done by trial error or using available tools for this purpose like [Netcraft - Search Web by Domain](https://searchdns.netcraft.com). Another interesting tool they offer is the [Netcraft - Site report](https://sitereport.netcraft.com).

Let's see an example. We are going to use the [Tesla](https://www.tesla.com) because they have a [bug bounty program](https://www.tesla.com/about/security).

If we execute the Search Web by Domain tool, we can see the next result:

![Tesla Netcraft](img/001_netcraft_tesla.png)

### Collecting cocation information