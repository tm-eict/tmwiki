---
title: Samenvatting Info Sec
description: Samenvatting  Info Sec van 2020/2021 gemaakt door Pieter van der Deen
published: true
date: 2021-01-23T12:08:48.078Z
tags: 
editor: markdown
dateCreated: 2021-01-21T21:04:57.092Z
---

# Samenvatting Info Sec
Met dank aan Pieter van der Deen's [Samenvatting](https://tmwiki.be/information_security/samenvatting_info_sec_pieter_vanderdeen.pdf).

## CIA-driehoek
[comment]: <> (remove white background of img)
![cia-triad](/cia-triad.png)
^https://blog.jamestyson.co.uk/the-cia-and-dad-triads)^
Deze driehoek is de basis voor information security en beveiligingsmaatregelen rond IT-gerelateerde zaken. Het doel is om de CIA te waarborgen. CIA staat voor:

1. **Availability**: De gegevens zijn beschikbaar voor iedereen die daar recht op heeftwanneer het nodig is.
	1. **RAID**: Redundant Array of Independent Disks (inexpensive)
	2. Netwerk, authenticatie, dedundante hardware, back-up, ...
2. **Integrity**: De gegevens zijn correct en volledig (betrouwbaarheid).

3. **Confidentiality** De gegevens zijn vertrouwelijk en enkel de nodige gegevens mogen opgezocht worden door personen die hiertoe bevoegd zijn of recht hebben op deze gegevens.
	1. Mitaire classificatie
		1. **Topsecret**: de gebruiker heeft een need to know (heel groot  gevaar voor de nationale veiligheid
		2. **Secret**: data met beperkte toegang (ernstig gevaar)
		3. **Confidential**: eigendomsdocumenten (ernstig gevaar)
		4. **Sensitive But Unclassified** (SBU): intern gebruik (FOUO)
		5. **Unclassified**: brengt geen schade toe
	2. Commerciële indeling
		1. **Confidential** (bedrijven)/private (individu): heel erg gevoelig (grote impact)
		2. **Sensitive**: intern gebruik (kleine impact)
		3. **Public**: publiek toegankelijk (geen impact)
	3. Technologie
		1. **Encryptie**

(P: Note: Volgorde is eigenlijk AIC, te onthouden met CIA) <br>
Een aantal voorbeelden van een schendingvan de CIA-driehoek zijn:

* Een agent controleert het vervallen van de groene verzekeringskaart van een chauffeur na een aanrijding.
* Een agent controleert het vriendje van zijn dochter in de polititedatabase.
* Geldautomaat
	* Confidentiality: two-factor authentication
		* Zowel kennis als een bezit nodig
	* Integrity: bankverrichtingen worden real-life uitgevoerd
	* Availability: altijd beschikbaar (ook als de bank gesloten is)
* Identiteitskaart
	* Confidentiality: zelf verantwoordelijk
	* Integrity: Informatie moet kloppen op de chip (medische records etc)
	* Availability: altijd, code voor sommige dingen, kaartlezer

**Non-repudiation(onweerlegbaarheid)**: is de waarborg dat ontvangst en/of verzending van een contract of een bericht niet kan worden ontkend door de beide betrokken partijen, respectievelijk de ontvanger en de verzender(alles kan worden bevestigd en gecontroleerd, logs).

## Hoofdstuk 1

### Nist
* **N**ational **I**nstitute of **S**tandards and **T**echnology
* Dit is een Amerikaans framework dat richtlijnen geeft over hoe organisaties cyber security kunnen implementeren
* Bestaat uit 5 funties
	1. Identify (ID)
	2. Protect (PR)
	3. Detect (DE)
	4. Respond (RS)
	5. Recover (RC)
* Voorbeeld: NIST ID.AM\-1 
  | Framework |  Functie    |  Categeorie | Subcategorie |
  | -------------: | :----------: | :-----------: | :----------- |
  | Nist | ID | AM | 1 |
  
## Hoofdstuk 2
* Waarom beveiliging van fysieke infrastructuur nodig?
	* Zonder fysieke beveiliging is er geen beveiliging
 * Physical Security: a system of **inclusion** and **exclusion** for assets
	  * Exclude non authorized people
	  * Include authorized people
  * Cybersecurity
	  * Involves securing physical access to property, systems and equipment ports
	  * Securing electronics, optical and information access tot he system’s data and controls
  * Infrastructure security: when **physical security** initiatives are applied to providing security for the basic physical and organizational structures needed for the operation of an enterprise, an organization, or society
* Drie lagen(Perimeters) om fysieke beveiliging te plannen:
	1. **The Outer Perimeter**: Securing this space involves controlling who can move (walk, drive, fly) across the legal or physical line that marks this perimeter. Examples of typical physical outer perimeters include property lines or the exterior walls of a building or complex.
	2. **The Inner Perimeter**: This perimeter typically involves physical barriers such as walls, doors, and windows either exterior or interior, depending on the context of the outer perimeter.
	3. **The Interior**: This is the innermost level of security and consists of the interior of the building, office, cubicle, ... That is surrounded by the inner and outer perimeters.
	4. (**Logische perimeter**: grenzen tussen netwerken, local hosts, ...)
* Bij elke laag zijn er twee concepten aan het werk:
	1. **Natural Access\-Control Methods**: Natural access control involves using natural design elements, such as structures and landscaping, to guide people as they enter and exit spaces.
	2. **Territorial Reinforcement**: Territorial reinforcement employs structures, systems, and devices to prevent unauthorized entry and create a clear difference between what is public and private.
* Drie basisregels _infrastructuur_

	[comment]: <> (Make inner link)
	1. **Access\-control and monitoring** systems (H2)
	2. **Video surveillance** systems (H3)
	3. **Intrusion-detection** and reporting systems (H4)
* **Tailgating** : An unauthorized person slips past the locking door closely behind someone who is authorized to pass through it.
* Access-control
	* Om fysieke toegang te vermijden (schade, vernietiging, diefstal, ...)
		* **Ingress**: recht om ergens binnen te gaan
		* **Egress**: recht om ergens buiten te gaan
		* **Regress**: rrecht om ergens opnieuw binnen te gaan
	* Voorbeelden
		* Outer perimeter
			* Natuurlijke elementen
				* Hagen
				* Paadjes
				* Bomen
				* Waterlopen
				* CPTED
					* **C**rime **P**revention **T**hrough **E**nvironmental **D**esign
          ![cpted-example.png](/cpted-example.png)
					^https://www.ifpo.org/news/power-cpted-glue-holds-security-programs-together-bill-nesbitt/#post/0^
			* Territorial reinforceme
				* Apparaten: access\-control, camera’s, intrustion\-detection, poorten, ...
				* Borden
				* Schuif- en draaipoorten (met motor)
					* Kaartenlezer (copy card)
					* Radiosignalen (capture the signal)
					* Numerieke toetsen (code beter regelmatig veranderen, (thermal) camera)
		* Inner perimeter
			* Muren, deuren, vensters en andere openingen
			* Sloten: manueel (sleutel) of elektronish (magnetish)
				* Solenoid: vershillende configuraties mogelijk
					* Sluit automatisch na het binnengaan (tailgating)
					* Sluit automatisch af wanner de stroom uitvalt (emergency exit)
				* Cijferslot
					* Persoonlijke toeganscode  vereist (keypad)
			* Interior
				* Alarm systemen (detectie)
				* Een receptionist 
					* Vragen naar de aard van bezoek
					* Opvallend gedrag waarnemen
				* Security guard
					* Kunnen inschatting maken en beslissingen nemen 
				* Een bewakingsagent (kan beslissingen nemen en tijdig ingrijpen)
				* Authenticatie (wie ben jij - basis voor authorisatie)
					* **Knowledge**: wat de gecontroleerde persoon weet (pincode)
					* **Possesion**: wat de gecontroleerde persoon bezit (bankkaart)
					* **Inheritance**: rol van de gecontroleerde persoon (verantwoordelijkheden)
					* **Location**: waar de gecontroleerde persoon is (containerpark)
					* Magnetische strip lezers (magnetische data op de strook
					* RFID: chip is not powered; powered by radio signal
					* Biometric scanners
					* Smart card
						* Identiteitskaart: **PII** (personally identifiable information)
						* Gegevens
							* Zichtbaar
								* Rijksregisternummer
								* Nationaliteit
								* Geslacht
								* Geboorteplaats
								* Geboortedatum
								* Naam
								* Foto
								* geldigheidsperiode
								* plaats van uitgave
							* Verborgen op de chip
								* adres (hoofdverblijfpaats)
								* identificatiecertificaat (eID in card reader)
								* handtekeningcertificaat (digital signing)
						* Chip moet na een aantal jaar vevangen worden
							* Read only
							* Software update
* Remote-access monitoring
	* Remote\-access monitoring systems are used to notify supervisory security personnel when an unauthorized access is attempted.
	* The notification can come in the form of a visual notification on a security control panel, a call via telephone, an instant messenger notice, or a text message to a smart phone. The notification can also involve activating strobe lights and high intensity sirens to call attention to the intrusion attempt.
	* **Locked\-Condition Monitoring**: Locked monitoring is a feature that allows the security supervisor to confirm that a door is locked. In addition to monitoring the locked status of a door or gate, the condition\-monitoring system can also provide details as to how long and during what time periods the door or gate has remained locked
	* **Unlocked\-Condition Monitoring**: The condition\-monitoring system can record and signal each time a specific gate or door is unlocked (granting access) and what type of access was granted. Unlocked monitoring can also identify who was granted access.
	* **Time\-of\-Day Settings**: Most automated access\-control systems base decisions about valid or invalid entry requests, also called transactions, on preconfigured time\-of\-day settings. This is normal because any entry request that does not fit the predefined time profile or time schedule of an identified user is subject to suspicion.
  
  
## Hoofdstuk 3
* PIR: Passive InfraRed
* Some systems are based on coaxial cable for component connectivity, while others are IP-based and rely on wireless Wi-Fi communications or traditional network cabling.
* CCD Camera (Charged Coupled Device) (dit is een alternatief van CMOS, maar wel heel oud)
	* Hoge resolutie
	* Weinig licht nodig
	* Weinig temperatuurafhankelijk
	* Hoge betrouwbaarheid
* IP camera (Internet Protocol)
	* Kan overal beken worden (internet
	* PoE (Power over Ethernet)
	* Notifcaties
	* Cloud back-up
	* Geen bijkomende hardware nodig (DVR)
	* Kan met een NVR verbonden worden (Network Video Recorder)
* Analoge camera
	* Resolutie is lager
	* Beter in lagere lichtsomstandigheden (lux rating)
	* Beste prestatie met coax-cable
	* Geen PoE
	* Kan op een lange afstand geplaatst worden van de videorecorder (tot 1.5 kilometer)
	* Geen encryptie, geen VPN, geen datacompressie
* Analoge en digitale camera's (CCTV)
	* **CCTV**: Closed Circuit TV
	* Uses a DVR (Digital Video Recorder)
	* Beeldscherm nodig om video te kunnen bekijken
* Belangrijkste specificaties voor camera
	* Lichtgevoeligheid
		* lux waarde
			* Hoe lager, hoe beter: De camera kan projecten zine in het donker
		* Resolutie
			* Analoog: aantal horizontale lijnen
			* digitaal aantal pixels
* Lenzen
	* Hoe groter de lens (en dus ook de brandpunt afstand), hoe smaller het beeld maar ook hoe minder detail
	* Soorten
		* **Varifocale** lens: zoom mogelijk, maar herfocussen elke keer
		* **Vaste focale** lens: één vast focuspunt
		* **Breedbeeld** lens: breeder beeld
		* **Tele- of zoom**lens: zoom met een automatische focus
		* **Fisheye** lens: ziet een hele kamer maar met vervormingen
		* **Pinhole** lens: verborgen opnames
* Zwart-wit vs kleur
	* Zelfde kwaliteit
	* Kleur: meer beschrijvend (kleur auto, kledij, ...) 
	* IR-verlichting
		* Weinig licht: infrarood LED-verlichting
			* Niet zichtbaar voor mensen (beter verborgenheid van de camera's)
* Toepassingen camera's
	* Binnen/buiten (weerstandbestendig of niet)
	* Dag/Nacht
	* Vast/pan/tilt
	* Bewegingsdetectie
	* Sequencing (wisselen tussen camer's)/multiplexing (alle camera's gelijktijdig)
	* Time lapse
	* ...
* Video recorders
	* Tegenwoordig digitaal (DVR ipv VCR)
	* Hoge hoeveelheid aan opslagruimte nodig
		* Internal storage (HDD in een videorecorder)
		* Peripheral storage (extern met HDD via USB to DVR)
			= DAS (Direct-Attached Storage)
	* Network storage (NAS en SAN)
		* NAS: Network Attached Storage
		* SAN: Storage Area Network
    
## Hoofdstuk 4
* **Intrusion-detection**
	* Bestaat uit die zones
		* Perimeter
			* Becherming van openingen in de perimeter: deuren, ramen, garages, ...
			* Interior
			* Fire
		* Basisonfiguratie
			* Controller
				* PCB (Printed Circuit Board)
				* Processor
				* Telefoonlijn inputs en outputs
				* Terminals (schroeven voor sensor input)
				* Back-up batterij
			* Toetsenborden
			* Binnensensors
			* Alarmsingalen
			* Autodialer naar telefoonlijn (sms of stem)
			* Autodialer naar bewakingsfirma
			* (optioneel) rookmelders
			* (optioneel) perimeter sensoren (vensters, deuren, ...)
		* Zones
			* Groep van sensoren die bij elkaar horen
			* Voorbeelden:
				* Een aantal bewegingssensoren in een gang
				* Beweging sensoren in een trapahal
			* Gesloten loop van schakelaar waar een kleine stroom moet doorheen lopen (current loop). Wanner dit onderbroken wordt zal de controller dit detecteren. Dit is bteter dan een normaal open circuit omdat daarbij het doorknippen van een kabel niet kan worden gedetecteerd
		* Sensors
			* Magnetishe contact switches
			* Glasbreuk sensors
				* Acoustische sensor
				* Trilling sensor
				* Bewgingsmelder
					* PIR = Pasisive InfraRed (does not emit any energy)
				* Voertuigdetectie
					* Photoelectric beam devices
					* Microwave beam devices
				* Druksensoren
				* brandmelders
					* Warmtesensoren
					* rookmelders
				* Output devices
					* Visual Notification
					* Audible annunciators (Alarm)
					* Remote messaging
          
## Hoofdstuk 5
* Meerdere factoren spelen een rol bij authenticatie
	* **Kennis/Knowledge**: wat de persoon weet
	* **Bezit/Possesion**: wat de persoon heeft
	* **Erfelijkheid/Inheritance**: wat de persoon is
	* **Locatie/Location**: waar de persoon is
* Bij two-factor authenticatie gebruik je een combinatie van twee van deze vormen
* Een open en gesloten conditie is niet hetzelfde als een vergrendeld en ongegrendeld conditie

## Hoofdstuk 6
Local host Security in the real world

* Gaat over toestellen die data kunnen verzamelen: local host
	* Smartphone, IP camera
	* Local hosts are all devices except for a server or sharing device
* CSO: Chief Security Officer
* Risk assessment met NIST
	* NIST Identification (ID)
		* Hardwareinventaris
		* Softwareinventaris
		* Data flow
		* Infrastructuur
		* kwetsbaarheden
	* NIST Protect (PR)
		* Wie mag inliggen op het systeem en wie niet
		* Hoe de zwakke plekken beschermen?
		* Remote access
		* Communicatie input en output
	* NIST Detect (DE)
		* Genomen maatregelen monitoren
		* Welke apparatuur hbe je nodig voor monitoring?
			* Machine zelf
			* Personeelsactviteiten
	* NIST Respond (RS)
		* Procedures om een aanval te behandelen
			* Lagen in lekken
	* NIST Recover 
		* Welke schade moet hersteld worden?
		* Backup
		* Redundant hardware.
    
## Hoofdstuk 7
* De drie zones van beveiliging
	1. **Outer** perimter: behuizing en hardware (H7)
	2. **Inner** perimter: operating system + programma's (H8)
	3. **Interior**: data opslag plaatsen op het toestel (encryptie?)

### Secure the local host
* Infrastructuur
	* Desktop in een gesloten kast
	* Kabelsot
	* Docking station with lock
* Er zijn drie plaatsen waar de data beschermd moet worden
	* geheugen (RAM - memory dump)
	* Storage (HDD, SDD, USB-stick, SD-kaart, ...)
	* Tijdens transfer van de ene naar de andere plaats (communicatie)(input/ouput)
	* Hoe kunnen ze aan deze data?
		* Via toetsenbord, muis, touchpad, touchsreen, UTP-poort, ...
* **BIOS**: Basic Input/Ouput System
	* Wachtwoord om toegeang te krijgen tot het systeem (bij opstarten nog voor OS wordt geladen)
* **UEFI**: Unified Extensible Firmware Interface
	* Opvolger van BIOS: zelfde functies maar kan meer
	* Grafishe interface
* Drie taken
	1. hardware componenten opstarten
	2. functionaliteitscheck
	3. Bootloader opstarten (soms al direct OS in het geval van EUFI)
* BIOS/EUFI security
	* Wachtwoord instellen
		* CMOS setup utility (complementary metal\-oxide\-semiconductor)
		* Anders toegang tot inner perimeter en interior (Hoezo interrior?)
			* Poorten (boot order) om toegang te krijgen tot de storage
		* Wachtwoord vergeten?
			* CMOS-batterij verwijderen
			* Jumpers op het moederbord verplaatsen
			* Soldeernaden lossen (oudere PC's)
			* Daarom behuizingen beveiligen achter slot zodat niet iedereen dit kan doen
		* Updaten!
	* BIOS of UEFI is de eerste plaats waar sofware wordt gebruikt. Dit is dan ook de beste plaat som te starten als een hacker
* Local system hardening
	* **Hardening** = een computersysteem beveiligen
		* Hardware wordt beveiligd door de BIOS/UEFI
	* Waar begingt een hacker? Bij de firmware.
* Andere paden naar de innner perimeter zijn
	* Fysieke poorten
		* Zowel input als de output nodig (resultaat van opdrachten bekijken)
		* Input geeft toegang tot de interne communicatie bussen zoals databus, geheugen en interne opslag (chipset)
			* Chipset = IC's die de connectieve tussen randapparatuur, de CPU en het geheugen verzorgen
			* Twee IC's vormen samen chipset: Northbrdig een Southbridge
				* Nortbridge
					* Heel snel
					* Moet meegaan met de snelheid van de CPU
					* Afhankelijk can welke CPU is gebruikt
					* Kan verbinden met PCIe
					* Taak: verbinden van CPU met RAM en andere snelle perifirals
				* Southbridge
					* Trager
					* Niet rechtsreeks verbonden met de CPU
				* BIOS/UEFI en OS bepalen wat wel is toegestaan met deze chipset
	* Softwarepoorten op netwerkkaart (draadloos of UTP) (H12)

### Fysieke poorten

Belangrijke pagina/samenvating over poorten kan je hier vinden: [ports](/en/Information_Security/ports)

* USB-poort (Universal Serial Bus poort)
	* Daisy chains met USB-hub
	* Indien rechtsreeks op mobo, uit teschakelen in CMOS setup
	* **Hot-swapping**: toevoegen of verwijderen wanner het systeem actief is
	* IDE (Integrated Drive Electronics) (Nu PATA genoemd = Parallel Advanced Technology Attachment); zorgt voor transport van data tussen ROM en RAM; tegenwoordig wordt SATA gebruikt (Serial ATA)
  
	* ![ports_usb-collection-1.png](/ports/ports_usb-collection-1.png)
		^http://www.beginnerslessenpc.nl/USB%20Kabels%20Verschillen.htm^
	* ![ports_usb-collection-2.png](/ports/ports_usb-collection-2.png)
		^https://www.cablestogo.com/learning/connector-guides/usb^
	* ![ports_usb-speed](/ports/ports_usb-speed.png)
		^https://www.synopsys.com/designware-ip/technical-bulletin/protocol-layer-changes.html^
	* Type A vooral gebruikt waar de kabel permanent bevestigd is (muis, toetsenbord, ...)
	* Type B vooral gebruikt waar de kabel verwijderbaar is (printer, arduino, ...)
	* USB 3.0 vaak blauw
	* | Version | Speed | Bits/sec | HD movie 25GB |
		| :----- | :----- | :----- | :----- |
		| USB 1.1 | Low speed (LS) <br> High speed (HS) | 1.5 Mbps <br> 12 Mbps | ~9.25 hours |
		| USB 2.0 | High speed (HS) | 480 Mbps <br> 14 Mbps | ~14 mins |
		| USB 3.0 | SuperSpeed (SS) | 5 Gbps | ~70 sec |
		| USB 3.1 | SuperSpeedPlus (SSP) | 10 Gbps | ~35 sec |
    
	* FireWire(FW) en ThunderBolt (TB)
		* FW is de opvolger van SCSI
		* TB is een vervanger voor oudere SCSO, SATA, FireWire, PCI-e(Weet niet zeker?)
		* Bandbreedte van USB, firewire e, Thunderbolt
			| Version | Bits/sec | Bytes/sec |
			| :----- | :----- | :----- |
			| USB 1.0 | 1.5 Mbit/s | 0.19 MB/s |
			| USB 1.1 | 12 Mbit/s | 1.5 MB/s |
			| USB 2.0 | 480 Mbit/s | 60 MB/s |
			| USB 3.0 | 4.8 Gbit/s | 600 MB/s |
			| USB 3.1 | 10 Gbit/s | 1.250 MB/s |
			| FireWire 400 | 400 Mbit/s | 50 MB/s |
			| FireWire 800 | 800 Mbit/s | 100 MB/s |
			| FireWire 3200 | 3.2 Gbit/s | 400 MB/s |
			| ThunderBolt | 2x 10 Gbit/s | 2x 1.250 MB/s |
			| ThunderBolt 3 | 2x 20 Gbit/s | 2x 2500 MB/s |
      
* ![all-ports](/all-ports.png)
* DE-15 heb je in 2 rijen en 3 rijen
* M = male; F = female
* BNC connector
 	![bnc-connector](/bnc-connector.png =250x)
  ^https://showmecables-static.scdn3.secure.raxcdn.com/media/catalog/product/cache/0aa466c0d56d23d446bcd4aa4538d2f7/3/0/301_2.jpg^
* eSATA
	* External SATA (Serial Advanced Technology Attachment) om aan de interne SATA-bus te koppelen
	* Directe toegang to een bus (gevaarlijk)
		![eSATA](/esata.png)
		^https://en.wikipedia.org/wiki/ESATAp#/media/File:Esatap\_port.JPG^
* POST: Power On Self Test

## Hoofdstuk 8
### Inner perimeter
*	Operating system
*	Application programs

### Operating systems
* Intermediate software tussen de hardware en de applicaties
* Taken:
	* Resource managment (Ram, disk, printer, ...)
	* Multi-user access
	* Programme-uitvoer
	* Geheugenbeheer
	* Disk management
	* File Management System (FMS)

### Disk Operating System (DOS)
Een collectie van programma's die gebruikt worden om algemene operaties van een computer te contoleren  vanuit een schijf-gebaseerd systeem, oftwel een besturingsysteem voor apparaten met schijfstations
* Voorbeelden: Microsoft Windows, Apple MAC OS X, GNU/Linux
* Bestaat uit 4 secties
	1. **Boot files** nemen controle van het systeem over na BIOS/UEFI (laden kernel-bestanden)
	2. **Kernel files** zorgen voor de cummunicatie met de CPU
	3. **File fnagment files** zetten data in RAM-geheugen, waar de CPU de data en instructies kan ophalen
	4. **Utility files** waarmee de gebruiker de resources kan beheren, het systeem kan troubleshouten en configureren

### Soorten operating systems
* Standalone OS (Windows, OS X, Android, ...)
* Client OS (in een netwerkomgeving; maken gebruik van ee nmaster computer = server)
	* Thick clients
		* Hebben zelf wel veel power en zouden lokaal kunnen werken
		* Maken gebruik van enkele services op de server
		* Heeft lokaal geheugen
	* Thin clients
		* Volledig functionele PC maar zonder geheugen voor opslag (HDD)
		* Alle data en software wordt op de server bewaard e, uitgevoerd
	* Terminal clients
		* Gewone terminals, heel dom, weinig geheugen, ...
		* Hebben zelf geen OS
* Server OS
	* Server OS is basis  om network te beveiligen (H14)
* NOS (Network Operating System)
	* Voor de communicatie en data-uitwisseling tussen verschillend DOSen (Disk Operating Systems)
	* Windows ServerOS, Linux server distributions, Unix
	* Combinatie van disk management voor verschillend toestellen

### Operating system attacks
Kan op twee manieren:
1. Kernel manipuleren
2. File management system aanvallen

* Kernel manipuleren
	* Door geheugen manipulatie
		* Waarde van een variable aanpassen
		* Return adres van een functie aanpassen
		* Pointer naar uitvoerbaare code wijzigen
		* Malicious code toevoegen aan het geheugen
	*  NX bit (No eXecution) of eXecute Disable (XD)
		*  Storage-only memory (voor specifieke instructieblokken) om het geheugen te beschermen waar geen data geplaatst kan worden
		* Instructies kunnen daar neit bewaard worden
		* Bescherming tegen buffer overflow attack waar code wordt geïnjecteerd
	* DEP mode (Data Execution Prevention)
		* Elke applicatie krijgt een geïsoleerd stukje geheugen dat als virtueel geheugen gezien kan worden
		* Enkel de applicatie zelf kan in de virtueel afgeschermde zone werken

### File system security
* Uitermate belangrijk
	* Beschadiging leidt tot denial of access
	* Data stelen als iemand toegang heeft tot het file system

Hoe kunnen we het file system en bestanden beschermen 
* ACL (Acces Control List)
	* Gebruikers hebben wel of geen toegang tot data (lezen, schijven, wijzigen, verwijderen, uitvoern)
	* Bij een OS: ACL beschermt objecten zoals TCP/UDP en I/O (user kan dan een process zijn
	* Unix en Linux: Mandatory Access Control (MAC)
		* Gebuiker administrator policy als bron
		* Werkt met access rights
	* Windows: Role\-Based Access Control (RBAC)
		* Gebruikt rollen van gebruikers als bron
		* Dit wordt vaak gebruikt in grote bedrijven
		* Werkt met permissies
	* Werkt enkel op het bijpassende OS
		Door bijvoorbeeld Kali Linux te gebruiken kan je in deze lijst kijken \-\> encryptie van lijst nodig
	* POSIX
		* Portable operating system interface
		* Standard voor Linux\-achtige systemen om ACL te delen
	* Encryptie
		* Meeste OS hebben een vorm van encryptie in hun file management system(bijvoorbeeld BitLocker)
		* Kan worden gedaan bij opslag van data of bij vervoeren van data
			* NIST:
				* PR.DS\-1: Data at rest
				* PR.DS\-2: Data in transit
		* Kan op verschillende niveaus worden toegepast
			* Toestel
			* Disk/partitie/volumne
			* Mappenstructuur
			* Bestand

### Files System Attacks
* Race condition attacks:
	* Tussen twee events voert een hacker malicious code in.

	Bv. Wanneer een besturingssysteem een tijdelijk bestand aanmaakt, checkt het OS eerst of de te gebruiken bestandsnaam al bestaat, daarna maakt die het bestand effectief aan (twee events). Hacker voert in tussentijd malicious code in met de gecheckte filename. Dat bestand kan adminrechten hebben.
* Alternative data streams (bestanden verbergen)
	* ADS of alternative data streams op NTFS
	* Voor het verbergen van rootkits
	* Bestaat voor support met HFS (Hierarchical File System van Mac) dat bestanden wel eens forked (opsplitst) in meerdere bestanden
	* Wordt ook toegepast op bestaande OS\-bestanden, waarin malicious code geplaatst wordt
	* Enkel opspoorbaar met gewijzigde timestamp
* Directory traversals
	* Backtracking, directory climbing attacks, canonicalization attacks
	* Slecht geschreven software of slecht beveilige (web)servers
		* Toegang verwerven tot een map met geen beperking, daarna opklimmen in de structuur

### Verschillen tussen OS'en
* Microsoft Windows
	* GUI\-gebaseerd
	* Werkt met x86 32\-bit en x86 64\-bit, ARM processors
	* Heeft ondersteuning voor NX\-bit en XD\-bit
	* Basic file system formats
		* FAT/FAT16/FAT32
			* File Allocation Table
			* Nog vaak gevonden op USB\-sticks, SD\-kaarten, ...
		* NTFS
			* New Technology File System
			* Standaard voor Windows
			* Heeft ACLs en EFS toegevoegd (encrypting file system)
		* ISO 9660 (CDFS)
			* Compact Disk File System
			* Voor op cd’s
		* UDF
			* Universal Disk Format
			* Opvolger van CDFS
			* Vooral gebruikt op DVD’s
	* Encryptie
		* Bestanden en mappen door EFS
		* Volledige schijf door BitLocker
	* Firewall maakt gebruik van packet filtering
* UNIX
	* Veel variaties
		* BSD (Berkeley Software Distribution)
	* Verschillende distributies maken gebruik van verschillendefile system formats
		* UFS
			* UNIX File System
			* Origineel file system
			* Boomstructuur
		* NFS
			* Network File System
			* Beestanden benaderen over het netwerk
	* Encryptie
		* Vroeger cypt
			* Makkelijk te kraken nu
		* DES: Data Encryption Standard
		* PGP: Pretty Good Privacy
		* PEFS: Private Encrypted File System
			Voor bestanden
		* GELI en GDBE
			voor schijven
	* Heeft ook firewalls
* Linux OS Distributions
	* Open-Source
	* Veel verschillende distributies
	* NX-bit ondersteuning op sommige systemen
	* File system types
		* Ext/ext2/ext3/ext4
			* **Ext**ended File System
			* meest gebruikt file system voor Linux
			* Ext2/3 ook veel op SD kaarten en andere flash schijven
		* ReiserFS
			* Alle veranderingen worden bijgehouden in een log bestand (journal)
			* Heeft permissies en ACLs, maar geen encryptie
		* Encryptie
			* Via pakket: eCryptfs
		* Ingebouwde firewall: Netfilter
			* Maakt ook gebruik van packet filtering
			* Maar ook filtering voor Network Address Translation (NAT) en Port Address Translation (PAT)
* Apple OS
	* Werkt met x86 32\-bit, x86 64\-bit  en ARM processors
	* NX-bit ondersteuning
	* Ondersteuning voor ISO9660, FAT, NFS, UFS en UDF
	* Ondersteunt FMS standaard
		* HSF/HSF+: Hierarchical File System (+)
			Gemaakt door Apple
		* SMBFS/CIF: Server Message Block File System of ook bekend als Common Internet File System
			Voor gebruik van gemeenschappelijke toegang tot bestanden
	* Encryptie
		FileVault voor encryptie van schijven
* iOS
	* Veel kenmerken van macOSmaar kan die applicaties niet draaien (mogelijk outdated)
	* RISC (Reduced Instruction Set Computing)
	* ARM (Acorn RISC Machines)
		* Gebruikt veel minder energie en produceert veel minder warmte dan x86 CISC (Complex Instruction Set Computing)
	* Encryptie
		Toestel gebaseerde encryptie
* Android OS
	* Gebaseerd om Linux OS kernel
	* Open Source
	* ARM
		* Onderseunt XN (is een page instruction)
		* Speciale versies die op x86 draaien
			* Ondersteuning voor XD\-bit en NX\-bit
		* Verschillende toestellen ondersteunen verschillende file systems
		* Er zijn wel enkele gemeenschappelijke file systems voor flash die vaak worden gebruikt
			* exFAT: extended File Allocation Table
				Microsoft
			* F2FS: Flash\-Friendly File System(version 2)
				* Samsung
				* Open-source
			* JFFS2: Journal Flash File System (version 2)
				Vervanging van YAFFS2 (Yet Another Flash File System)
			* Ext2/Ext3/Ext4
		* Vaak ook ondersteuning voor FAT
		* Encryptie
		 	Schijf encryptie van flash geheugen: dm\-crypt
		
### Operating System Security Choices
* Microsoft Windows is het vaakste het doel van criminelen
* **Grayware**: irritante ongewilde software

### Security tools en OS
Nadat het OS is opgestart moeten stappen worden ondernomen om niet\-geauthentiseerd toegang tegen te houden
* Local login\-vereisten
	* Gebruiker en groepsaccounts
	* Wachtwoord policies
		* Wachtwoorden
			* Hoofdletters (A, B, C, D, ...)
			* Kleine letters (a, b, c, d, ...)
			* Getallen (0, 1, 2, 3, ...-
			* Speciale tekens (?, !, &, |, ...)
		* Wachtwoordentechnieken
			* Lengte: hoe langer hoe beter
			* Vervanging: jOrisg33ns
			* Toevoeging: jorisgeens123 \<slecht wachtwoord\>
			* Mnemonisch: UraGreet
			* Afkorting: Ihobtf (I have only begun to fight –Natalia)
			* Volle zin met vervanging: welk0m1nd3l3sv@nV@n6@@g
		* Goede praktijken met wachtwoorden
			* Gebruik een consistente naamconventie
				Bv. Groentennamen met getallen en symbolenPrei38@w0rk!
			* Bij eerste gebruik verplicht laten wijzigen
			* Wachtwoorden niet opschrijven (awareness)
			* Train gebruikers in het maken van sterke wachtwoorden (indien mogelijk 2-factor)
			* Dwing een policy af
	* Lockout policies
		* Account lockout policies
			* Maximal aantal pogingen
			* Brute force attacks tegengaan
		* Computer locking
			* Na verloop van tijd automatisch
* Bijkomende authenticatie
	* Kaart of vingerscanner(Biometrische scanners)
* Lokale administratie tools
	* Event logging en audit
		* Windows: security log file (event viewer)
		* Windows: Administrative Tools > Local Security Policy
		* Linux: System log
	* Encryptie
	* Monitoren van application software security
* Remote access\-bescherming
	* Firewall (H9)
	* Browser beveiligingsopties
* Bescherming tegen malicious software
* Security updates en patches

| Patch | Update |
| :----- | :------ |
| Richt zich alleen op security  vulnerabilities |  Update de applicatie verandert funtionaliteit en hoogt de versie op |
| Verandert niet aan funtionaliteit of dependencies | Breekt vaak plugin/theme/extensie/dependencies |
| Verandert de applicatie versie niet, compatibel met latere update | In de meeste gevallen niet veilig te automatiseren |
| Velig te automatisren | |

### Data encryptie
* Symmetrische encryptie: zelfde sleutel voor encryptie en decryptie
* Asymmetrische encryptie: twee verschillende sleutels
	* Private key(decryption)en public key(encryption)
	* Public key is afgeleide van private key
	* PKE: Public Key Encryption
* Encryptie kan plaatsvinden op verschillende niveaus
	* File system\-level (file and folder)
		* Windows: EFS (encrypting file system) langs Bestandsverkenner > Eigenschappen > Geavanceerd
		* Gewapend tegen BIOS\-kaping!
		* Folders hebben ook list folder content permissie
	* Disk\-level
		* Heel de schijf is encrypted
			* Ook OS bestanden
			* Kan via software of hardware
			* Software
				* Staat meestal al op OS
			* hardware
				* TPM (trusted platform module): chip with for instance encryption keys
				* TPM chip is fixed on motherboard
				* Cannot be transferred to another main board
				* Controleert of er niks aan het OS is veranderd
	* Transport\-level
		* USB\-sticks met encryptie
		* Certificaten (https)
    
## Hoofdstuk 9
### Stappenplan tegen netwerkbedreigingen
1. Gebruik een beveiligde netwerkverbinding
	* Routers zorgen voor de beste eerste beerscherminglaag
		* Standaard admin\-gebruikersnaam en wachtwoord wijzigen
		* Standaard SSID wijzigen
		* Configureer het hoogst mogelijke encryptieniveau
		* MAC\-adresfilter (bv. 00:A0:C9:14:C8:29)
2. Pas een geconfigureerde **firewall** toe
	* **Controleert de data flow tussen computer en network**
	* Software of hardware (zie later)
	* Standaard staan alle poorten meestal open!
3. Run één anti\-malware\-programma
	* Meerdere antimalwareprogramma’s kunnen elkaar tegenwerken
	* Kan als suite of als aparte producten (antivirus, antispyware, firewall, ...)
4. Verwijder onnodige software van de computer
	* Mogelijke slapende exploits
	* Weet je wat de software doet?
5. Stop alle onnodige services op de computer
	* Weet je wat de service doet? Hoort die bij een bepaald programma?
	* Service altijd natrekken, kan een OS\-service zijn
6. Schakel onnodige OS\-functionaliteiten (bv. webserver) uit
	* Bv. Autorun (DVD of USB met virus)
7. Beveilig de webbrowser
	* (Cross\-site) scripting
	* Onveilig browsen
	* Plug\-ins
	* Security levels
	* Proxies
	* Cookies
		* Sessions cookies: verdwijnen als de browser wordt gesloten
		* Persistent cookies: blijven tot de vervaldatum is bereikt
8. Voer updates en patches steeds uit
	* Dicht beveiligingslekken zo snel mogelijk
	* Op alle software op het toestel
9. Gebruik sterke wachtwoorden
	* Drie verschillende soorten logons
		1. Lokaal niveau (machine zelf)
		2. Netwerkniveau (LAN/internet)
		3. Specifieke software (boekhouding)


### Lokale bescherming
5 veel gebruikte tools
1. Lokale firewell
	* Software, bedoeld voor individuele computers met dial\-up, LAN of andere rechtstreekse internetverbindingen
	* Beheert het inkomend en uitgaand dataverkee
	* Bewaken poorten en services
		* 0 tot 1023: specifieke services
		* 1024 tot 49151: geregistreerde poorten
		* 49152 tot 65535: dynamisch en tussen computersoftware onderling
	* Well known ports and services
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
		* News: oude service van het verleden
		* IRC: Internet Relay Chat
		* POP: Post Office Protocol

2. Inbraakdetectie
	* IDS (Intrusion Detection Systems)
		Monitor system, logs key eventsand policy violations, alert reports
		* Network-based (NIDS)
			Niet verder besproken
		* Host-based (HIDS)
			Gebruikt twee strategieën
			1. Signature analysis (patterns)
				Kijkt voor verdacht patronen uit een lijst met verdachte patronen
			2.  Anomaly analysis
				Statistische analye van verkeer van data
				* Profile\-based (rules)
					Zoekt naar ongewone patronen. Leert zelf wat "normal" is
				* Threshold\-based (level)
					Als een bepaald event meerdere keren voorkomt
		* IPS (Intrusion Prevention Systems)
			* Prevent the succeeding of intrusions
			* Ook wem IDPS genoemd
				Intrusion Detection and Prevention System
	3. Browser beveiligingsopties
	4. Antivirus/anti\-malware
		* Grayware: niet gewenst, maar moet niet kwaadaardig zijn
		* Malicious software: kwaadaardig
				Virussen (dupliceren vanzelf met hostprogrammaen verspreiden zichzelf
			* Wormen (geen hostprogramma nodig, zoekt een exploit in het network en besmet alle computers, zodat er een hoge payload is op het network)
			* Trojaans paard (lijkt een betrouwbaar programma te zijn, verspreid zichzelf niet)
			* Rootkits (administrative controle van het toestel verwerven, werken op rootniveau, nestelen zich bijvoorbeeld voor de bootloader)
			* Ransomware (encryptie van data met vraag om losgeld)
			* Spyware (probeert gevoeligedata ongezien te stelen)
			* Adware (toont ongevraagd gerichte reclame in de brower of andere applicaties) 
			* Logic bombs (delete data, zoals een trojaans paard met betrouwbare software, activeert zichzelf op een logisch moment, na x dagen, na het gebruik van xkeer van het programma, malicious code zit in heel veel lijnen gewone code vervat)
			* Zombies (voor DDOS-aanval –distributed denial of service)
			* Botnets (vele zombies samen voor bijvoorbeeld spam uit te sturen
		* Antimalware
			* Antivirus (signatures en ongewoon gedrag
			* Antispyware (twee soorten: één die opspoort en verwijdert, één die installatie tegenhoudt)
	5. Software updates en patches
		* Service pack
			* Grote hoeveelheid aan updates verpakt in één
			* Altijd eerst een back\-up nemen vooraleer service pack te installeren (zou onstabiel kunnen zijn)
		* Patch
			* Kan ook als reactie op een virus zijn
		* Updates
			* Bevordert beveiliging, betrouwbaarheid of de voorkeur van een hacker/cracker voor een bepaald besturingssysteem
	
### Exploits
* Weaknesses in software
* Conflict bij het maken van software
	* Zo eenvoudig mogelijk in gebruik zijn voor eindgebruikers
	* Bullet proof, zodat er niets mee kan foutlopen
* Buffer overflow \-\> kan systeem laten crashen \-\> Denial of Service (DoS)

### Soorten hackers/crackers
* White hat \[ethisch hacker met contract]
* Black hat \[cracker of criminal hacker]
* Grey hat \[werkt vanuit overtuiging, overschrijdt wettelijke grenzen]
* Red hat \[valt black hats aan]
* Scriptkiddies \[werkt met bestaand material en scripts, geen kennis van zaken]

## Hoofdstuk 10
Overzicht + examenvragen

## Hoofdstuk 11
* IP: Intellectual Property

## Hoofdstuk 12
### Netwerken
Twee  basistypes van netwerken
1.	LAN (Local Area Network)
	Voor geografisch kleine gebieden (een huis, gebouw, ...)
2.	WAN (Wide Area Network)
	Voor geografisch grote gebieden
	
Andere types van netwerken
* CAN (campus/corporate area network)
	LANs die met elkaar verbonden zijn op campussen
* MAN (Metropolitan Network)
	Zit tussen LAN en WAN
* WLAN (Wireless Local Area Network)
	draadloos
* SAN (Storage Area Network)
	Voor dataopslag
### [OSI-model](/en/Information_Security/OSI-model)
Open systems interconnection
* To standardize communications (data handling) between network components
![OSI-model.png](^/osi-model.png =512x)
^http://electricala2z.com/wp-content/uploads/2017/10/osi-model.gif^

Lagen
* Laag 1: Fysieke laag
	* Transmissie media (elektrische of lichtsignalen)
	* Activatie van de media
	* Communicatiepoorten
* Laag 2: Data link
* Frames voor datapakketten aanmaken en verzenden tussen communicatiepunten
* Error detection en correctie
* Media access protocols
* Bestaat uit twee sublagen
	* LLC (Logic Link Control) sublaag is de overgang met de OS (drivers)
		* Communicatie tussen software en fysieke hardware
		* Hier kan niet veel worden verandert en wordt bepaald door OS
	* MAC (media access control) sublaag gaat over de software op fysieke controller (netwerk kaart)
		* Is verantwoordelijk voor het encapsulerenvan de data die afkomstig is van de bovenliggende lagen
		* Deze zal encapsulation doen (toevoegen van de Ethernet header met onder andere de MAC adressen) en de\-encapsulation (verwijderen van de Ethernet header). Wanneer een frame wordt verstuurd over een router zal deze router de het destination ip adres bekijken, in de routing table (waarin routes door het netwerk staan vermeld aan de hand van ip adressen) kijken naar welk ip adres dit moet worden doorgestuurd, in de arp table kijken welk mac adres hierbijhoort, en het nieuwe destination mac adres toevoegen aan het packet
		* Verschillende toestellen op hetzelfde netwerk identificeren met een MAC adres: 48 bits, 12 hexadecimale getallen
* Laag 3: Netwerk
	* Routing van datapakketten over netwerknodes, netwerksegmenten en media.
	* **Multiplexing (muxing)**: samenvoegen analoge of digitale signalen tot 1 enkel signal
	* **Demultiplexing (demux)**: scheiden van 1 signal in meerdere signalen
	* Samenstellen van berichten
	* Connecties opzetten en verbreken
* Laag 4: Transport
	* End\-to\-end data flow met foutcorrectie en recovery
* Laag 5: Session
	* Sessions beheren tussen applicaties
	* Starten en stoppen van datatransfers
	* Data flow tussen applicaties
	* Security
	* Authenticatie en tunneling protocols (**SSH**: secure shell, **IPsec**: Internet Protocol security, **PPTP**: point-to-point tunneling protocol, ...)
* Laag 6: Presentataion
	*	Hoe ziet de data er bij ontvangst uit?
		*	Encryptie
		*	Datacompressie
*	Laag 7: Aplication
	*	Data voor de eindapplicaties behandelen
	*	Browser, e\-mail (gebruikersnaam en wachtwoord)
*	Laag 1-3: Media layers
*	Laag 4-7: Host layers

Data transmissie pakketten
* Encapsulatie: header toegevoegd in elke laag
	![osi-building-transmission-packets.png](/osi-building-transmission-packets.png =500x)
	^Cybersecurity Essentials, ISBN 978-1-11936239-5 pagina 278^
	
OSI layer security
* Zit doorheen elke laag verweven

| OSI LAYER | Network Security Model | Explout Type  | Security Focus |
| :-- | :-- | :-- | :-- |
| 1) Physical Layer | 7) Physical Level | Physical Tampering/Break-in | Physical Security |
| 2) Data Link Layer | 6) VLAN Level | Network Scanning Local/Internal | Access Security |
| 3) Network Layer | 5) ACL Level | Network Scanning Complete/Internal | Domain Security |
| 4) Transport Layer | 4) Software Level | Software Specific Exploits | Port Security |
| 5) Session Layer | 3) User Level | Social Engineering - Users | Authentication/Encryption  |
| 6) Presentation Layer | 2) Administrative Level | Social Engineering - Administrators | Authentication
| 7) Application Layer | 1) IT Department Level | Social Engineering - IT Staff | ID/Authentication   |
* **Three\-layered rings of security**
	* Bestaat op twee toestellen: zender en ontvanger
		* Het medium verbind de hun outer perimeters (kabel, luchtgolven, ...)
	1. Outer perimeter
		* Laag 1 (fysieke laag)
		* Beveiligen van datakabels en netwerkapparatuur
	2. Inner perimeter
		* Laag 2 (data link)
		* Data kan hier aanvaard worden, geweigerd of doorgestuurdop basis van de identiteit
	3. Interior perimeter
		* Laag 3-7
		* Bijvoorbeeld: laag 4 met het blokkeren van poorten
			laag 7 is de meest aangevallen laag (zie later)
      
