---
title: Voorbeeld examen
description: Vragen die je kan verwachten op het examen en zelf gemaakte voorbeeld vragen.
published: true
date: 2021-06-13T17:51:11.963Z
tags: 
editor: markdown
dateCreated: 2021-06-12T14:14:52.981Z
---

# Voorbeeld examen/vragen OS Adv

Zelf gemaakte voorbeeld vraagjes + vragen van Phaedra. `(Phaedra)` wilt zeggen dat Phaedra deze vraag heeft gegeven of verwacht dat je dit kunt (in klas vermeld). Alle andere vragen zijn zelf gemaakt.

## 1. DNS

1. **Wat is name resolution?**
Het vertalen van een naam/URL naar IP

1. **Wat is het verschil tussen een authoritative name server en non-authorative name server?**
Authoritive antwoord direct met een IP, non-authoritive antwoord met een referentie naar een andere name server (per domein)

1. **Wat is een DNS resolver?**
Het deel van het besturingssysteem. Hier wordt eerst naar gekeken voor name resolution.
Dit beschikt caching en hosts file, als niet gevonden -> default dns.

1. **Geef een voorbeeld van recursive resolution voor info.website.com.**
Eerst bij root voor com, dan naar andere name server voor website.com, dan uiteindelijk authoritive nameserver voor info.website.com.

1. **Wat is reverse lookup? Voor wat is dit?**
Vertalen van IP naar naam. Wordt gebruikt voor filters, met naam werken is makkelijker, whitelisting.

1. **Geef wat typische records voor DNS server**
	  - A ipv4
    - AAAA ipv6
    - NS name server, geeft authoritative ns voor een specifieke zone (altijd samen met A of AAAA)
    - SOA start of authority, identificeert primary dns voor zone
    - MX Mail exchange
    - SRV Service record (AD)
    - PTR pointer (voor reverse dns)
    
1. **Wat is DNS forwarding? (Phaedra)**
Doorsturen naar een andere DNS als het niet in het domein/database (kan ook conditioneel etc) ligt.

## 2. AD 1 architecture

1. **Wat is een AD schema? (Phaedra)**  
Schema: definitie van de object, zegt welke velden er zijn, blauwdruk voor een object, structuur van een object.
Elk object heeft zijn structuur of velden (attributen), deze structuur wordt een schema genoemd.

1. **Wat is het nut van Forests?**  
Organisaties kunnen meerdere domains hebben. Forests geven de mogelijkheid om deze domeinen te groeperen in Forests. Hierbij wordt er een parent-child relationship toegepast.
In deze forest wordt er (bij default, aanpasbaar?) two-way trust toegepast.

1. **Leg uit wat de functional level van een domain is.**  
AD servers met een nieuwe versies hebben geen compatibiliteit met servers die oudere versies bezitten.
De functional level beschrijft de versie van de features die alle AD server gebruiken. Bij default is dit de versie van de meest outdated AD server.

1. **Wat zijn sites?**  
Sites reprensiteren een fysieke plaats. Hiermee kan een AD server weten waar resources zijn. Dit is nuttig voor authenticatie en replicatie. (Stel trage internet link tussen verschillende netwerken => lagere replicatie tijden en users op juiste domain laten inloggen).

## 3. AD 2 GPO's/user profiles

1. **Wat is een group policy?**  
Een collectie van gebruiker en computer configuratie instellingen.

1. **Op wat zijn GP's toepasbaar/te linken? Som ze op.**  
   - Computers
   - Sites
   - Domains
   - OU's

1. **Op wat kan een GP effect hebben? Licht deze extra toe (Phaedra)**  
   - *Computer*
     - Houdt geen rekening met welke user
     - Specifieke instellingen voor een computer (zoals netwerkinstellingen)
     - Toegepast wanneer de OS gestart wordt
   - *User*
     - Houdt geen rekening met op welke computer deze gebruiker inlogt
     - Specifieke instellingen voor een gebruiker (zoals rechten voor welke applicaties er beschikbaar zijn)
     - Toegepast wanneer de gebruiker inlogt

