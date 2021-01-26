---
title: OSI-model
description: 
published: true
date: 2021-01-26T14:26:01.533Z
tags: info-sec, network
editor: markdown
dateCreated: 2021-01-21T15:09:52.659Z
---

[Open Systems Interconnection-model](https://en.wikipedia.org/wiki/OSI-model) 
![Different layers in OSI-model](http://electricala2z.com/wp-content/uploads/2017/10/osi-model.gif =512x)

Extra explanation in [book](https://drive.google.com/file/d/1f_TkF0QISOQmXScrwByJxn9QEfhPXULH/view) on page 276.

## Data transmissie pakketten
* Encapsulatie: header toegevoegd in elke laag
	![osi-building-transmission-packets.png](/information_security/assets/osi-building-transmission-packets.png =500x)
	Foto data encapsulatie[^1]

Beveiliging is doorheen elke laag verweven:
| OSI LAYER | Network Security Model | Exploit Type  | Security Focus |
| :-- | :-- | :-- | :-- |
| 1) Physical Layer | 7) Physical Level | Physical Tampering/Break-in | Physical Security |
| 2) Data Link Layer | 6) VLAN Level | Network Scanning Local/Internal | Access Security |
| 3) Network Layer | 5) ACL Level | Network Scanning Complete/Internal | Domain Security |
| 4) Transport Layer | 4) Software Level | Software Specific Exploits | Port Security |
| 5) Session Layer | 3) User Level | Social Engineering - Users | Authentication/Encryption  |
| 6) Presentation Layer | 2) Administrative Level | Social Engineering - Administrators | Authentication
| 7) Application Layer | 1) IT Department Level | Social Engineering - IT Staff | ID/Authentication   |

## Layer 7: Application Layer
This layer is where the application and user communicates
Applications used here such as SMPT, if youre sending an email for example.
Data voor eindapplicaties (e-mail, browser ...).

Example:
- Is the application erroring out?
    
## Layer 6: Presentation layer
This layer formats the data in a way the receiving application can understand it. This layer can also encrypt/decrypt and compress/decompress data if needed.
Hoe ziet de data er uit bij ontvangst?

Example:
- Are you reading the data in the same order that you wrote it?

## Layer 5: Session layer
This layer is responsible for establishing and terminating connections between devices.
- Sessions beheren tussen applicaties
- Starten en stoppen van datatransfers
- Data flow tussen applicaties
- Security
- Authenticatie en tunneling protocols zoals SSH, IPsec, Point-to-point tunneling

Example:
- Are you connecting to the correct address?

## Layer 4: Transport layer
This layer adds transport protocols such as TCP/UDP, and adds source/destination
port numbers.
End-to-end data flow met foutcorrectie en recovery

Example:
- Could the internet card be functional?

## Layer 3: Network layer
The network layer handles ip addressing and routing. At this layer, the source
and destination IP addresses are added.
- Routers operate at this layer (routing the datapackets across nodes, networksegments and media).
- Multiplexing/demultiplexing
- Samenstellen van berichten.
- Connecties maken en verbreken.

Example:
- Is the router functioning?
- Do i have the right IP address?

## Layer 2: Data Link layer
At this layer, the physical addresses are added to the data. This is source and
destination mac addresses.
Switches operate at this layer

- Frames voor datapakketten aanmaken en verzenden tussen communicatiepunten
- Error detection en correctie
- Media access protocols (MAC)
- Bestaat uit twee sublagen
	- LLC (Logic Link Control) sublaag is de overgang met de OS (drivers)
		- Communicatie tussen software en fysieke hardware
		- Hier kan niet veel worden verandert en wordt bepaald door OS
	- MAC (media access control) sublaag gaat over de software op fysieke controller (netwerk kaart)
		- Is verantwoordelijk voor het encapsulerenvan de data die afkomstig is van de bovenliggende lagen
		- Deze zal encapsulation doen (toevoegen van de Ethernet header met onder andere de MAC adressen) en de\-encapsulation (verwijderen van de Ethernet header). Wanneer een frame wordt verstuurd over een router zal deze router de het destination ip adres bekijken, in de routing table (waarin routes door het netwerk staan vermeld aan de hand van ip adressen) kijken naar welk ip adres dit moet worden doorgestuurd, in de arp table kijken welk mac adres hierbijhoort, en het nieuwe destination mac adres toevoegen aan het packet
		- Verschillende toestellen op hetzelfde netwerk identificeren met een MAC adres: 48 bits, 12 hexadecimale getallen

Example:
- Maybe the switch has gone bad?

## Layer 1: Physical layer
carries data across physical hardware.
Uses: ethernet cables.
- Transmissie media (elektrische of lichtsignalen)
- Activatie van de media
- Communicatiepoorten

Examples:
- are all the cables plugged in?
- Is the network card functioning?
- Could it be a faulty cable?

## Acronym
Something to help you learn:
7: All - Application
6: People	- Presentation
5: Seem	- Session
4: To	- Transport
3: Need	- Network
2: Data	- Data
1: Processing	- Physical

https://youtu.be/LANW3m7UgWs
[Samenvatting info sec van Pieter Vanderdeen.pdf](/information_security/samenvatting_info_sec_pieter_vanderdeen.pdf)
[^1]: Cybersecurity Essentials, ISBN 978-1-11936239-5 pagina 278