### Netwerktopologieën (laag 1)
* Bus
	* Met centrale communicatielijn (ethernet) ofwel bus
	* **Nodes** of stations met uniek adres
	* Iedere node kan informatie op de bus zetten en juiste informatie eraf halen
* Ring
	* Communicatielijn is geslotenin een cirkel
	* Repeater stuurt info door vanuit elke node
	* Geen collisions
	* Risico: één node plat betekent netwerk plat\-\> meerdere redundante paden leggen
* Ster
	* Communicatie langs een centrale component (switch)
	* Geeft elke node een tijdsvenster om informatie mee te verzenden
		* Indien het bericht te lang is voor het tijdsvenster, zal het in stukken worden opgedeeld
* Mesh
	* Elke node heeft een rechtstreekse verbinding met elke andere node
	* Telefonie, Bluetooth, LoRaWAN, ...
* Hybride
* Logische topologie
	* Niet elke getkeende topologie komt met de interne circuits overeen met de visuele topologie
		* In een router zitten alle poorten als een bustopologie (Wat?)
	
### Labo
Enkele protocollen
* Authentication Headers (AH)
	* Data integriteit
	* Origin authentication
	* Beschermt tegen replay attacks
		* Een opgenomen bericht wordt opnieuw verzonden om toegang te kunnen krijgen
	* Gebruikt ESP (Encapsulating Security Payloads)
