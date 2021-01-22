---
title: Samenvatting Info Sec
description: Samenvatting  Info Sec van 2020/2021 gemaakt door Pieter van der Deen
published: false
date: 2021-01-22T09:51:21.059Z
tags: 
editor: markdown
dateCreated: 2021-01-21T21:04:57.092Z
---

# Samenvatting Info Sec
Met dank aan Pieter van der Deen's [Samenvatting](https://tmwiki.be/information_security/samenvatting_info_sec_pieter_vanderdeen.pdf).

## CIA-driehoek
[comment]: <> (remove white background of img)
[![cia-triad](/cia-triad.png)](https://blog.jamestyson.co.uk/the-cia-and-dad-triads)
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
	2. **Video surveillance ** systems (H3)
	3. ** Intrusion-detection** and reporting systems (H4)
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
					https://www.ifpo.org/news/power-cpted-glue-holds-security-programs-together-bill-nesbitt/#post/0
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