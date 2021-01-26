---
title: Ports
description: Port names and pictures. Info whether they can pose a security risk or not.
published: true
date: 2021-01-26T20:48:16.405Z
tags: info-sec, network, ports
editor: markdown
dateCreated: 2021-01-21T16:14:13.582Z
---

> Joris zijn antwoord!
![poortvragenjoris.png](/information_security/assets/ports/poortvragenjoris.png)
{.is-info}

## Te kunnen/kennen
- Alle poorten (op deze pagina) kunnen herkennen en benoemen.
- Of ze gevaarlijk zijn of niet.
- USB versies en namen moet je kennen **(snelheden zijn niet te kennen).**

Veel poorten zijn oud en niet meer in gebruik. Soms zelfs maar 1 keer gebruikt. Het is dus moeilijk om voor alle poorten te weten of ze gevaarlijk zijn. Joris Geens heeft nog geen antwoord gegeven op de vragen hierover

## Dangers
Alles wat 2 weg communicatie heeft (dus input en output) vormt een gevaar. Sommige poorten hebben ook directe connectie met systeem bussen, deze zijn nog gevaarlijker.
Andere zoals USB zijn nu eenmaal klein en hebben I/O.

Enkel input devices kunnen geautomatiseerd worden, maar deze gevaren zijn vaak niet meer van toepassing (volgens Joris)
Enkel output devices zijn over het algemeen veilig, maar afkijken is in principe mogelijk.

You can find this information at p131-134.

### USB ports and devices
USB devices can be very small which means they are easy to hide and transport. This makes it easy for they to carry/inject malicious software into local host computers.
That's why its very important to protect USB ports in a computer, as well as controlling access of individuals.

### eSATA ports
External SATA (Serial AT Attachment) are ports connected to the system's internal SATA bus. This bus is a standard for connecting hard drives to the computer system. Since they provide direct access to the buses that connect hard drives, they are security concern and might be worth covering up.

### Legacy ports
Serial COM ports, Small Compuiter System Interface (SCSI) and LPT parallel printer ports pose a security risk since they are all capable of handling two-way communications with the system's internal devices

## Tips
Tips om deze onnozele hoeveelheid van random oude poorten te leren:
- Poorten zoals DE-9F, DB-25 Serial/COM port, DE-9 Serial RS232 ... hebben de hoeveelheid pins in naam staan.
- Analoge connecties zijn vooral rond zoals audio, coax, component video/audio etc
- Poorten die input EN output vertonen de grootste mogelijkheid voor een risico.

## Data ports
Deze kunnen zeker een gevaar zijn. Ze kunnen data transporteren en sommige (eSATA, COM, SCSI, LPT) hebben connectie met interne systeem bussen.
|Port picture|name|dangers|
|:--|:--|:--|
|![port_firewire_4_pin_ilink.png](/information_security/assets/ports/port_firewire_4_pin_ilink.png =100x)| Firewire 4 pin iLink | Ja. Vergelijkbaar met USB. Support input en output|
|![port_firewire_800_3200.png](/information_security/assets/ports/port_firewire_800_3200.png =100x)| Firewire 800/3200 1394b/c | Ja. Vergelijkbaar met USB. Support input en output|
|![port_ethernet_8p8c_rj45.png](/information_security/assets/ports/port_ethernet_8p8c_rj45.png =100x)| Ethernet 8P8C RJ-45 | Ja. I/O voor communicatie. Kan je verbinden met een netwerk.|
|![port_modem_rj11.png](/information_security/assets/ports/port_modem_rj11.png =100x)| Modem RJ-11 | Voor modem en telefonie.|
|![port_apple_desktop_bus_adb.png](/information_security/assets/ports/port_apple_desktop_bus_adb.png =100x)| Apple Desktop Bus/ADB | Ja (wel extreem traag). Low-speed devices. Vervangen door USB. Voor kb/m.|
|![port_mac_serial.png](/information_security/assets/ports/port_mac_serial.png =100x)| Mac Serial | (niet zeker) Communicatie via printers|
|![port_de9f.png](/information_security/assets/ports/port_de9f.png =100x)| DE-9F | Ja. Ze kunnen two-way communication voeren met system internal devices. 9 staat voor aantal pins, F = Female.|
|![port_db25_serial_com_port.png](/information_security/assets/ports/port_db25_serial_com_port.png =100x) | DB-25 Serial/COM port | Ja. Ze kunnen two-way communication voeren met system internal devices. 25 Staat voor aantal pins.|
|![port_de9rs232.png](/information_security/assets/ports/port_de9rs232.png)|DE-9 Serial RS232|Ja. Ze kunnen two-way communication voeren met system internal devices. 9 staat vr pins.|
|![port_esata.png](/information_security/assets/ports/port_esata.png)|e-SATA|Ja. Ze hebben access tot de bussen van de diskdrives in een systeem.|
|![port_centronics_parallel_36_pin.png](/information_security/assets/ports/port_centronics_parallel_36_pin.png)|Centronics Parallel 36 pin|Ja. Ze kunnen two-way communication voeren met system internal devices.|
|![port_centronics_scsi_50pin.png](/information_security/assets/ports/port_centronics_scsi_50pin.png)|Centronics SCSI 50pin|Ja. Ze kunnen two-way communication voeren met system internal devices.|
|![port_50_pin_scsi_2.png](/information_security/assets/ports/port_50_pin_scsi_2.png)|50 pin SCSI 2|Ja. Ze kunnen two-way communication voeren met system internal devices.|
|![port_aaui.png](/information_security/assets/ports/port_aaui.png)|AAUI|(niet zeker) Deel van FriendlyNet en gefaald. Zelfde risco als rj-45.|
|![port_coax.png](/information_security/assets/ports/port_coax.png)|F-Connector RF/COAX|Zelfde risco als rj-45|
|![port_db25f.png](/information_security/assets/ports/port_db25f.png)|Parallel Port/SCSI 1/DB-25F|Ja. Ze kunnen two-way communication voeren met system internal devices. 25 staat vr pins. F = Female|