* Security Associations (SAs)
	* Key exchange
	* Authentication
* Internet Key Exchange (IKE)
	* Wordt gebruikt om een beveiligde verbinding op te zetten met IPsec
		* IPsec werkt in laag 3
		* Verschilt van SSL omdat SSL op de browser werkt (laag 4/6/7)
		* Twee modes
			* Transport mode: only IP payload is encapsulated
			* Tunnel mode: the entire IP packet is encapsulated

## Hoofdstuk 13
### Netwerkprotocol
*	Een netwerkprotocol = een reeks aan regels voor communicatie tussen netwerkcomponenten
	*	Om met elkaar te communiceren, moeten ze hetzelfde protocol gebruiken
	*	OSI model
		*	Lagen 1 –2 (fysiek en data link: bekabelde, draadloze en optische netwerken)
			*	Verschillende protocollenvoor verschillende media
		*	Lagen 3 –4 (network en transport: routing schema’s, e\-mail, webapplicaties en beveiligde verbinding)
*	**Ethernet**
	*	Netwerkprotocol (IEEE 802.3) (Institute of Electrical and Electronic Engineers
		*	Laag 1 (fysiek) en laag 2 (data link)
		*	<> draadloos!
		*	CAT5\-kabel:    100 Mbit/s (0,1 Gbit/s)
			CAT5e\-kabel: 1000 Mbit/s (1 Gbit/s)
			CAT6\-kabel: 10000 Mbit/s (10 Gbit/s)
	* Verschillende protocollen voor verschillende media (draadloos, draad, ...)
* NIC (Network Interface Card)
	* Hardware\-kant van het netwerkverhaal
	* Insteekkaart die data omzet in elektrisch signaal (modulatie)
* MAC-adres (Media Access Control\-adres)
	* Ook physical address genoemd
	* 48\-bit met zes paar hex (IPv4)
	* 64\-bit met acht paarhex (IPv6, Firewire, ZigBee, ...)
	* Ingebakken in de NIC (the burned in address in chip, flash, ...)
	* Uniek identificatienummer (zou moeten zijn)
	* Oorspronkelijk Ethernet, nu ook WiFi, Bluetooth, ...
	* Voorbeeld:
		* MM:MM:MM:SS:SS:SS
		* 24 bits links = manufacturer (uitgereikt door IEEE)
			* 00:13:10, 00:25:9C en 68:7F:74 voor Cisco LinkSys
		* 24 bits rechts = specific device
			* 00:1D:7E:53:2B:09
	* **Spoofing**
		* Wijzig je MAC\-adres vanuit het OS
		* Om je eigen router op de werking ervan te controleren zit het wijzigenvan het MAC in bijvoorbeeld Windows in
* TCP/IP
	* Transmission Control Protocol/Internet Protocol
	* Suite met protocolsoGeadopteerd in de IT\-wereld door integratie in OS’en
	* Toepasbaar op diverse technologieën (Ethernet, Token Ring, ...)
	* Routable over diverse soorten netwerken (Windows, Apple, Linux, ...)
	* Ontwikkeld door Amerikaanse overheid (geen proprietary)
	* TCP = laag 4 (transport), IP = laag 3 (network)
	* Package fragmentation en reassembly
		* Twee header fields (IP header en TCP header)
		* Data field
		![net-basics.png](/net-basics.png)
		^Cybersecurity Essentials, ISBN 978-1-11936239-5 pagina 300^
	* Connecties opzetten (three\-way handshake)
		1. SYN (Synchronize)
		2. SYN (Synchronize) en ACK (Acknowledge)
		3. ACK (Acknowledge)
		4. Uitwisselen data (niet deel van de handshake)
		![threeway-handshake.png](/threeway-handshake.png)
		^Cybersecurity Essentials, ISBN 978-1-11936239-5 pagina 300^
	* Kwetsbaarheden
		* Attack of makeup of packets
			* Header manipulation
				* IP spoofing
					Manipuleren van source endestination IP in header
				* SYN flood (denial of service) exploits three\-way handshake
					Hacker stuurt vele SYN requests naar een server en spoofs IP\-adres of houdt ACK packet bij, waardoor er op de server allemaal connecties blijven openstaan en geheugen server volloopt
					![syn-flood.png](/syn-flood.png)
		^https://www.cloudflare.com/img/learning/ddos/syn-flood-ddos-attack/syn-flood-attack-ddos-attack-diagram-2.png^
		
*	**MAC** en TCP/IP
	*	MAC = laag 2, TCP/IP = laag 3
	*	**DHCP** (dynamic host configuration protocol)past **ARP** (Address Resolution Protocol) toe om een MAC\-adres aan een IP\-adres te koppelen
*	**IP\-adressen
	*	IPv4\-adressen**
		*	32\-bits (232\= 4.294.967.296 adressen)
		*	**Dotted decimal notation**
			*	XXX.YYY.ZZZ.AAA (vier 8\-bits velden of octetten)
		*	Voorbeeld:
			* 10000111.10001011.01001001.0011011 
				komt overeen met 135.139.073.054
				MSO LSO(Most en Least Significant Octet)
			* IPv4 classes
				* Class A: laatste drie octetten duiden host aan
					* Range van 001.x.x.x tot 126.x.x.x (hele grote netwerken)
					* 17 miljoen nodes (hosts) in elk van de 126 netwerken
				* Class B: laatste twee octetten duiden host aan
					* Range van 128.x.x.x tot 191.254.0.0 (medium netwerken)
					* 65.534 nodes (hosts) in elk van de 16 384 netwerken
				* Class C: laatste octet duidt de host aan
					* Range: van 192.x.x.x tot 223.254.254.0
					* 254 nodes (hosts) in elk van de 2 miljoen netwerken
				* **Subnetting**
					* Beperk het aantal bruikbare IP\-adressen voor hosts
						* Subnet mask verbergt of masks
							* 255.255.255.0 laat 10.0.1.1, 10.0.1.100, 10.0.1.255 toe, niet 10.0.2.5
							* Voordelen
								* Netwerkafscheiden
								* Efficiënt gebruik van IP\-adressen
								* Eén IP\-adres over meerdere fysieke locaties verdelen
			* **IPv6\-adressen**
				* 128\-bits (2128 of 3,4 x 1038adressen)
				* 16 octetten (32 hexadecimale getallen)
					* 2001:0db8:85a3:0000:0000:8a2e:0370:7334
				* Niet alle IPv6 kan je omzetten naar IPv4!
					* Er zijn meer IPv6 adressen dan IPv4
				* Bestaat uit twee delen
					1. Host = interface identifier
					2. Netwerk = network address (bepaald door ~~subnet mask~~ prefix)
				* In browser tussen vierkante haken
					* http://\[2001:0db8:85a3:0000:0000:8a2e:0370:7334\]
				* Aaneenliggende nullen weglaten met '::'
	*	
	| RFC1918 name | IP address range | Number of addresses | Largest CIDR block (subnet mask) | Host ID size | Mask bits | Classfull description |
	| :-- | :-- | :-- | :-- | :-- | :-- | :-- |
	| 24-bit block | 10.0.0.0 - 10.255.255.255 | 16 777 216 | 10.0.0.0/8 (255.0.0.0) | 24 bits | 8 bits | single class A network |
	| 20-bit block | 172.16.0.0 - 172.31.255.255 | 1 048 576 | 172.16.0.0/12 (255.240.0.0) | 20 bits | 12 bits | 16 contiguous class B networks |
	| 16-bit block | 192.168.0.0 - 192.168.255.255 | 65 536 | 192.168.0.0/16 (255.255.0.0) | 16 bits | 16 bits | 256 contiguous class C Networks |
				
* **Ethernet**
	* Familie van standaards die oplegt hoe de signalen moeten worden verstuurd
	* Half\-duplex: data kan in twee richtingen maar niet gelijktijdig
	* Hoe weten of datalijn in gebruik is?
		* **CSMA/CD** (Carrier Sense Multiple\-Access with Collision Detection) protocol
			* Node luistert eerst of de LAN in gebruik is
			* Bij gelijktijdig zenden door twee nodes, wachten elk willekeurige tijd met opnieuw zenden
      
## Hoofdstuk 14
### Understanding network servers
* Server = computersysteem dat services levert aan clients
	* Server op uitschuifbare rails
		* In een rack
		* In een kast
	* Soorten
		* Algemeen gebruik\-server (KMO)
		* Applianceserver (met gerichte hard\-en software)
		* Toepassingssoftwareserver (interactie met databases)
		* Mail server
		* Firewall server (internet gateway)
		* Proxy server (caching)
		* Webserver (website)
		* Database server (databases)
		* Terminal server (mainframes)
			A terminal server enables organizations to connect devices with a serial port to a local area network
		* Gateway server (to other types of networks)
		* DNS server (converteren naar ip\-adres)
		* Router server (shared resources van alle routers binnen het netwerk)
		* Bridge server (computergroepen verbinden)
		* FTP (file transfer protocol)
		* NAS (network attached storage)
		* SAN (storage area network)
		* RAS (remote access system: dial in op het LAN)
		* Print server (lokaal en remote)
		* DHCP (dynamic host configuration protocol)
	* Beveiliging
		* Shared resources beperken in rechte
		* Firewall om servers te beschermen
		* Account gegevens (password) hashen (versleutelen)
		* Subnetting / meerdere routers
		* Auditing

## Hoofdstuk 15
### Network connectivity devices
Switch
*	Verbindt apparaten binnen een LAN
*	Opvolger van hub 
	*	Hub stuurt alle gegevens naar iedereen door (broadcast)
	*	Hub verdeelt maximale bandbreedte over alle aangesloten nodes
*	Switch verdeelt de datapakketjes gericht tussen zender en ontvanger (peer to peer)
*	Soorten
	*	Verschillende soorten, verschil in routering
	*	Layer 2 (data link) = basisswitch
		*	MAC\-adressen als routering
		*	Data packet = frame
	* Layer 3 (network) = brouter (bridged router)
		* IP\-adressen als routering
		* Gebruikt hetzelfde protocol als een router
	* Layer 4 (transport) = router
		* Kan NAT (network address translation) toepassen om data te routeren
			\= omzetten van private ip\-adressen naar gateway\-ip\-adres en omgekeerd
	* Layer 7 (application)
		* Kan http\-protocol toepassen om data te routeren
			* Kijken naar URL, cookies, SSL session om pakketten sneller te routeren
	* VLAN
		* Virtual local area network
		* Beperkt de zichtbaarheid van delen van een netwerk
		* Communicatie langsheen geselecteerde poortenoTypes
			* Unmanaged
				* Out\-of\-the\-box: plug and play (PnP)
				* Geen setup nodig
			* Managed
				* Kan geconfigureerd worden voor een specifiek netwerk
				* Langs CLI (command line interface) of web based (SNMP\= Simple Network ManagementProtocol)
			* PoE

Router
*	Verbindt twee netwerken (bv. LAN met provider)
*	Routering met IP\-adressen
*	OS op routers
	*	Cisco System’s Internetwork Operating System (IOS)
		*	Andere Linux/Unix gebaseerde OS
	*	Soorten (bekabeld en draadloos)
		*	Edge
			*	Communiceert tussentwee netwerken (ISP en LAN)(internet dus)
			*	Staat op de rand (edge) van het netwerk)
		*	Core
			*	Communiceert binnenin een netwerk (op de backbone) voor high\-performance
			*	Verkeer tussen edge routers regelen
		*	Virtual
			*	Software routers
			*	Voordeel: makkelijk schaalbaar