1. **Wanneer ik GPO's link aan mijn container, hoe kan ik verwachten dat ze toegepast worden? Wat heeft RSoP hier mee te maken?**  
Ze worden recursief toegepast. De GPO wordt toegepast op alle objecten in deze container (inheritance). Een meer specifieke GPO krijgt prioriteit. Het uiteindelijke resultaat noemt men de RSoP of Resultant Set of Policies.

1. **Wat is een WMI filter? Geef hierbij een mogelijke toepassing**  
Dit zijn filters die kan instellen om te limiteren op welke computers (a.d.h.v. hun attributen zoals os, cpu arch, windows server rollen, registry...) een GPO wordt toegepast.
Bv. Je wilt een GPO toepassen enkel op computers waarvan hun CPU een 32-bit architecture heeft.

1. **Wat is het nut van Loopback Processing op GPO's? (Phaedra)**  
Group Policy applies to the user or computer in a manner that depends on where both the user and the computer objects are located in Active Directory. In some cases, users may need policy applied to them based on the location of the computer object alone. You can use the Group Policy loopback feature to apply Group Policy Objects (GPOs) that depend only on which computer the user signs in to.

1. ***Picture of GPO's and organizational structure* Explain what the RSoP will be when user A is in place 1 and then when he moves to place 2 (Phaedra)**  
Je moet RSoP's kunnen vinden als je foto's/structuren krijgt. De volgorde dat GPO's worden toegpast vinden.

## 4. AD 3 LDAP

1. **Wat is LDAP voluit geschreven?**  
Lightweight Directory Access Protocol

1. **Wat is LDAP in het kort?**  
Een Directory Service. Deze geeft aan alles een locatie in een netwerk. Hiermee kan je ook queries uitvoeren naar objecten (je weet de exacte locatie van een object nog niet).

1. **Leg uit hoe LDAP gestructureerd is.**  
LDAP directory is een database waarbij alles georganiseerd is in een boom structuur. Startend van root zijn alle objecten uniek te vinden met hun locatie. Queries kunnen gemaakt worden naar een LDAP directory server/DSA (Directory System Agent), niet gevonden queries worden doorgestuurd. De LDAP directory zelf bevat sets van objecten (= entry) met attributen (zoals namen en waarden). Elke entry heeft hierbij een unique identifier/(r)DN (Relative) Distinguished Name.

1. **Wat definieert een AD schema? Geef hierbij een simpel voorbeeld.**  
Objecten met hun attributen.  Bv: een gebruiker bevat een naam, voornaam, email ... een schema defineert deze.

1. **Wat is het verschil tussen DN en RDN?**  
Distinguished Name van een object is eigenlijk het pad ernaar. Deze moet uniek zijn.
Een DN heeft attributen zoals C=/country, CN=/Common name, L=/Location, OU=/Organizational Unit ...
Relative Distinguished Name verwijst naar de naam van het object zelf. Deze moet uniek zijn in de OU waar het object insteekt.

1. **Wat is een SID? Wat een fout die vaak voor komt bij VMs?**  
Security Identifier/ID is een uniek nummer gemaakt door de windows server OS. Deze wordt toegekend aan een security principal object. In de achtergrond wordt hiermee gewerkt en niet gewone namen.
Wanneer je een VM cloned behoudt deze dezelfde SID. Dit zorgt voor conflicten, met sysprep kan je een nieuwe SID generen.

1. **Een object kan meerdere namen hebben. Som enkele voorbeelden op**  
   - Security principal name
   - Security identifier (SID)
   - LDAP name−Object GUID
   - Logon names (UPN, SAM)

1. **LDAP Query: `cn=TestUser,ou=Sales,dc=MyDomain,dc=com`. Wat is deze query in de gewone windows OS user interface voor gebruikers (Canonical name)?**  
Canonical name: MyDomain.com/Sales/TestUser

