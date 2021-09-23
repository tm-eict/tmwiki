---
title: IPv6
description: 
published: true
date: 2021-06-01T13:50:26.013Z
tags: 
editor: markdown
dateCreated: 2021-05-29T13:32:28.043Z
---

# IPv6

## Why???

**We needed more addresses.**  
IPv4 = 32 bit = 4 294 967 296  
[People on the planet](https://www.worldometers.info/world-population/) ~ 7 869 009 829  
IPv6 = 128 bit = 340 282 366 920 938 463 463 374 607 431 768 211 456  

**Problems with NAT** (Network Address Translation)

- Checksum recalculation
- ICMP manipulation like Destination host unreachable
- IPsec problems: changing IP addresses fail integrity check
- No end-to-end reachability: port forwarding
- Decreased performance•NAT is Not Security

**In short:**

- IPv4 address depletion
- Access to IPv6-Only web services and users
- Increasing performance
- Improved security

## Shorthands

You can shorten down IPv6 addresses in 2 ways:

- omitting leading zero's
- omitting 1 or more 16 bit segments of 0's
  - **You can only do this once!**

Example for 1:  
2001:0DB8:0000:1111:0000:0000:0000:0200  
No leading 0s  
2001: DB8:0:1111:0:0:0:200

Example for 2:  
Preferred
FE80:**0000:0000:0000:0**123:1567:89AB:CDEF  
No leading 0's:  
FE80:0:0:0: 123:4567:89AB:CDEF  
Compressed:  
`FE80**::**123:4567:89AB:CDEF`

## Address types

- Unicast address
  - Uniquely identifies interface
  - Can be source and dest addr
- Multicast address
  - Group listening
  - All listeners will receive
  - Can only be dest addr
- Anycast
  - Multiple interfaces (devices) with the same unicast address
  - Lowest routing cost as route

There is no broadcast in IPv6

### Global Unicast Addresses

- routable address in the IPv6 internet
- Similar to IPv4 public IP
- In IPv6, all end devices should get a Global Unicast Address to access the internet, No NAT
- 2000::/3 addresses (first hextetfrom 2000 to 3fff)
  - 3 bits ^
  - 45 bits Global Routing Prefix
  - 16 bits subnet ID
  - 64 bits Interface ID

3 ways to assign ipv6 to device:
- Manually configured (Static IPv6 address)
- Stateful DHCPv6
  - DHCP server similar to ipv4
- Stateless Address Autoconfiguration (SLAAC)
  - Obtain prefix, prefix length, and default gateway from router advertisements
  - Interface ID calculated by device/client -> with EUI-64 process/MAC or random

### Link-local unicast address 

- Only for same subnet
- Not routed
- FE80::/10 (FE80-FEBF for first hextet)

### Others

- **Loopback address** ::1/128
- **Unspecified** ::/128
  - Can be used as source to obtain an ipv6 addr
  - cannot be assigned or used as dest
- **Unique local address** FC00::/7
  - Similar to IPv4 private ranges
- **Embedded ipv4** ::/80   
  - Used to communicate with IPv4

### Multicast

One-to-many approach, but more efficient than broadcast since it can be filtered by switches.  
FF00::/8 (FF00-FFFF)  
These addresses can only be destination addresses.

**Preserved reserved addresses**:

- FF02::1 All nodes on subnet
- FF02::2. All routers on subnet
- FF02::5 OSPFv3 routers on subnet
- FF02::A EIGRP routers on subnet
- FF05::1:3 All DHCP servers on site
- FF02::1:FFXX:XXXX Solicited-Node
  - Used for Neighbor Discovery (ND) and Duplicate Address Detection (DAD)
  - X's -> copy last 24 bits of unicast address

**Transient multicast (dynamic multicast**

- FF10::/12
- temp multicast for streaming, conferencing etc etc
- Multicast Listener Discovery (MLD) is used by hosts to subscribe to or leave a multicast group

### Summary

| First Hextet (Far Left) | Type of 1Pv6 Address                                                                                                                                 |  |
|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|--|
| 0000 to 00FF            | Loopback address,any address, unspecified address,or 1Pv4- compatible                                                                                |  |
| 2000 to 3FFF            | Globalunicast address (a routable address in a range of addressesthatis currently being handedout by the Internet Ass igned NumbersAuthority [IANA]) |  |
| FE80 to FEBF             | Link-local(a unicast addresswhich identifies the host computer on the localnetwork)                                                                  |  |
| FC00 to FCFF            | Unique-local(a unicast address which can be assigned to a host to identify it as being part of a specific subnet on the local network)               |  |
| FF00 to FFFF            | Multicast address                                                                                                                                    |

## IPv6 Header

![IPv4 vs IPv6 header](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fi.stack.imgur.com%2Fic5Vw.gif&f=1&nofb=1)

