---
title: Voorbeeld examen
description: 
published: true
date: 2021-01-22T23:33:06.214Z
tags: 
editor: markdown
dateCreated: 2021-01-21T16:23:45.370Z
---

# Voorbeeld examen
Te kunnen examen vragen zijn vragen (/vragen over leerstof) die leerkracht benadrukt heeft tijdens de les. Extra vragen zijn vragen gemaakt door leerlingen.

De vragen kan je open doen voor het antwoord door er op te klikken.

**Theorie examen zijn open vragen, geen meerkeuze.**
Voor NIST en vele andere vragen is het vooral dat je uitleg en redenering goed is. Soms is dat zelfs belangrijker dan het antwoord zelf, dus voluit en doordacht opschrijven!
## Te kunnen examen vragen
<details>
  <summary markdown="span">Waarvoor staat de CIA triad?</summary>
  Confidentiality<br>
  Integrity<br>
  Availability<br>
</details>
<details>
  <summary markdown="span">Waarom is een bewakingsagent vaak beter?</summary>
  Inschattingsvermogen, intuiteit, betere beslissingen, klanten kunnen vragen stellen richtlijnen ...
</details>
<details>
  <summary markdown="span">Pas de 3 perimeters toe op een een computer.</summary>
  De outer perimeter stelt de behuizing en hardware voor.<br>
  De inner perimeter stelt de OS en programma's voor.<br>
  De interior is data opslage zelf (bv. encryptie is hier toepasselijk)
</details>
<details>
  <summary markdown="span">Leg het pad dat je moet afleggen als je van USB naar de CPU wilt gaan.</summary>
  Obscure vraag dat je kan leren op hft6-10 ppt slide 31.<br><br>
  
  **antwoord:**

**USB -> southbridge -> northbridge -> CPU**
  
  Hierbij moet je een pad kunnen uitleggen, maar je moet het hele schema niet kennen.
  Rare obscure vraag dus breek je hoofd er niet over.
  **Tips:** CPU met northbridge (snel: RAM, PCI-E(xpress)), northbridge met southbridge (trager: PCI, USB, Audio ...)
</details>

<details>
  <summary markdown="span">Verschil tussen patch en update?</summary>
  Patch: kleine fixes. Vooral en vaak security. Verandert functionaliteit NIET. Oke om automatisch te laten gebuiren.<br>
  Update: verandert de applicatie wel. Breekt vaak dependenties. Niet veilig te automatiseren
</details>

- [Geef het volledige OSI-model](/en/Information_Security/OSI-model)

<details>
  <summary markdown="span">Wat is TTL en waarom is het nodig?</summary>
  Time To Live. Het is nodig omdat anders sommige packets kunnen blijven rond gaan op het <a href="https://en.wikipedia.org/wiki/Network_topology">web.</a>
</details>

<details>
  <summary markdown="span">Geef de 3 IP classes</summary>
  Je moet de nummers niet vanbuiten kennen (zoveel hosts etc). Subnetting is voor OS-fundamentals.
  
  Class A: Hele grote netwerken
  Class B: Medium netwerken
  Class C: Privé netwerken
  
</details>

<details>
  <summary markdown="span">Geef de Three-layered rings of security (perimeters).</summary>
  
1.  Outer perimeter:
	- Laag 1 (fysieke laag)
	- Beveiligen van datakabels en netwerkapparatuur
  
2.	Inner perimeter
	- Laag 2 (data link)
	-	Data kan hier aanvaard worden, geweigerd of doorgestuurdop basis van de identiteit
  
3.	Interior perimeter
  -	Laag 3-7
  -	Bijvoorbeeld: laag 4 met het blokkeren van poorten
  -	laag 7 is de meest aangevallen laag (zie later)
</details>

## Vragen zonder antwoord
- Framework V1.1 NIST document: verlijking met andere frameworks in appendix A (framework core).
- Je bent in staat om met NIST vragen op te lossen. Risico analyse.
- pagina van Enisa met wat vragen.

## Extra vragen
<details>
  <summary markdown="span">Wat zijn belangrijke specificaties voor een camera?</summary>
lux waarde (licht gevoeligheid)
<br>
-Hoe lager, hoe beter: De camera kan projecten zine in het donker

Resolutie:
    -Analoog: aantal horizontale lijnen
    -digitaal: aantal pixels
</details>
<details>
  <summary markdown="span">Wat is IR op een IP camera en hoe werkt het?</summary>
  InfraRood.
  ...
</details>
<details>
  <summary markdown="span">Wat is een fisheye lens?</summary>