1. **Wat is een object GUID?**
Globally Unique IDentifier. Deze is unique, globaal over meerdere domeinen. Een SID is enkel unique binnen een domein. (Kopieren van een domein naar een andere = GUID hetzelfde, SID verandert).

## 5. AD 4 remote access

1. **Leg kort VPN uit en waarvoor het vaak gebruikt wordt**
Virtual Private Network gebruikt het internet/IP om te connecteren met een ander netwerk.
Er wordt een tunnel gemaakt tussen 2 gateways. De client verbind met de gateway, die communiceerd met de gateway op het ander netwerk die met de machines communiceert.
Default is tunnel **niet** encrypted. Client/server architecture.
![VPN](https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fwww.home-network-help.com%2Fimages%2Fxsite-to-site-vpn-network-diagram.jpg.pagespeed.ic.JtgVtK5Aut.jpg&f=1&nofb=1)
Dit wordt gebruikt om site-to-site te verbinden en/of remote access.

1. **Wat is tunneling?**
Encapsuleren van een protocol in pakketen van een ander protocol (IPsec, GRE (cisco)).
Dit zorgt ervoor da het netwerk het binnenste protocol niet moet supporten. Gewoon bv IP vanbuiten.

1. **Leg de CIA triad uit in context tot VPN**
	  - Confidentiality - encryptie (enkel leesbaar voor wie het is)
    - Integrity - data (= aangekomen)
    - Authentication - van de sender (betrouwbaar ID, atrr of origin)
    
1. **Wat is non-repudation?**
Onweerlegbaarheid. Je kan niet zeggen dat je het niet verzonden hebt/ontvangen hebt. Er is bewijs.
Bv: Als je iets koopt online kan je niet ontkennen dat dit niet gebeurt is.

1. **Wat is het nadeel van symmetrische encryptie?**
Beide partijen moeten dezelfde secret key hebben voor encryptie en decryptie. Deze moet je dus kunnen leveren. Hoe kan je dit veilig doen?

1. **Leg asymmetrische encryptie uit (Diffie-Hellman). (Phaedra)**
[Video voor uitleg.](https://youtu.be/NmM9HA2MQGI)
Public key wordt gemaakt adhv van de private key.
Moeilijk om de private key van de public key te halen. (wiskunde, grote priemgetallen)
Beide partijen combineren hun private key met de public key = hetzelfde
Deze gebruikt voor encryptie en decryptie.
Dit is het meest gebruikte algoritme in praktijk.

1. **Welke soort encryptie gebruikt IPsec dan? Waarom?**
IPsec gebruikt symmetrische encryptie waarvan de keys assymetrisch gedeeld werden.
Symmetrische encryptie is sneller.

## 6. Mail

1. **Wat is MTA voluit en welk protocol gebruikt dit?**
Message Transfer Agent. SMTP (Simple Mail Transfer Protocol).

1. **Wat is MAA voluit en welk protocol gebruikt dit?**
Message Access Agent. IMAP4 en POP3.

1. **Wat is het verschil tussen deze protocollen?**
SMTP wordt gebruikt voor het sturen van e-mails (outbound) (sender to server, server to server), send = "push". IMAP en POP wordt gebruikt voor het ontvangen van e-mails (inbound), receive = "pull".

1. **SMTP was vroeger weinig beveiligd. Geef een korte samenvatting van deze evolutie.**
    - Vroeger weinig tot geen beveiliging
    - Whitelisting van locatie met IP-addressen
    - Authenticatie van users/clients
    - SSL encryptie
    - IMAP kan simpel weg aangepaste headers bevatten (plain text), dus kan je gewoon je naam en email aanpassen/spoofen.
      - Certificaten worden meegeleverd om de authenticiteit te verifiëren.

1. **Geef eigenschappen van POP.**
Post Office Protocol:
    - *Download-and-delete principle*
    - Gaat er van uit dat er maar 1 client is
    - Voor clients dat niet altijd online zijn
    - Bespaard op storage (mails worden na pull verwijderd op server)
      - ISP email accounts blij :) -> storage = moneyyysss
    - POP3 heeft authenticatie methodes, eerst werden credentials in plain-text meegegeven