Gateway
* Toesteldat twee netwerken verbindt, die elk een ander protocol gebruikt
	* Hardware\-en softwareprotocollen

Bridge
* Verbindt meerdere netwerksegmenten
* Broadcasts gaan naar alle poorten(blijven dus niet in netwerksegment)
* Voorloper van de switch

Kwetsbaarheden
* Fysiek beschermd (bv. server room, afgesloten kasten, ...)
* Uitschakelen van niet\-gebruikte services en programma’s
* MAC\-adressen filteren
* Configuratie van het toestel

Aanvallen
* Unauthorized access
* Packet sniffing
* ARP spoofing attacks
	* Vals ARP request sturen zodat IP naar fout MAC adres verwijst
* MAC flooding
	* MAC address table vullen op switch zodater geen nieuwe MAC adressen bijkunnen opswitch en alle berichten moet gaan broadcasten naar alle poorten
* Router flooding
	* Router overbelasten
* Denial of Service (DoS)
	* Een systeem overbelasten waardoor het niet meer goed kan functioneren
	* DDoS (Distributed DoS)
		* DoS met meerdere remote systemen tegelijk
* Session replay
	* Aanvaller bewaart een aantal IP pakketten, wijzigt deze en stuur ze dan weer uit om toegang te krijgen of andere ongewenste gevolgen
