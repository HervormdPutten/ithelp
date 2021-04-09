---
title: "Migratie"   
weight: 1    
description: Informatie over de migratie van Solcon naar Microsoft 365.
---

## Uitleg

In het verleden hadden we alle emailadressen ...@hervormdputten.nl bij Solcon. Nu gaan we alle emailadressen overzetten
naar Microsoft 365. De emailadressen die we aanmaakten bij Solcon waren steeds emailadressen die horen bij een
functie/ambt binnen de kerk. Een gemeentelid bekleedt die functie voor een bepaalde tijd en dan neemt iemand anders die
functie over. Zo'n wisseling vraagt ook altijd het overdragen van de bijhorende mailbox inclusief wachtwoord. Het
wachtwoord wordt vaak genoeg niet aangepast, daarmee zou de voorganger ook nog toegang kunnen houden. In de nieuwe
structuur krijgt iedereen een **persoonlijk account**, met bijbehorende persoonlijke mailbox. Daarnaast word voor een
functie een gedeeld postvak aangemaakt. Degene die de functie bekleed, krijgt toegang. Bij overdracht is het mogelijk
dat tijdelijk 2 personen toegang hebben, maar na verloop van tijd worden de rechten van de eerste persoon ingetrokken.

De reden om het op deze manier te doen is dat er geen wachtwoorden worden overgedragen en als iemand een andere functie
krijgt binnen onze gemeente blijft de toegang hetzelfde met hetzelfde account. We hebben met OwnCloud ervaring opgedaan
met deze manier van werken, en dat werkt er fijn. Het geeft ons ook precies inzicht in wie toegang heeft tot welk
account.

## Stappenplan

Hieronder is een stappenplan beschreven hoe we de migratie per emailadres gaan doen. Als er vragen zijn, dan kan er
altijd een email gestuurd worden naar ithelp@hervormdputten.nl

1. Een [persoonlijk account](../../account) wordt aangemaakt, dit is een emailadres als <voornaam>.<achternaam>
   @hervormdputten.nl.    
   Accountgegevens worden automatisch toegestuurd naar het opgegeven prive emailadres. Controleer of
   de [toegang](../toegang) werkt.
1. Een [gedeeld postvak](../gedeeldpostvak) wordt aangemaakt. Controleer ook of het werkt en verstuur een bericht vanuit
   het gedeeld postvak naar je prive emailadres.   
   LET OP: Een email versturen naar het gedeeld postvak, komt nog bij het emailadres bij Solcon terecht, meer details
   zie hieronder bij 'email tijdens migratie'.
1. Als beide goed werken, bevestig dit dan naar ithelp@hervormdputten.nl.
1. Het emailadres bij Solcon wordt nu weggehaald. Vanaf nu gaat alle email naar het gedeelde postvak.

## Overzetten oude emails

Er zijn 2 situaties mogelijk: u heeft alle oude emails op uw computer / laptop of oude emails staan nog bij Solcon,
bijvoorbeeld als u gebruik maakt van de Webmail van Solcon.

### Overzetten van oude emails vanaf de Solcon Webmail

Alle email die nu nog bij Solcon opgeslagen staat, kunnen we in **importeren bij Microsoft 365**. Daarvoor is het nodig
dat de huidige gebruikersnaam en het bijbehorende wachtwoord doorgegeven worden, dan kunnen we alles overzetten. Dan
zijn ze daarna beschikbaar in het nieuwe gedeeld postvak.

### Overzetten van oude emails vanaf uw computer/laptop

#### PST bestand

Als u nu Outlook gebruikt, dan kunt een PST bestand aanmaken (of het is al opgeslagen in een PST bestand). We kunnen een
PST bestand laten importeren bij Microsoft 365.

#### Met IMAP

Een andere mogelijkheid is om in uw email programma het nieuwe postvak te openen met behulp van IMAP. Daarna kunnen dan
de emails verplaatst worden naar het gedeeld postvak.   
Zie [gedeeld postvak](../gedeeldpostvak) voor meer informatie over IMAP.

## Emails **tijdens** de migratie periode

{{% alert title="Zo kort mogelijk" color="warning" %}} Het doel is om deze migratie periode zo kort mogelijk te houden,
om verwarring te voorkomen, maar er gaan geen emails verloren in deze periode {{% /alert %}}

Als het emailadres is aangemaakt bij Microsoft 365 dan bestaat het emailadres dus op 2 plekken en dat kan verwarring
opleveren.   
Versturen gaat altijd goed en werkt vanaf beide plekken.   
Als mensen reageren of zelf een email sturen, komt de email aan op 1 van beide plekken en het hangt ervan af waar het
vandaan verstuurd word.

* De verzender heeft een account binnen Microsoft 365?   
  :arrow_right: Dan komt de mail binnen bij het gedeelde postvak bij Microsoft 365.
* De verzender heeft een emailadres buiten Microsoft 365?   
  :arrow_right: Dan komt de mail binnen bij het @hervormdputten.nl emailadres bij Solcon.

Om te **voorkomen** dat er email gemist wordt, kunnen we een **forward** instellen van Solcon naar Microsoft 365. Als dat niet
gebeurd dan moet u in deze periode is het dus nodig om beide postvakken in de gaten te houden.
      