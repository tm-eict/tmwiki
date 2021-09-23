---
title: IPv4
description: Internet protocol version 4. Special addresses and how to subnet.
published: true
date: 2021-05-29T13:02:38.240Z
tags: network
editor: markdown
dateCreated: 2021-05-29T12:30:57.700Z
---

# IPv4

## Special addresses

- **Network and broadcasts** are the last addresses in a network
- **Loopback address** 127.0.0.1 to 127.255.255.254 (127.0.0.0/8) (refers to device/NIC itself)
- **Link-Local address** - 169.254.0.0 to 169.254.255.255 (169.254.0.0/16) addresses can be automatically assigned to the local host (with no DHCP server) (TTL = 1)
- **TEST-NET addresses** - 192.0.2.0 to 192.0.2.255 (192.0.2.0/24) set aside for teaching and learning purposes, used in documentation and network examples
- **Experimental addresses** - 240.0.0.0 to 255.255.255.254 are listed as reserved

## Private subnet ranges

- 10.0.0.0/8 | 255.0.0.0
- 172.16.0.0/12 | 255.240.0.0
- 192.168.0.0/16 | 255.255.0.0


## Subnetting

**Reasons to subnet**:
- Control traffic by containing broadcast traffic within subnetwork
- Reduce overall network traffic and improve network performance
- Security

IP consists of 4 * 8 bits.

| 2^7 | 2^6 | 2^5 | 2^4 | 2^3 | 2^2 | 2^1 | 2^0 |
|-----|-----|-----|-----|-----|-----|-----|-----|
| 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   |

**Octets**
- subnet = 2^8 - 2^(8 - length)
- change = 2^8 - subnet

| Subnet prefix length | change | subnet |
| --: | --: | --: |
| 0 | 0 | 0 |
| 1 | +128 | 128 |
| 2 | +64 | 192 |
| 3 | +32 | 224 |
| 4 | +16 | 240 |
| 5 | +8 | 248 |
| 6 | +4 | 252 |
| 7 | +2 | 254 |
| 8 | +1 | 255 |

### Example 1/2 for subnetting with explanation: 192.168.2.102/24  

| 192       | 168          | 2         | 102         |
|-----------|--------------|-----------|-------------|
| 128 + 64  | 128 + 32 + 8 | 2         | 64 + 32 + 4 + 2|
| 1100 0000 | 1010 1000    | 0000 0010 | 0110 0110   |

**Subnet mask**: prefix /24 means 24 bits or 3 bytes that will be 1 starting from MSB:  
1111 1111 . 1111 1111 . 1111 1111 . 0000 0000  
255.255.255.0  

To find the **network address** you simply need to do an AND operation with subnet mask and the given ip address:  

| IP address      | 192       | 168          | 2         | 102         |
|-----------------|-----------|--------------|-----------|-------------|
| Binary IP       | 1100 0000 | 1010 1000    | 0000 0010 | 0110 0110   |
| Subnet mask     | 1111 1111 | 1111 1111    | 1111 1111 | 0000 0000   |
| Network address | 1100 0000 | 1010 1000    | 0000 0010 | 0000 0000   |

Thus the network address is 192.168.2.0
The host part of the IP address are the remaining 0's from the subnet mask, in this case that would be 102.

Network address is identical for all devices in the same network, however the host portion is *unique*.

To find the **amount of hosts**:  
32 (total bits) - 24 (prefix/subnet mask) = 8 (0's)  
Amount of hosts = 2^8 - 2 (network + broadcast) = 256 - 2 = 254 hosts

The **broadcast address** has all the host bits set to 1.  
Here it would be 192.168.2.255.

### Example 2/2
172.16.104.99/27

|                       | Bin                                     | Dec             |
|-----------------------|-----------------------------------------|-----------------|
| **IP address**        | 10101100.00010000.01101000.011**00011** | 172.16.104.99   |
| **Subnet mask**       | 11111111.11111111.11111111.111**00000** | 255.255.255.224 |
| **Network address**   | 10101100.00010000.01101000.011**00000** | 172.16.104.96   |
| **Broadcast address** | 10101100.00010000.01101000.011**11111** | 172.16.104.127  |
| **Number of hosts**   | 5 host bits                             | 2^5 - 2 = 30    |
| **First host**        | 10101100.00010000.01101000.011**00001** | 172.16.104.97   |
| **Last host**         | 10101100.00010000.01101000.011**11110** | 172.16.104.126  |

## VLSM

Variable Length Subnet Masks is a technique to devide a network space in unequal parts depending on the amount of hosts.

**How to VLMS:**

- Order your networks (subnets) from largest to smallest. Start with the largest network.
- Subnet the network for the largest subnet
- Go to the next network (subnet), see if you need to subnet again
- Repeat the process to create subnets of various sizes

I highly recommend making a few exercises in Assignment 7.03.
