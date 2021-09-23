---
title: Remote Access
description: 
published: true
date: 2021-06-12T21:38:18.766Z
tags: 
editor: markdown
dateCreated: 2021-06-12T21:38:14.424Z
---

## Remote Access
- Home office and remote managment
### Dial up networking (DUN)
- Client calls the phone number of the dial-up server through a standard phone line
- PPP (Point-to-Point) protocol is used
  - Enable TCP/IP over serial line
- The machine making the connection is called the Remote Access (RAS) client
- The machine receiving the connection is called the RAS server
### Virtual private network (VPN)
- Uses internet, gateways use IP address to connect
- Creates tunnels between both gateways
  - Seperate protocol for direct communication between the gateways

Process: 
1. Client communicates with gateway
2. Gateway communicates with other gateway
3. Receiver gateway communicates with destination machine

- The tunnel is visible on a public network so it is recommended to encrypt all traffic
  - This is not by default
#### Site-To-Site VPN
- using VPN devices on both sides
  - Virtually in direct connection
  - Unaware of vpn
#### Client/Server architecture
- VPN software on remote client

#### VPN Via RAS server
- Client connects to RAS server via internet
  - Uses vpn client tool
    - Built into windows if youre using a windows Server VPN
- Ras has 2 network interfaces, Internet and local network
- RAS works as dhcp relay, the client gets a DHCP address on the remote network

### Tunneling Protocols
- Allows encapsulation of one protocol within packets of another protocol
- Inside protocol does not have to be supported on the outside network
  - On internet, TCP/IP is outside
  - TCP/IP packet payload contains actual payload encoded with inside (tunneling) protocol
examples: GRE (cisco), IPsec
#### Security Aspects

- CIA-triad
  Confidentiality
    - It is- only readable by people that are allowed to read it
  - Integrity
  - Authentication
    - Ensure the communication is authentic
      - Entity
      - Attributes
      - Origin of data
- Authorization
  - Determine who has access
- Data integrity
  - Data received = Data sent
- Non-Repudation 
  - Sender cannot deny having sent the message
  - Receiver cannot deny having received the message

#### SSL
Network layer: IPsec -> VPN

### IPSEC
- Security on Network layer
  - Adventages: 
    - Application-independent
    - Security for platforms that dont support it themselves
    - Limited to specific access points
  - Disadventages:
    - Beyond the secured access points, data is unsecured
- Additional security
  - ip protocol
    - Ip is unfit for authentication
    - No confidentiality in ip
  - Addition to ipv4
  - Integrated in IPv6

- applications: 
  - Secure branch office connection
  - Secure remote access over Internet
  - Extranet connectivity
  - E-commerce security
- Confidentiality
  - Encryption : no specific encryption algorithm
- Data integrity
  - Checksums
- authentication
  - Internet Key Exchange (IKE)
    - Username/Password
    - Pre-shared Key (PSK)
    - Digital certificates

### Symmetric Encryption
- Secret key used for encryption AND decryption
- Block cypher
  - Data is encrypted in fixed size blocks
  - DES (Data Encryption Standard | "broken"): block size 64 bits, key 56 bits
  - Triple-DES: 3*56bits key
  - AES (Advanced Encryption Standard): Block size 128, key 128,192 or 256
- Stream Cypher: 
  - Byte after byte
  - RC4: key 8 to 2048 bits
  - Sometimes used in SSL, WEP (WiFi)
- Disadventages: Both parties need to know the key
### Asymmetric Encryption
- Private/public key encryption
- Principle:
  - Public key is derived from private key
  - Private key can not be deduced from the puplic key
- Increasingly threatened by: new solving techniques and higher computational power
ex: RSA (Rivest-Shamir-Adleman)
- Confidentiality
  - Only sender and receiver know the contents of the message
- Authentication
  - Everyone is who they claim to be
- Message is encrypted using a public key
- The data can then be decrypted using a private key

#### Certificates
- Authentication of receiver
- Is used to exchange the public key of the receiver
- Certificate is signed:
  - By the receiver
    - Not very secure
  - By a certification authority (CA)
    - Can they be trusted?
- CA have public keys which are signed by a more trusted CA
  - Hierarchy of CA
    - Top level "root CA"

#### X.509 authentication
  - Framework for delivery of authentication services to directory users
    - Storage for public key certificates
    - Authentication protocol based on certificates
  - Revocation
    - Sometimes necessary before end of validity period
      - Secret key compromised
      - CA certification compromised
      - User no longer certified by CA
    - Certificate Revocation List (CRL)
      - Kept and updated by each CA
      - List of revoked CAs
        - List of serial numbers
        - Signed by CA
#### IPSEC security services
- Confidentiality : Encryption
  - Free choice
  - DES, 3DES, AES
  - Diffie-Hellman key exchange
- Integrity: Hashing
  - HMAC: Hash-Based Message Authentication Code
    - Message input + secret key -> HMAC code
  - MD5: 128 bit key, SHA-1: 160 bit key : "broken" 
  - Most recent: SHA-256, SHA-512, Whirlpool
- Authentication
  - PSK: shared secret key (Pre-Shared key)
    - Symmetric encryption
    - Key entered manually
    - Key used with other information to form actual auth key
  - RSA
    - Uses digital certifcates to authenticate
    - Context of IKE
#### Diffie-Hellman key exchange
- Key exchange is done in asymmetric way
ZIE SLIDE 66

#### Anti-Replay
  - Prevent duplicate authenticated packets
  - Sequence number
  - Moving window
  - Sequence number must fall inside the window
  - Window moves to the right as packets are received
### SSL vpn
- Layer4: Transport Layer TLS

- Transport layer security
- SSL : Secure Socket Layer

- Client/Server
  - Network traffic is secured via SSL
    - No installation of specific client
  - Site-to-site
    - Requires specific software
#### SSL handshake
- Determine the secret keys that will be used for the communication
  - Establish SSL protocol
    - Selection of algorithms
    - Auth of both parties by exchanging certificates
    - Generate common secret key

#### Openvpn
  - Open source vpn software

  - Uses SSL
    - Confidentiality: Symm. encryption
    - Data integrity: hashing
    - authentication: RSA
  - UDP port 1194
#### routed vs bridged
  - Routed: The remote hosts belong to a different subnet
    - Problem communication with other machines in local network of openvpn machine
      - they need a gateway
      - There is already another gateway
      - Solution: define static routes

  - Bridged: The remote hosts belong to the same subnet
    - Remote hosts get ip address in same network

  - Integrated in some routers
  - SoftEtherVPN : based on openVPN
#### SSH
Layer 7: Application layer :SSH

- Client server architecture
- Remote login over unsecured network
- Standard TCP port 22
- Session:
  - Negotiation about session-encryption
  - Authentication
- Session data is encrypted using symmetrical encryption
- Shared key is exchanged during session setup using asymmetric encryption
- Client Authentication
  - Password authentication
  - challenge-response: key based
    - Client has private key, uploads public key to server
      - Server encrypts a challenge message and sends to server
        - Only client can decrypt this
- Data integrity
  - HMAC hashing
  - During initial negotiation hashing algorithm is agreed
  - Hash calculated with
    - Shared key
    - Sequence number
    - Message content