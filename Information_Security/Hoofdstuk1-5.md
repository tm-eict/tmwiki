---
title: Hoofdstuk 1-5
description: 
published: true
date: 2021-04-22T13:11:43.312Z
tags: info-sec
editor: markdown
dateCreated: 2021-04-22T13:11:37.948Z
---

## Cia Triad
![CIA TRIAD](https://blog.jamestyson.co.uk/wp-content/uploads/2019/09/CIA-triad.png =384x)

  1. Availability
    	- Data moet beschikbaar zijn wanneer het nodig is
        - Netwerk, authenticatie, redundante hardware, Back-up
        - RAID: Redundant Array of Inexpensive/Independent Disks

  2. Integrity
    - Betrouwbaarheid
     bv: telefoonnummers in gids

  3. Confidentiality
    - Gevoelige data beschermen van ongemachtigde gebruikers
      - militaire classificatie
        - **Top secret:** need to know
        - **Secret:** beperkte toegang
        - **Confidential:** eigendomsdocumenten
        - **Sensitive but unclassified:** intern gebruik
        - **Unclassified:** geen schade
      TSCSU:  U.S Can Stop Terrorism (reversed)

  	  - Commerciële indeling
        - **Confidential:** heel erg gevoelig
        - **Sensitive:** intern gebruik
        - **Public:** Geen impact, publiek toegankelijk

  - Technologie
      - Encryptie
  - Non-repudiation
      - Er moet onbetwistbaar bewijs zijn dat de partijen data ontvangen hebben zodat ontkenning niet mogelijk is

## Cyber Security Frameworks
  - Enisa (Europa)
  - NIST (Appendix C)
    - ID identify
    - PR protect
    - DE detect
    - RS respond
    - RC recover
## Infrastructure security
- Drie basisregels
  - Acces-control  en monitoring
    - Fysieke toegang vermijden
      - ingress = recht om binnen te gaan
      - egress = recht om buiten te gaan
      - regress = recht om opnieuw binnen te gaan
  - Video surveillance
  - Intrusion detection
- Exclusion en inclusion
  - Exclude non authorized people
  - Include authorized people

- Perimeter
  - Outer perimeter = fysieke afbakening terrein
    - Natuurlijke elementen
      - hagen, paadjes,bomen,waterlopen
    - Territorial enforcement
      - Apparaten (camera's, poorten, acces-control, intrusion-detection)
        - Schuif en draaipoorten
          - Kaartenlezer (Je kan kaarten kopiëren)
          - Radiosignalen (Je kan het signaal ontvangen en repliceren om binnen te komen)
          - Numerieke toetsen (Met warmte camera kan je de volgorde waarin toetsen zijn ingedrukt bepalen)
      - Borden

  - Inner perimeter = De muren, deuren,ramen
    - Sloten: manueel of elektronisch
      - Solenoid: verschillende configuraties mogelijk
        - tailgating (Sluit automatisch na binnengaan)
        - emergency exit (Sluit automatisch wanneer stroom uitvalt)
      - Cijferslot
  - Interior = binnen
    - Alarmsystemen
    - Receptionist
    - Bewakingsagent
    - Authenticatie
      - Knowledge (Wat weet de persoon, bv: pincode)
      - Possession (Wat heeft persoon in bezit, bv: bankkaart)
      - Inheritance (Wat is de rol van de persoon)
      - Plaats (waar is de persoon)
      
      - Kaarten
        - Met magnetische strip
        - Smart cards (chip op kaart)
          - ID: PII (Personally Identifiable Information)
          - Zichtbaar
            - rijksregisternummer, label, geldigheidsperiode, plaat van uitgave, familienaam en voornamen, nationaliteit, geslacht, geboortedatum, geboorteplek, foto
            - op chip: adres, idnetificatiecertificaat (eID kaartlezer), handtekeningcertificaat (digital signing)
  
  ![epassport.png](/information_security/assets/epassport.png =384x)

  - Logische perimeter = grenzen tussen netwerken, local hosts...
- CPTED
  - Crime prevention through environmental design
  - Ontwerp gebouw en omgeving ontmoedigt criminelen
