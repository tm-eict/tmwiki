---
title: Samenvatting Info Sec
description: Samenvatting  Info Sec van 2020/2021 gemaakt door Pieter van der Deen
published: true
date: 2021-01-22T13:18:25.811Z
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
					* **Inheritance**: rol van de gecontroleerde persoon verantwoordelijkheden)
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
	* **Erfelijkheid/nheritance**: wat de persoon is
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
* USB-poort (Universal Serial Bus poort)
	* Daisy chains met USB-hub
	* Indien rechtsreeks op mobo, uit teschakelen in CMOS setup
	* **Hot-swapping**: toevoegen of verwijderen wanner het systeem actief is
	* IDE (Integrated Drive Electronics) (Nu PATA genoemd = Parallel Advanced Technology Attachment); zorgt voor transport van data tussen ROM en RAM; tegenwoordig wordt SATA gebruikt (Serial ATA)
	* ![usb-ports-1](/usb-ports-1.png)
		^http://www.beginnerslessenpc.nl/USB%20Kabels%20Verschillen.htm^
	* ![usb-ports-2](/usb-ports-2.png)
		^https://www.cablestogo.com/learning/connector-guides/usb^
	* ![usb-ports-3](/usb-ports-3.png)
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
  
<style type="text/css">
 	/* Indent Formatting */
  /* Format: 1-a-i-A-1-I */
   ol { list-style-type: decimal;}
   ol ol {list-style-type: lower-alpha;}
   ol ol ol { list-style-type: lower-roman;}
   ol ol ol ol { list-style-type: upper-alpha;}
   ol ol ol ol ol { list-style-type: decimal;}
   ol ol ol ol ol ol { list-style-type: upper-roman;}
   /* https://www.w3schools.com/cssref/pr_list-style-type.asp */
   /* https://stackoverflow.com/questions/11445453/css-set-li-indent */
   /* https://stackoverflow.com/questions/13366820/how-do-you-make-lettered-lists-using-markdown */
</style>