ziet een hele kamer maar met vervormingen
</details>
<details>
  <summary markdown="span">Meerdere factoren spelen een rol bij authenticatie. Welke?</summary>
    Kennis/Knowledge: wat de persoon weet<br>
    Bezit/Possesion: wat de persoon heeft<br>
    Erfelijkheid/inheritance: wat de persoon is<br>
    Locatie/Location: waar de persoon is
</details>
<details>
  <summary markdown="span">Wat is 2FA?</summary>
    Two-factor authentication.<br>
  	Hierbij gebruik je twee vormen van de vorige vraag.
</details>
<details>
  <summary markdown="span">Wat is hot-swapping?</summary>
  Toevoegen of verwijderen van hardware wanneer het systeem actief is.<br>
  Bijvoorbeeld USB-stick is hot-swappable. 
</details>
<details>
  <summary markdown="span">Pas de 3 perimeters toe op een een computer.</summary>
  De outer perimeter stelt de behuizing en hardware voor.<br>
  De inner perimeter stelt de OS en programma's voor.<br>
  De interior is data opslage zelf (bv. encryptie is hier toepasselijk)
</details>
<details>
  <summary markdown="span">BIOS/UEFI security voorbeelden?</summary>
  Wachtwoord, poorten ...
  BIOS of UEFI is de eerste plaats waar sofware wordt gebruikt. Dit is dan ook de beste plaat som te 	starten als een hacker.
</details>

<details>
  <summary markdown="span">Wat bedoelen ze met de term hardening?</summary>
  Een computersysteem beveiligen, harder maken om in te breken.<br>
  Zoals in de vorige vraag is wachtwoord in BIOS een vorm van hardening.
</details>

![port_centronics_parallel_36_pin.png](/ports/port_centronics_parallel_36_pin.png =200x)
![port_mini-vga.png](/ports/port_mini-vga.png)
![port_db25_serial_com_port.png](/ports/port_db25_serial_com_port.png)
<details>
  <summary markdown="span">Geef de poorten en of ze gevaarlijk zijn of niet.</summary>
  Centronics parallel 36 pin, ja.<br>
  mini-vga, nee.<br>
  db-25 serial com port, ja.<br>
</details>
<details>
  <summary markdown="span">Geef een paar soorten servers.</summary>
  Mag echt van alles zijn, niet te ver zoeken. <br>
  Webserver, DNServer, DHCP server, Algemeen gebruik-server, Mail server, Proxy server, Database server, NAS, FTP, ... <br>
  Meer op slide slide 79 hfst11-17 ppt.
</details>

<details>
  <summary markdown="span">Wat is encryptie?</summary>
  Het coderen/versleutelen van data (op basis van een algoritme).<br>
  Je hebt dus een code/sleutel nodig om de data te kunnen lezen/decrypten/decoderen.<br><br>
  Meeste OS's hebben een vorm van encryptie in hun FS.
</details>

<details>
  <summary markdown="span">Wat is een directory traversal attack?</summary>
  Backtracking of climbing van directories (waar je eigenlijk niet mag zijn.)<br>
  Dit is vaak door slecht geschreven software of slechte (web)servers.
</details>

<details>
  <summary markdown="span">Hoe kan je brute force logins tegengaan?</summary>
	Maximal login attempts. Verplichte wachtduur tussen attempts. Captcha's (Of combinatie)
</details>

<details>
  <summary markdown="span">Geef 5 soorten malware (behalve die de vraag eronder bevatten).</summary>
	Worms, (Trojan Horse), rootkits, (ransomware), spyware, adware, (logic bombs), zombies, botnets ...
</details>

<details>
  <summary markdown="span">Leg logic bombs, trojan horse en ransomware uit.</summary>
  Trojaans paard (lijkt een betrouwbaar programma te zijn, verspreid zichzelf niet)<br><br>
	Logic bombs: delete data, zoals een trojaans paard met betrouwbare software, activeert zichzelf op een logisch moment, na x dagen, na het gebruik van xkeer van het programma, malicious code zit in heel veel lijnen gewone code vervat.<br><br>
  Ransomware: encryptie van data met vraag om losgeld
</details>

<details>
  <summary markdown="span">Wat is een service pack?</summary>
	Grote hoeveelheid patches en updates in 1. Altijd back-up -> kan onstabiel zijn.
</details>

<details>
  <summary markdown="span">Leg uit wat een grey hat hacker doet.</summary>
	Werkt vanuit overtuiging (kan dus ethisch zijn), overschrijdt wettelijke grenzen.
</details>

## Afkortingetjes

|Afkorting|Voluit|
|:--|:--|
|POSIX|Portable Operating System Interface|