* Rerouting attack
	* Aanvallen die toegang heeft tot routingtables en zeaanpast
* Masquerade attack
	* Manipuleren van IP pakketten om vals IP adres te maken (valse identiteit) en daarmee toegang te krijgen tot het netwerk

Netwerkdefensie
* Data rate limiting
* Delayed binding
* Bogus IP address filtering
* Access control list
* Deep packet inspection
	* Zoeken naar signalen van virussen, spam of andere bedreigingenen zal bepalen op het pakket moet worden doorgestuurd of niet. Soms kan het zijn dat een verdacht pakket naar een speciale locatie wordt verzonden voor verder onderzoek.
* Packet filtering
	* Pakketten filteren op basis van hun source/destination adressen, poorten of protocols

Network hardening
*	Monitoring
*	Security policy
*	Alle netwerkapparaten up\-to\-date
*	Servers in het juiste netwerksegment, subnet of beveiligingszone (bv. achter een extra router)
*	ACL’s
*	Rollen nakijken
      
## NIST cybersecurity framework
> National Instituteof Standards and Technology (NIST)
### The framework
Het framework bestaat uit drie delen
1. the Framework Core
	* A set of cybersecurity activities and references that are common across critical infrastructure sectors and are organized around particular outcomes. The Framework Core comprises four types of elements: 
		* Functions
			* Identify
				Develop an organizational understanding to manage cybersecurity risk to systems, people, assets, data, and capabilities.
			* Protect
				Develop and implement appropriate safeguards to ensure delivery of critical services.
			* Detect
				Develop and implement appropriate activities to identify the occurrence of a cybersecurity event.
			* Respond
				Develop and implement appropriate activities to take action regarding a detected cybersecurity incident.
			* Recover
				Develop and implement appropriate activities to maintain plans for resilience and to restore any capabilities or services that were impaired due to a cybersecurity incident.
		* Categories
		* Subcategories
		* Informative References.