1. **Geef eigenschappen van IMAP.**
Internet Message Access Protocol:
    - Meerdere clients, zelfde mailbox mogelijk
    - *Mails blijven op de server tot manueel delete*
      - kan gecached worden op device
    - Gebruikt flags zoals "read", "replied", "deleted"
    - Meerdere mailboxes als folders mogelijk
    - Server-side searches
    - Extensions mogelijk
      - Bijvoorbeeld GMail threads.

1. **IMAP of POP, wat gebruiken web-mails?**  
IMAP heeft hier het grotere voordeel aangezien de mails niet verwijderd na dat ze binnegetrokken zijn. Als dat gebeurt voor een web-mail zouden al je mails verdwijnen als je de sessie sluit (of ze moeten lokaal opgeslagen worden in enorm grote cookies).

2. **Wat is MIME? (Phaedra)**  
Multipurpose Internet Mail Extensions is een internet standaard dat de basis mail format uitbreidt. Voegt support toe voor meer character sets (wordt nog steeds verzonden als ASCII, maar met extra informatie van MIME door ontvanger terug gezet. Met deze header/extension kan je ook attachments sturen zoals audio, video, foto's en applicatie programma's.

## 7. AD 5 Global Catalog

1. **Waarvoor dient de global catalog?**  
    - Zoeken naar objecten
        - User searches (LDAP) voor directory info
        - Alle domeins in forest (+trust relationships van andere forests)
    - Valideren van object references
        - Wanneer een object een reference heeft naar een object in een ander domein
    - User principal name authentication
        - Normaal gezien door DC maar users van andere domains -> DC heeft GC server nodig

1. **Geef de stappen die doorlopen worden bij een user authentication aan de hand van een GC server.**
		
    - Zoek naar DC's in site van client
    - Query van user om DN te vinden (user@domain -> DN)
    - GC server antwoord op deze query
    - DC geeft antwoord terug
    - Gebruiker logt in op juiste DC
    
1. **Welke records in een DNS server gebruiken clients/domains om DC's te vinden?**
SRV records.

1. **In welke partities is een AD database (logisch) gescheiden? Beschrijf ze kort.**
		
    - Schema (Phaedra)
    		- Informatie per forest over hoe alle objecten en attributen gedefinieerd worden
        - Repliceert naar alle DCs in forest
        - Maar 1 *schema master*
    - Configuration
    		- Info over AD structuur in forest (domains, sites, ADs, services)
        - Repliceert naar alle DC's in forest
    - Domain
    		- Info per domain over Users, groups en OUs
        - Repliceert naar all DC's in domein (opgeslagen in global catalog)
    - Application
    		- Geplaatst in, child van domain part, child van app. part, new tree in forest
        - Informatie over applicaties duh
        - eg. ForestDNSzones worden naar alle DCs en dns servers repliceert, DomainDNSzones is uniek per domain en wordt enkel naar DCs gestuurd die een DNS server zijn
        - Niet repliceert naar global catalog
    - Global catalog
    		- Enkel op DC dat een global catalog server is
        - Repliceert naar alle GC servers in forest
    
1. **Leg schema master uit. (Phaedra)**
Een schema is een blauwdruk voor object en hun attributen (regels voor het maken en manipuleren van objecten). Er is 1 schema partition per forest, deze informatie wordt repliceert naar alle domain controllers. De schema master is de enigste DC waarop het schema kan geupdate worden.

1. **Leg uit wat een trust relationship is**
Relatie tussen 2 domeinen. Dit laat toe om gebruikers in te authenticeren in andere domains. In te stellen: Geef gebruikers toegang aan resources van andere domains. Admins kunnen gebruikers in andere domains beheren.

1. **Wat is de standaard trust relationship in AD?**
Two-way en transitief. Authenticatie passeert in twee richtingen.
Het is transitief omdat als A B vertrouwt en B C zal A C vertrouwen.

1. **Waarom zou je meerdere forests hebben?**
Wanneer elke forest apart moet geconfigureerd worden en andere access control moet hebben. Een nieuw domain bij een forest wordt automatisch geconfigureerd. Wordt ook toegevoegd aan global catalog. Access control tussen forests moet expliciet ingesteld worden.

1. **Ik probeer in te loggen op domain B als user uit domain A. Gaat dit als de twee domains in dezelfde forest zitten?**
Ja. Er is two-way, transistive trust tussen domains in een forest. Dit laat toe om in te loggen en te authenticeren op een computer op eenderd welk domain, dit betekent niet dat je rechten en permissies hebt in alle domeinen.

1. **Wat zijn de taken van een RID master? ((Phaedra)/vaak uitgelegd tijdens les)**
(1 per domein in een forest) Geef een pool van RIDs van de globale pool aan andere DCs. Op deze manier wordt SID conflict vermeden en kan een DC nieuwe security principal objects aanmaken (tot de pool leeg is). Wanneer een object tussen domains verplaatst wordt moet de DC de RID master aanspreken. Als je een DC wilt toevoegen/maken moet de RID master online zijn om een RID pool te kunnen geven.

## 8. AD 6 access control, groups

1. **Wat is de naam van de voorgekeurde mutual windows authentication?**
Kerberos

1. **Leg uit wat Kerberos is.**

   	- 3-part authentication
    - Passwoord is enkel verstuurd voor een ticket
    - Authenticatie met tickets
    
1. **Welke delen heeft Kerberos? (Denk aan cerberus)**
![Cerburus](https://static.wikia.nocookie.net/hades_gamepedia_en/images/4/45/Cerberus.png/revision/latest/scale-to-width-down/628?cb=20181210043935 =x150)
	  1. SS: Service Server
    2. *AS: Authenticating Service*
    3. *TGS: Ticket Granting Server*
    - *Italic* = deel van KDC (Key Distribution Service/Center) op AD

1. **Leg een authenticatie process uit a.d.h.v. Kerberos.**
	  1. Client authenticates with Authentication Server (AS)
    2. Client get a time-stamped Ticket-Granting-Ticket (TGT) (you may get tickets)
    3. Client wants to access a service:
    	a. Sends TGT (ticket) to TGS (Ticket Granting Server)
      b. If TGT accepted by TGS -> ticket + session key
      c. Client uses these for access to service
      
1. **Wat is NTLM dan?**
Dit is een challenge/response authenticatie (vermijden dat password naar server gestuurd wordt).
Dit wordt gebruikt als Kerberos authenticatie niet gebruikt kan worden, bv:
	  - Client auth met andere AD server forest zonder inter-forest trust
    - Client auth met AD server dat niet in een domain zit
    - Geen AD (workgroup of p2p)

1. **Leg de stapjes van een NTLM challenge-response uit (client <-> server <-> AD).**
	  1. Users sends access request
    1. Server sends a challenge message (16-byte random number)
    1. Client encrypts challenge with hashed password and sends encrypted response to server
    1. Server sends challenge and response to domain controller
    1. Domain controller compares challenge and response to authenticate user
    1. Server sends response to client
    
1. **`Folder1/Folder2/Folder3/doc.txt`
Hierbij geldt: Folder1 heeft modify, Folder2 full access, Folder3 read-only.
Welke rechten heb je voor doc.txt?**
Met precendence werken/last writer wins. => read-only

1. **Leg precendence uit van allow en deny permissions.**
	  - Deny overschrijft allow op hetzelfde level of parent level.
    	- ~~Allow~~
      		- **Deny** + ~~allow~~
    - Allow overschrijft deny op lagere parents of op object
    	- ~~Deny~~
      		- Allow
        		- Object
    	- ~~Deny~~
      		- Object: allow
          


