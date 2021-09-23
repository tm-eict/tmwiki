---
title: Woorden
description: 
published: true
date: 2021-06-01T20:19:42.678Z
tags: 
editor: markdown
dateCreated: 2021-05-30T09:23:55.968Z
---

# Woorden

| Begrippen | Voluit | Betekenis |
| -- | -- | -- |
| ACL | Acces Control List | Permit or not permit the flow of data, based on security settings |
| NIC | Network Interface Card | Specialized ports on an internetworking device that connect to individual networks |
| LAN | Local Area Network | |
| WAN | Wide Area Network | |
| WLAN | Wireless LAN | |
| SAN | Storage Area Network | |
| QoS | Quality of Service | Prioritize some packets over others |
| NAT | Network Address Translation | Mask private IP addresses to one public IP address |
| CIDR | Classless Inter-Domain Routing | just a prefix for subnet like /24 |
| OSI | Open Systems Interconnection | |
| CSMA | Carrier Sense Multiple Access | Checks to see if it may use the data lines, no collisions etc |
| CSMA/CD | /Collision Detection | |
| CSMA/CA | /Collision Avoidance | Used in wireless networks, notifications can collide but never data |
| Crosstalk |  | Door inferentie kan je de andere lijnen horen. |
| BIA | Burned In Address | Mac address |

## Cables

| Afkorting | Voluit | Betekenis |
| -- | -- | -- |
| UTP | Unshielded Twisted-Pair | UTP's zijn het populairst. TP's zorgen voor betere bescherming tegen interferentie. |
| STP | (Braided) Shielded Twisted-Pair | Extra bescherming tegen inkomende interferentie. (extra ground pin) |
| FTP | Foil Shielded Twisted-Pair | |
| SMF | Singlemode [Fiber](https://tmwiki.be/en/Network_Fundamentals/samenvatting#fiber-optic) | Kleine core, minder dispersion, lange afstanden, laser |
| MMF | Multimode [Fiber](https://tmwiki.be/en/Network_Fundamentals/samenvatting#fiber-optic) | Grotere core, meer dispersion, minder maar toch lange afstanden, LEDs |

## Casts

| Cast | Betekenis |
| -- | -- |
| Unicast | One to one |
| Multicast | One to many |
| Broadcast | One to all (not present in ipv6) |
| Anycast | One to closest (lowest routing cost) |

## Protocollen

| Protocol | Voluit | Betekenis | Port |
| -- | -- | -- | -- |
| TCP | Transmission Control Protocol | Session-based, betrouwbaar data versturen |  |
| UDP | User Datagram Protocol | Stateless and not reliable, no overhead, fast |  |
| ICMP | Internet Control Message Protocol | ping, administration and control |  |
| IP | Internet Protocol |  |  |
| ARP | Address Resolution Protocol | Resolves IP address to MAC address by doing a broadcast |  |
| HTTP(S) | Hypertext Transfer Protocol (Secure) |  | 80 (443) |
| (T)FTP | (Trivial) File Transfer Protocol port |  | 20 (69) |
| DHCP | Dynamic Host Configuration Protocol | Lease IP addresses | 67 server, 68 client (UDP) |
| DNS | Domain Name System/Server |  | 53 |
| NAT | Network Address Translation | Mask private IP addresses to one public IP address |  |
| SMTP | Simple Mail Transfer Protocol | Send mails |  |
| POP3 | Post office protocol | Receive mails |  |
| IMAP | Post office protocol | Receive mails |  |
| Telnet |  | Session with shell, send commands | 23 |
| OSPF | | (For routers:) find routes of other routers, dynamicly make maps |  |
| EIGRP | | (For hosts:) dynamicly get ip for host |  |
| LLC | Logic Link Control | |