2. The Framework Implementation Tiers
	* A lens through which to view the characteristics of an organization’s approach to risk—how an organization views cybersecurity risk and the processes in place to manage that risk.
	* Geeft aan in welke mate een organisatie het framework gebruikten reageert op dreigingen(wachten tot er iets gebeurt, actief zoeken, ...)
	* Hoe hoger de tier, hoe beter
		* Tiers:
			* Tier 1: Partial
				Enkel iets doen als er een cybersecurity event plaatsvindt
			* Tier 2: Risk Informed
				Risicomanagement is toegelaten, maar is geen policy in de organisatie. Men is bewust dat er iets kan gebeuren, maar zal geen voorzorgmaatregelen nemen in heel de organisatie.
			* Tier 3: Repeatable
				Policy voor risicomanagement. Er worden regelmatig controles en updates gedaan.Iedereen in de organisatie is zich bewust van de risico’s en weet welke rol die speel hierin.
			* Tier 4: Adaptive
				Organisatie is continu bezig om beveilig te verbeteren. Er is een door iedereen gekende aanpak over hoe je met cybersecurity events moet omgaan.
3. The Framework Profiles
	* A representation of the outcomes that a particular system or organization has selected from the Framework Categories and Subcategories.
	* Geeft aan in welke mate de huidige implementatie overeenkomt met de gewenste implementatie van het framework core (categorieën en subcategorieën).
		* Current profile
		* Target profile

