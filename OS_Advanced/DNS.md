---
title: DNS
description: Labo 1 informatie proberen bundelen
published: true
date: 2021-02-18T18:24:58.419Z
tags: 
editor: markdown
dateCreated: 2021-02-18T17:52:43.495Z
---

# DNS
Even een korte samenvatting van dingen die je moet weten voor het eerste labo.
> Wanneer je een clone maakt van een windows server moet je sysprep uitvoeren (dit staat vanonder in het document van het labo)
{.is-warning}

> Het is niet de bedoeling dat je het labo document negeert, als het compleet was heb ik het hier niet overgenomen!
{.is-warning}

## static ip
Static ip's toekennen op windows server is hetzelfde als op windows 10 maar hier nog even een uitleg:

Open control panel > Network and Internet > Network and sharing center > change adapter settings
Kies dan de juiste adapter, rechter muisklik > properties > kies ipv4/ipv6 > properties
Opgelet: De dhcp server heeft ook een range, kies dus geen ip adressen binnen deze range!
![static_ip.png](/os_advanced/static_ip.png =850x)


## DHCP

Nu moeten we een dhcp server rol op een van de servers maken.
[Deze site](https://computingforgeeks.com/how-to-install-and-configure-dhcp-server-on-windows-server/) heeft een handig stappenplan, je zal natuurlijk niet exact kunnen kopiëren

## Client
Maak een master windows 10 VM
Maak een clone en test of deze een ip krijgt van de dhcp server.

## Web server
Zie labo document

## DNS server setup
[Deze site](https://computingforgeeks.com/install-and-configure-dns-server-in-windows-server/) heeft een handig stappenplan om een dns rol op te zetten in windows server 2019, je zal opnieuw waarschijnlijk niet zomaar kunnen kopiëren

## DNS forward delegatie
[Deze site](https://computingforgeeks.com/how-to-add-dns-forward-lookup-zone-in-windows-server/) heeft hier opnieuw een stappenplan voor