## Other
Is geen gevaarlijk (in principe [Rubber Ducky](https://www.plurilock.com/answers/rubber-ducky-attack-what-does-rubber-ducky-attack-mean/) achtige aanvallen wel mogelijk).
|Port picture|name|extra|
|:--|:--|:--|
|![port_ps2.png](/information_security/assets/ports/port_ps2.png =100x)| PS/2 | Weinig tot geen. (werkt met interrupts) |
|![port_atkeyboard.png](/information_security/assets/ports/port_atkeyboard.png)|AT Keyboard|Weinig tot geen.|
|![port_da-15-macvideo.png](/information_security/assets/ports/port_da-15-macvideo.png)|Mac Video/Midi/gameport/AUI<br>DA-15| Input + output + connectie met de north/south bridge is een risico. https://en.wikipedia.org/wiki/Game_port|

## Video/Audio
Deze hebben over het algemeen weinig gevaar. Afkijken kan een vorm van risico zijn.
|Port picture|name|dangers|
|:--|:--|:--|
|![port_optical_audio.png](/information_security/assets/ports/port_optical_audio.png =100x)| Optical Audio "TosLink" | Neen. Vooral enkel voor audio.|
|![port_surround_sound.png](/information_security/assets/ports/port_surround_sound.png)|Surround sound|Nee.|
|![port_stereoheadphoneslineinmic.png](/information_security/assets/ports/port_stereoheadphoneslineinmic.png)|Stereo/headphones<br>Line in<br>Mic|Nee.|
|![port_digitalaudiorca.png](/information_security/assets/ports/port_digitalaudiorca.png)|Digital Audio RCA plug style|Nee.|
|![port_compositeaudiovideo.png](/information_security/assets/ports/port_compositeaudiovideo.png)|Composite Audio/Video|Nee.|
|![port_svideo.png](/information_security/assets/ports/port_svideo.png)|S-Video|Nee.|
|![port_componentvideo.png](/information_security/assets/ports/port_componentvideo.png)|Component Video<br>Tip: RGB of RBG in dit geval|Nee.|
|![port_minidisplayport.png](/information_security/assets/ports/port_minidisplayport.png)|Mini DisplayPort|Nee.|
|![port_mini-dvi.png](/information_security/assets/ports/port_mini-dvi.png)|Mini-DVI|Nee.|
|![port_mini-vga.png](/information_security/assets/ports/port_mini-vga.png)|Mini-VGA|Nee.|
|![port_hdi-45.png](/information_security/assets/ports/port_hdi-45.png)|Apple Hi-Density Video HDI-45|Nee. Deze plug heeft ook maar gediend voor wel één display van Apple.|
|![port_adc.png](/information_security/assets/ports/port_adc.png)|Apple Display Connector – ADC|Nee.|
|![port_lfh60.png](/information_security/assets/ports/port_lfh60.png)|LFH60 (dual DVI-D)|Nee.|
|![port_dms59.png](/information_security/assets/ports/port_dms59.png)|DMS59 (Dual DVI-D)|Nee.|
|![port_hdmi.png](/information_security/assets/ports/port_hdmi.png)|HDMI|Nee.|
|![port_micro-dvi.png](/information_security/assets/ports/port_micro-dvi.png)|Micro-DVI|Nee.|
|![port_displayport.png](/information_security/assets/ports/port_displayport.png)|DisplayPort|Nee.|
|![port_dvivideo.png](/information_security/assets/ports/port_dvivideo.png)|DVI Video|Nee.|
|![port_de15-vga.png](/information_security/assets/ports/port_de15-vga.png)|DE-15/HD-15/VGA/SVGA|Nee. 15 staat vr pins. Als het 15/blauw is -> VGA.|

## USB
Altijd gevaarlijk aangezien ze klein en makkelijk transporteerbaar zijn voor malicious intent.
|USB picture|name|
|:--|:--|
|![port_usb-a.png](/information_security/assets/ports/port_usb-a.png)|USB A-Type|
|![port_usb-b.png](/information_security/assets/ports/port_usb-b.png)|USB B-Type|
|![port_usb-c.png](/information_security/assets/ports/port_usb-c.png)![port_usb-c2.png](/information_security/assets/ports/port_usb-c2.png =100x)|USB Type-C|
|![port_micro-usb-a.png](/information_security/assets/ports/port_micro-usb-a.png)|Micro-USB A|
|![port_micro-usb-b.png](/information_security/assets/ports/port_micro-usb-b.png)![port_micro-usb-2.png](/information_security/assets/ports/port_micro-usb-2.png =100x)|Micro-USB B|
|![port_usb-mini-b-5pin.png](/information_security/assets/ports/port_usb-mini-b-5pin.png)|USB Mini-b (5-pin)|
|![port_usb-mini-b-4pin.png](/information_security/assets/ports/port_usb-mini-b-4pin.png)|USB Mini-b (4-pin)|
|![port_usb3.0-a.png](/information_security/assets/ports/port_usb3.0-a.png)![port_usb3.0-a2.png](/information_security/assets/ports/port_usb3.0-a2.png =100x)|USB 3.0 A-Type|
|![port_usb3.0-b.png](/information_security/assets/ports/port_usb3.0-b.png)![port_usb3.0-b2.png](/information_security/assets/ports/port_usb3.0-b2.png =100x)|USB 3.0 B-Type|
|![port_usb3.0-micro-b.png](/information_security/assets/ports/port_usb3.0-micro-b.png)|USB 3.0 Micro B|

Versies en snelheidsnamen te kennen. **Snelheden** zelf **niet**.
| Version | Speed | ~~Bits/sec~~ | ~~HD movie 25GB~~ |
| :-- | :-- | :-- | :-- |
| USB 1.1 | Low speed (LS) <br> High speed (HS) | ~~1.5 Mbps <br> 12 Mbps~~ | ~~\~9.25 hours~~ |
| USB 2.0 | High speed (HS) | ~~480 Mbps <br> 14 Mbps~~ | ~~\~14 mins~~ |
| USB 3.0 | SuperSpeed (SS) | ~~5 Gbps~~ | ~~\~70 sec~~ |
| USB 3.1 | SuperSpeedPlus (SSP) | ~~10 Gbps~~ | ~~\~35 sec~~ |
![port_usbversions.png](/information_security/assets/ports/port_usbversions.png)

## Network ports
### Vaak voorkomende netwerk poorten
| Service | Well-known Port Number |
| :-- | :-- |
| FTP | 20, 21 |
| Telnet | 23 |
| SMTP Mail | 25 |
| HTTP (www) | 80 |
| POP3 (mail) | 110 |
| News | 144 |
| HTTPS | 443 |
| PPTP | 1723 |
| IRC | 6667 |
<br>

### Poorten en services per range
|Range|Services|
|:--|:--|
|0 - 1023|Specifieke services|
|1024 - 49151|Softwarehuizen|
|49152 - 65535|Dynamische en tussen computersoftware onderling