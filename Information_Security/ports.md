---
title: Ports
description: 
published: true
date: 2021-01-22T13:38:18.586Z
tags: 
editor: markdown
dateCreated: 2021-01-21T16:14:13.582Z
---

# Ports
## Dangers?
You can find this information at p131-134.
### USB ports and devices
USB devices can be very small which means they are easy to hide and transport. This makes it easy for they to carry/inject malicious software into local host computers.
That's why its very important to protect USB ports in a computer, as well as controlling access of individuals.

### eSATA ports
External SATA (Serial AT Attachment) are ports connected to the system's internal SATA bus. This bus is a standard for connecting hard drives to the computer system. Since they provide direct access to the buses that connect hard drives, they are security concern and might be worth covering up.

### Legacy ports
Serial COM ports, Small Compuiter System Interface (SCSI) and LPT parallel printer ports pose a security risk since they are all capable of handling two-way communications with the system's internal devices

|Port picture|name|dangers|
|--|--|--|
|![port_optical_audio.png](/ports/port_optical_audio.png =100x)| Optical Audio "TosLink" | Neen. Vooral enkel voor audio.
|![port_firewire_4_pin_ilink.png](/ports/port_firewire_4_pin_ilink.png =100x)| Firewire 4 pin iLink | Ja. Vergelijkbaar met USB. Support input en output
|![port_firewire_800_3200.png](/ports/port_firewire_800_3200.png =100x)| Firewire 800/3200 1394b/c | Ja. Vergelijkbaar met USB. Support input en output
|![port_ethernet_8p8c_rj45.png](/ports/port_ethernet_8p8c_rj45.png =100x)| Ethernet 8P8C RJ-45 | Ja. I/O voor communicatie. Kan je verbinden met een netwerk.
|![port_modem_rj11.png](/ports/port_modem_rj11.png =100x)| Modem RJ-11 | (niet zeker) Voor modem en telefonie. Niet echt.
|![port_apple_desktop_bus_adb.png](/ports/port_apple_desktop_bus_adb.png =100x)| Apple Desktop Bus/ADB | (niet zeker) Nee. Low-speed devices. Vervangen door USB. Voor kb/m.
|![port_mac_serial.png](/ports/port_mac_serial.png =100x)| Mac Serial | (niet zeker) Communicatie via printers
|![port_ps2.png](/ports/port_ps2.png =100x)| PS/2 | Nee. Enkel input via interupts
|![port_de9f.png](/ports/port_de9f.png =100x)| DE-9F | Ja. Ze kunnen two-way communication voeren met system internal devices. 9 staat voor aantal pins.
|![port_db25_serial_com_port.png](/ports/port_db25_serial_com_port.png =100x) | DB-25 Serial/COM port | Ja. Ze kunnen two-way communication voeren met system internal devices. 25 Staat voor aantal pins