### Stappenplan
1. Prioritize and Scope.
	* Doelen vastleggen
2. Orient
	* Bekijken wat de opties zijn, oriënteren
3. Create a Current Profile.
4. Conduct a Risk Assessment.
	* Wat is de kans dat een cybersecurity event plaatsvindt?En wat is de impact?
5. Create a Target Profile.
6. Determine, Analyze, and Prioritize Gaps
	* Verschil tussen current profile en target profile bepalen. Vervolgens plan opstellen om deze verschillen op te lossen.
7. Implement Action Plan.

## Examen 
* Open vragen
* Voor examen hoofdstuk ~~1 – 25~~ 1 t.e.m. 15
* Je krijg NIST op het examen: geeft 2 categorieën en subcategorieën + leg uit
	* Zijn screenshots van het boek
* Risk assesment (met NIST)
* Poorten kunnen herkennen, naam, waarvoor het wordt gebruikt, input or output, ...
* Wat is een firewall en wat doet het?
* Alle namen van de 7 lagen van het OSI model kennen + kunnen uitleggen
* Three-layered rings of security zeker kennen
* IP en TCP header -> enkele voorbeelden kunnen geven van wat er in zit
* Verschillende types van switches kennen
* Mac address table
* Geef twee voorbeelden van besturingssystemen op routers
	* Cisco IOS
	* Andere Unix systemen
* **H5, H10 en H17 zeker nakijken: samenvattingen\+ examenvragen**

## Opdracht
Kernel attack slide 59
* Kernel praat met CPU
* Instructie die naar CPU gaan wijzige

4 kernel attacks in linux
* Welke commando’s
* Hoe kan je dan doen?
* Hoe kan je code in geheugen zetten zodat kernel die gaat gebruiken?
* ...

In document
*	Naam
*	Groep
*	4 titels (slide 59)
*	Gewoon copy\-paste van internet + bronvermelding 

## Einde
Met dank aan Pieter van der Deen's [Samenvatting](https://tmwiki.be/information_security/samenvatting_info_sec_pieter_vanderdeen.pdf).