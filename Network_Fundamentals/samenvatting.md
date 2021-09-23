---
title: Samenvatting
description: 
published: true
date: 2021-06-01T12:32:31.880Z
tags: 
editor: markdown
dateCreated: 2021-05-30T09:03:23.123Z
---

# Gezamenlijke samenvatting
## Les 1
### Ways to communicate
- peer-to-peer
	- Every client is connect to every other client
- Client-server
	- Every client is connected to one device (the server)

### Network types
#### LAN (Local Area Network)
- small geographical area
- Single organiztaion
- High speed
- Behing a firewall

#### WAN (Wide Area Network)
- Wide geographical area
- multiple service providers
- Slower links between LANs (link = routes)

#### Internetwork
- An internetwork is defined as aglobal mesh of interconnected networks (WANs + LANs)

#### Converged network
- Everything on one network (voice, video, data, ....)

#### Circuit Switched network
- Temporary direct physical connection (old telephone lines)
- One path per connection

#### Packet Switched Network
- Packt contains address 
- Muliptle paths to destinations
- Lost packets can be retransmitted
- Packets can arrive out of order/on different times

### Reliable Network
#### Fault tolerance
- Limits the impact of a hardware or software failure
- Recovers quickly when a failure occurs
- Depend on redundant links (links = routes)
	- Redundant connections allow for alternative paths if a path fails

#### Scalability
- Expand quickly for extra support

#### Quality of Service (QoS)
- Some services require consistent quality and uninterrupted delivery
- Defining which types of data packets must be delivered at the expense of other types of packets that can be delayed or dropped. 
- Classify applications in categoriesbased on specific quality of service requirements
- Combination of communication characteristics and the relative importance

#### Security
- Physical protection
- Firewall
- Confidentiality
	- User authentication
	- Strong password
	- Data encryption
- Communication integrity
	- data and source integrity 
	- Digital signatures, hashing algorithms and check sum
- Availability

## les 2
See: [ipv4](/en/Network_Fundamentals/ipv4)

## les 3
See: [commands](/en/Network_Fundamentals/commands)

# Peter's samenvatting

## Reliable network

- **Fault Tolerance**
  - Limits the impact of hardware or software failure
  - Recovers quickly
  - Depend on redundant links
- **Scalability**
  - Expand quickly for extra support
- **Quality of Service**
  - Some services require consistent quality and uninterrupted delivery
- **Security**
  - Physical protection
  - Firewall
  - Confidentiality
  - Communication integrity
  - Availability

## Protocols

### casts

unicast: one to one
multicast: one to many
broadcast: one to all
anycast: one to closest

DNS
DHCP
NAT
NAT: Network Address Translation

### IP Protocols

- TCP: Transport Control Protocols
  - Session
  - Every msg is ACK
- UDP: User Diagram Protocol
  - Stateless and not reliable
  - Faster/less overhead
  - real-time
- ICMP: Internet Control Message Protocol
  - ping
  - Administration and control

### Others

- IP: Internet Protocol
- ARP: Address Resolution Protocol
  - Resolves IP address to MAC address by doing a broadcast
- HTTP(S): Hypertext Transfer Protocol (Secure) port 80/443
- (T)FTP: (Trivial) File Transfer Protocol port 20/69
- DHCP: Dynamic Host Configuration Protocol
- DNS: Domain Name System/Server port 53
- NAT: Network Address Translation (eg: Router to internet)
- SMTP, POP, IMAP: Mail protocols
- Telnet port 23

## Ethernet cables and transmission media

### Copper cables/media

![RJ-45 copper cable](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d5/Pkuczynski_RJ-45_patchcord.jpg/1280px-Pkuczynski_RJ-45_patchcord.jpg)
Connection port: RJ45 port (also called LAN port)  
UTP/FTP/STP cables  
UTP: Unshielded Twisted-Pair (most common)  
STP: Shielded Twisted-Pair (expensive)  
Coax cable (TV)  
Twisted pairs (4 times 2 twisted cables)  
Ethernet max 100m  
Verschil tussen cat 5 e5 en 6 is korter twisten. -> minder interference.

Susceptible to interference from EMI (Electromagnetic interference), RFI (radio frequency interference) and crosstalk (wires next to each other can cause magnetic fields to carry over, eg. two telephone cables next to each other and you can hear them talk over the other line).

### Fiber optic

Flexibel thin strand of pure glass/silica.  
Transmits data with light pulses.
Fiber optic can reach much further distances (100 000 meter from 100 m in copper) and higher bandwidths (up to 100 Gbps).  
It is also immune to interference. However fiber optic is **very expensive compared to copper.**

![single vs multimode](https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fpeakoptical.com%2Fwp-content%2Fuploads%2F2018%2F06%2Fmilti-single-modes.png&f=1&nofb=1)

**Singlemode:**

- Small core
- Less dispersion
- Suited for very long distance
- Lasers as light source
- Commonly used with campus backbones for distances of *several thousand* meter

**Multimode:**

- Larger core
- Greater dispersion -> loss of signal
- Suited for long distances (less than single)
- LEDs as light source
- Common for LANs, 100s meters, within campus

> Multimode does **NOT** carry more bandwidth, in fact single mode has a higher theoritical bandwidth. It is simply more suited for LANs and allows other light sources.
{.is-warning}


### Wireless/WLAN

Can cover large areas but is susceptible to interference and materials blocking its signal (limiting the range). Security is also a downside since you don't need physical access.

2.4Ghz: Lower frequency, lower bandwidth, higher range, 11 channels(?)
5GHz: Higher frequency, higher bandwidth, less range, 25 channels(?)

## Bandwidth

Throughput is a measurement of data across media over a period of time.  
Throughput gets bottlenecked by the slowest link.
  
Goodput is the actual useful data:  
`Goodput = throughput - traffic overhead` (sessions, ACKs, encapsulation)  
Goodput is most interesting for end users.

## OSI-model

### Datalink layer

- LLC: Logical Link Control
- MAC: Media Access Control (lowest data link sublayer)
  - Data Encapsulation
    - Frame assembly before transmission and frame disassembly upon reception
    - Header and trailer to network layer
  - Communicates directly with physical layer

## Data-collision

- Controlled Access  (token ring,  FDDI)
  - Needs method of checking wether busy or not
- Contention-based Access
  - Device tries to send, if busy waits, if not, sends.
    - Chance of collision when to devices send at same time -> needs to be resent.
  - No extra mechanism needed to check whether the line is busy

Contention-based access is used for Ethernet.

## MAC

MAC address is burned into a device (NIC). It cannot be changed (stored in ROM). On boot-up this address is copied in RAM. The operating system can 'spoof' a MAC address easily.

Broadcast MAC: FF-FF-FF-FF-FF-FF

## Ethernet frame

- Source MAC address
  - Identifier of NIC/interface
- Length/type
  - Field contains exact length of frame's data field
  - Network layer protocol
- Data
  - Contains data from a higher layer (commonly ipv4 packet)
- Pad
  - Frames are atleast 64 bytes long, padding can be used for small packets (adding extra size to the fram till minimum is reached)
- Frame Check Sequence
  - CRC value
  - Detect errors in frame with cyclic redundancy check of 4 bytes. If calc is match -> no error.



