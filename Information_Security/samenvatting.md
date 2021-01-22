---
title: Samenvatting Info Sec
description: Samenvatting  Info Sec van 2020/2021 gemaakt door Pieter van der Deen
published: false
date: 2021-01-22T08:46:57.131Z
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
* **N**ational **I**nstitute of **s**tandards and **T**echnology
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

[comment]: <> (CSS Only works in preview)
<style type="text/css">
 	/* Indent Formatting */

  ul li {list-style-type: circle;}
	ul ul  li {list-style-type: disc;}
	ul ul ul li{list-style-type: square;}
   
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