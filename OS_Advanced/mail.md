---
title: Email
description: 
published: true
date: 2021-06-13T09:27:58.029Z
tags: 
editor: markdown
dateCreated: 2021-06-13T09:27:52.038Z
---

## Email

### The Stone Age
- Messaging on mainframe computers: standalone
- ARPANET, Mail Box Protocol ($\lt$ 50 hosts)
- Later FTP
- UUCP : Unix-to-Unix Copy Program
- SMTP: Simple Mail Transfer Protocol
  - Introduced at the same time as UUCP
    - Today almost completely replaces UUCP
#### UUCP addressing
  - Complete route in address = "bang-path"
  - Still used in Usenet, but purely informative

#### Architecture
- Sender and receiver on the same mail server
    - 2 user agents (UA)
      - Sending and receiving of email
      - UI
      ex: Outlook
      cmd: Mail, pine,elm
  ##### ELM
  - Electronic Mail
- Sender and Receiver on a different mail server
  - 2 user agents 
  - 2 Message Transfer Agents (MTA): client and server
- Sender and receiver on a different mail server
  - Sender is connected to mail server via LAN or WAN network
    - 2 User agents
    - 2 Message Transfer Agents for communication between sender and mail server: Client and server
    - 2 Message Transfer Agents for communication between both mail servers: Client and server
- Sender and receiver are on a different mail server
  - Sender and receiver are both connected to mail server with LAN or WAN
    - 2 User Agents
    - 2 Message Transfer Agents for communication between sender and mail server: Client and server
    - 2 Message Transfer Agents for Communication between both mail servers: Client and server
    - 2 Message Transfer Agents for communication between receiver and mail server: Client and server


#### Message Transfer Agent (MTA)
- Client-server principle
  - Client sends
  - Server receives
- Protocol: SMTP
#### Message Access Agent
- SMTP can not be used
  - It is a push protocol
  - Bulk date from client to server
- We need Pull protocol
  - Client pulls data from server
  - Message Access Agent
- Well known protocols
  - POP3
  - IMAP4
- Summary
  - SMTP is used for sending mail
  - POP or IMAP are used for receiving mail

#### SMTP protocol
- Text based
- Connection oriented
- Port 25 for connection between mail servers
- TCP port 587 for UA connection to mail servers
- Client/Server protocol
  - Client sends bulk data to server
- Clients:
  - UA
  - MTA on a server : relay
- Connection:
  - UA clients configured with name of the SMTP server
  - Client needs server IP address
    - DNS
  - MX record is used within DNS
- Security
  - In the past, white-list with IP addresses
  - Now: Client authentication
  - Encryption on the standard ports, using SSL
  - Open relays: Unsecured mail servers
      - Only mail relay
      - subject of Black-listing
- Authentication
  - Extension of SMTP protocol
  - Client logs on to mail server
  - Can be required by the server
  - Does not guarantee authenticity
#### POP and IMAP
- Pull protocol
##### POP
- Post Office Protocol
- Download and delete principal
  - Mail downloaded to client (UA), deleted on server
  - Used for ISP email accounts (Storage is expensive)
- Uses standard TCP port 110
- Security
  - Encryption
    - TLS or SSL
  - Unencrypted credentials
  - Authentication methods
    - USER/PASS login
    - APOP: Encryption of user/pass via MD5 hash
    - Auth extension: SASL authentication
- UIDL
  - Each message gets a simple index number
  - Unique IDentification Listing Command
  - 5 character unique and permanent
  - Extension to POP 3

##### IMAP
- Internet Message Access Protocol
  - Internet Mail Access Protocol
  - Interim Mail Access Protocol
- IMAP4
- TCP port 143
- Secure connection via STARTTLS
- Multiple clients can use the same mailbox
- Messages remain on the server
- Uses flags
  - Read, Replied, Deleted
  - Stored on server
- Mutliple mailboxes are possible
- Extension mechanism
  - Allow extensions to the basis protocol
###### Google X-GM-1 Extensions
  - X-GM-RAW:L extended search
  - Access to the Gmail unique message ID
  - Access to Gmail thread ID
  - Access to Gmail labels
#### IMAP VS POP
- IMAP has adventage
- Can do partial fetch fo0r previewing message
### Microsoft Exchange Server
- Is basis of Active Directory
- MAPI protocol for communication with outlook clients
- Compatible with POP, IMAP and SMTP
### Unix mail servers
- Exmin: most-used MTA
- Postfix
- Sendmail: Default mail server
- Qmail
- Fetchmail
### Mime
- Multipurpose Internet Mail Extensions
- 7 bit ASCII
### Web-Based Email
- Squirrelmail
  - Based on php
  - Web server needs access to IMAP and SMPTP server
  - Stateful connection
  - IMAP proxy