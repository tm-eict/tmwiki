---
title: DNS
description: 
published: true
date: 2021-06-12T11:40:42.618Z
tags: 
editor: markdown
dateCreated: 2021-04-22T13:12:41.363Z
---

## DNS
- Domain name system
- First Unix implementation: 
  - BIND: Berkeley Internet Name Domain
- Replaces the hosts.txt file
### What is DNS?
- Translation domain name into an ip address
- Request , Response

### Structure
- Hierarchical
- Max 253 characters and 127 levels


| Third-level | Second-level | Top-level |
|-------------|--------------|-----------|
| developers  | google       | com       |  
| www         | domainname   | com       |


- Top : root
- Top-level domains : .com , .org
- Sub-domains

### DNS zones
- Administrative representation of a domain
  - Legal entity (person, company)
    - Maintain dns zone
  - Administrative function
    - Name servers
    - Zone information
<a name = "dnsservertypes"></a>
- Zone informaton is kept/maintained on dns servers
  - Root DNS servers
    - 13 physical servers
    - Managed by ICANN
    - Refers to TLD servers
  - Top-Level Domain DNS servers (.com , .org)
  - Sub-domain DNS servers (second-level and lower)
    - Managment delegated to companies that use them
    - Auhtorative for that zone or domain
      - Can provide name-versus-IP-address data
      - Non-authorative servers only refer to other servers
### Name Resolution
- The process of translating a name into an address
   - When looking for a url in a browser
   - Looking for a network device by name
- DNS resolver
  - Part of the OS
  - First step
  - Receives requests
    - From OS, apps, browsers
  - Contacts nameservers when necessary
  - Uses caching
### Recursive resolution
- Name resolution can't be done by just 1 server
  - Internet is too big
  - DNS is a distributed database
    - Data spread over a lot of dns servers
      - [see here (zone information)](#dnsservertypes)
- Basic operation
  1. Request name resolution
  2. Request is sent to recursive DNS resolver
  3. DNS resolver contacts root server
  4. Root server refers to TLD server
  5. TLD server refers to second level
  6. Second level refers to third level and so on until the correct ip is found
### Authorative vs Non-Authorative
- Authorative
  - Can only reply with an IP address
- Non-Authorative
  - Refer to other name servers, per domain
  ex: 
  root gives ip of top level domain nameserver
  top level domain nameserver gives ip of subdomain name server etc...
### Hosts file
- First implementation
- Text file including hostnames and corresponding ip addresses
- Still used by resolver (can override info of dns servers)

### Network settings for DNS
- How does OS resolver know where to look next?
  - Network settings: DNS server addresses
    - Static or dhcp
ex: 
> google.com
1. Browser checks chache
2. OS resolver
  - Cache or host file
3. ISP DNS server
4. ISP queries root DNS for address of DNS server for .com
5. Query is passed to .com DNS server
### Caching
- To prevent root servers from receiving all queries
- Cache servers
  - Sore results of DNS queries for a limited time (TTL)
  - Can also perform recursive algorithm
  - At any level
  - optional
  - Checks if cached result exists, if not continues as normal
### Reverse DNS lookups (rDNS)
- Translate IP to hostname
##### Usage
- Tools (ping, traceroute)
- Anti-Spam
  - Filtering of generic Domain names
  - Outdated
- Forward confirmed reverse DNS
  - Verifies IP versus URL versus web server
  - White-listing
- System logging and monitoring tools
  - Easier and more user friendly
### DNS data
- How is it stored
  - DNS database
  - Different record types for different types of data
    - Actual name resolution - name vs IP
    - Address of other nameservers
    - Zone authority info
- DNS enables discovery of services
ex: mail service, Active Directory
##### Record types
- A: Address (HOST) : IPv4 address
- AAAA : Aaaaddress : IPv6 address
- NS : Name Server
  - identify authorative namserver for zone
  - must be accompanied by A or AAAA
- SOA : Start of Authority
  - Identifies primary DNS
  - Defined by NS and A record
- MX : Mail exchange (maps domain name to one or more Mail transfer agents for the domain)
- PTR : Pointer : Returns a name, used for rDNS
- SRV : Service : Generic record, can be used for any new protocol
  - Used in AD
- TXT : text : general use, info

### DNS forwarding
- We want internal DNS server but also want access to the internet
1. Configure client to use internal DNS server
2. Add a forwarder to the DNS server (to for example 8.8.8.8 - Google dns)

### DNS zone types
- Primary zone
  - Authorative, primary source of info
  - Master copy of zone data in local file on server
- Secondary zone
  - Secondary source of info
  - Copy of primary zone data
#### Zone transfer
- Copy from primary to secondary
  - Full transfer: All records are transfered
  - Incremental transfer: Only changed records are transferred
### Zone delegation
- Delegate managment/maintenance of zone data to another server
  - useful for very large domains
  - Admin purposes
- Zone data for the delegated zone can only be edited on the server to which the zone was delegated
  - Its authorative
### DNS blacklisting
- DNSBL : contains black-listed IP addresses
- Lookup is similar to rDNS
  - A record is returned : given address is black-listed
  - NXDOMAIN record : not lsited
- TXT records can contain more info about the reason for black-listing
### DDNS
- Dynamic DNS
- When the IP address changes regularly
  - ISP do that
  - DNS record needs to be updated automatically
- Requires client side service
  - Most routers built-in
  - Windows: integral part of AD
  - Linux : tools like dnsmasq
  - Update communications need to be secure
    - Man in the middle ? 
    - Spoofing ? 
### Domain registrars
- Registrars manage official domain names
- Source of information about domains
### DNS security
- Threats
  - DDoS : Distributed Denial of Service
    - Flood DNS server with requests in an attempt to get it down
    - Address spoofing, cache poisoning
      - Replace authentic address by fake address
      - The goal is to redirect traffic to a malintending website
- Domain Name System Security Extensions (DNSSEC)
  - Digital signing of all DNS server replies
  - A DNS resolver can now verify the authenticity of a reply