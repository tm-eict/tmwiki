---
title: Commands
description: 
published: true
date: 2021-05-23T10:51:37.440Z
tags: 
editor: markdown
dateCreated: 2021-05-21T11:19:12.117Z
---

## Rename Switch/Router
1. `> enable`
2. `# configure terminal`
3. `(config)# hostname <new name>`


## Access
### Console password
1. `> enable`
2. `# configure terminal`
3. `(config)# line console 0`
4. `(config-line)# password cisco`
5. `(config-line)# login`
6. `(config-line)# end`

### Privileged password
1. `> enable`
2. `# configure terminal`
3. `(config)# enable secret <new password>`
4. `(config)# exit`

### Encrypt password (never used)
1. `> enable`
2. `# configure terminal`
3. `(config)# service password-encryption`

### Enable telnet
1. `> enable`
2. `# configure terminal`
3. `(config)# line vty 0 15`
4. `(config-line)# password <new password>`
5. `(config-line)# login`
6. `(config-line)# end`


## Network
### Setup IPv4 Router
1. `> enable`
2. `# configure terminal`
3. `(config)# interface <interface>` interface is something like "gigabitethernet 0/1"
4. `(config-if)# ip address <ipv4 address> <subnet mask>`
5. `(config-if)# no shutdown`

### Setup IPv6 Router
1. `> enable`
2. `# configure terminal`
3. `(config)# ipv6 unicast-routing`
4. `(config)# interface <interface>`
5. `(config-if)# ipv6 address <ipv6 addres>/<prefix>` address is something like 2001:AAAA:CAFE:1::1/64
6. `(config-if)# ipv6 address FE80::1:1 link-local` not needed but useful sets the link-local to a static address

### Setup IPv4 Switch
1. `> enable`
2. `# configure terminal`
3. `(config)# interface vlan 1`
4. `(config-if)# ip address <ipv4 address> <subnet mask>`
5. `(config-if)# no shutdown` Not sure if this is needed
6. `(config-if)# end`
7. `(config)# ip default-gateway <ipv4 gateway>` 

### Setup IPv6 Switch
1. `> enable`
2. `# configure terminal`
3. `(config)# ipv6 unicast-routing`
4. `(config)# interface <interface>`
5. `(config-if)# ipv6 address <ipv6 addres>/<prefix>` address is something like 2001:AAAA:CAFE:1::2/64
6. `(config-if)# ipv6 address FE80::1:2 link-local` not needed but useful sets the link-local to a static address

### Configure IP routes

`ip route <destination network> <destination network mask> <next hop ip address>`

eg:
- `Router0(config)# ip route 172.16.0.0 255.255.255.0 10.10.0.2`
- `Router1(config)# ip route 192.168.0.0 255.255.255.0 10.10.0.1`

## Config file
### Show configs/files
1. `> enable`
2. `show running-config`

You can specify what parts to show of the running-config (interface vlan 1, dhcp etc)

### Copy running – startup config
1. `> enable`
2. `# copy running-config startup-config`

### Reset switch/router (this is just one way)
1. `> enable`
2. `# write erase`

To apply changes you have to reload.

### Reload
1. `> enable`
2. `# reload`

### Copy config to tftp
1. `> enable`
2. `# copy running-config tftp:`
3. Enter IP of tftp server
4. Enter filename for the config

Example:
```
S1# copy running-config tftp:
Address or name of remote host []? 192.168.1.3
Destination filename [s1-confg]?
!!
1465 bytes copied in 0.663 secs (2210 bytes/sec)
S1#
```

> Make sure that the tftp server has write/read permissions to the folder you're using (otherwise you can't copy *to the directory*). `%Error opening tftp://<IP>/s1-confg (Permission denied)`
{.is-warning}

### Copy config from tftp
1. `> enable`
2. `# copy tftp: running-config`
3. Enter IP of tftp server
4. Enter filename of the config (on the server)

Example:
```
S1# copy tftp: running-config
Address or name of remote host []? 192.168.1.3
Source filename []? Switch1-confg.txt
Destination filename [running-config]?
Accessing tftp://192.168.1.3/Switch1-confg.txt...
Loading Switch1-confg.txt from 192.168.1.3 (via Vlan1): !
[OK - 1580 bytes]
[OK]
1580 bytes copied in 9.118 secs (173 bytes/sec)
*Mar 1 00:21:16.242: %PKI-4-NOAUTOSAVE: Configuration was modified. Issue "write memory" to save new certificate
*Mar 1 00:21:16.251: %SYS-5-CONFIG_I: Configured from tftp://192.168.1.3/Switch1-confg.txt by console
Switch1#
```

## Arp commands
- Show arp table: `> show arp` or on windows `> arp -a`
- Clear arp table `# clear arp` or on windows `# arp -d`


## Some helpful commands
- View interfaces: `> show interface`
- View specific interface: `> show interface <interface>`
- View all ipv4 interfaces: `> show ip interface`
- View all ipv6 interfaces: `> show ipv6 interface`
- View current config: `# show running-config`
- Show the ip routing table of router: `> show ip route`


## Hot keys
- Tab - Completes the remainder of a partially typed command or keyword
- Ctrl-R - Redraw line
- Ctrl-A - Move cursor to start of line
- Ctrl-E - Move cursor to end of line
- Ctrl-Z - Exits configuration mode and returns to user EXEC
- Ctrl-C - Aborts the current command and exits the configuration mode
- Down Arrow - Next command in history
- UP Arrow - Previous command in history 
- Ctrl-Shift-6 - Allows the user to interrupt an IOS process 
  - This is especially useful when u get stuck when mistyping `enable` or something takes too long (can save you time). 
  
