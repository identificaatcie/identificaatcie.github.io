---
layout: page
title: Algemene informatie
permalink: /algemene-info/
---
Hieronder is informatie over de IRMA-kaart, en in het bijzonder over de IRMA-pilot binnen Thalia, te vinden. 

# Wat is een IRMA-kaart nu eigenlijk?
De IRMA-kaart is een RFID smartcard: een soort contactloze bankpas, met daarop 'credentials'. Deze 'credentials'  kunnen dan weer één of meerdere attributen bevatten. Met die attributen kan iemand op een privacyvriendelijke manier bewijzen dat hij of zij bijvoorbeeld 18+ is, zonder daarbij meer gegevens zoals zijn of haar leeftijd door te geven. Een ander attribuut is bijvoorbeeld:  'ik ben lid van Thalia'.
Een IRMA-kaart kan meerdere attributen bevatten, geplaatst door en voor verschillende partijen ('service providers'), waardoor hij multifunctioneel en breed inzetbaar is. In theorie zou je op deze manier heel wat pasjes in je portemonnee door één IRMA-kaart kunnen vervangen.

# Het Surfnet root credential 
Als je als bachelor- of pre-masterstudent een IRMA-kaart ontvangen hebt, bevat deze ten eerste een 'Surfnet-root credential'. Deze Surfnet-root is er door onze iCIS-afdeling op geplaatst. Dit credential bevat één attribuut, namelijk je studentnummer. Hierdoor kan je met je IRMA-kaart bewijzen dat je student bent (en tijdens de controle kan je er dan zelfs voor kiezen om je studentnummer wel of niet te tonen).

Het Surfnet-root credential zelf kan je verder niet zoveel mee; het is enkel nodig om het student card credential (zie kopje hieronder) op je IRMA-kaart te laden.
Met het student card credential kan je:
* Korting op koffie in de Huygenskantine krijgen
* Korting op software krijgen, zie hier: https://demo.irmacard.org/tomcat/irma_pilot/production/vouchers/
* In de toekomst gratis printen, zie hier: https://www.irmacard.org/irma-printer-kiosk/

# Hoe kom je aan het student card credential? 
Om van bovenstaande 'extra's' gebruik te maken, moet je het student card credential op je kaart laden. Je hebt hiervoor een computer met de Javaplugin en een kaartlezer óf een android-telefoon met NFC nodig.

Vervolgens kan je via onderstaande site het student card credential op je kaart laden. Navigeer om te beginnen op je computer naar onderstaande site (zorg dat je een werkende javaplugin hebt!):
https://demo.irmacard.org/tomcat/irma_pilot/issue/studentCard/

Zodra die site vraagt om je IRMA-kaart te gebruiken, plaats je deze in je kaartlezer. Heb je geen kaartlezer? Dan kan je een Android NFC-telefoon gebruiken. Druk daartoe op 'Use Phone'.
Installeer vervolgens deze App op je telefoon:
https://github.com/credentials/irma_android_cardproxy/releases/
Hiertoe moet je in de (beveiligings)instellingen op je telefoon **Apps uit onbekende bronnen toestaan** ingeschakeld hebben. 

# Wat heeft Thalia met de IRMA-kaart te maken?
Thalia doet dit jaar mee in de IRMA-pilot en heeft in samenwerking met iCIS jou van een kaart kunnen voorzien. Om deze pilot binnen Thalia in goede banen te leiden heeft Thalia de Identificaatcie ("identificatie commissie") opgericht.

Naast het Surfnet root credential, heeft Thalia (indien je Thalia-lid bent) nog drie extra credentials op je kaart geladen, namelijk:

* Thalia leeftijd
    Met één boolean attribuut: 'over18'
* Thalia Membertype
    Met drie boolean attributen: 'Lid', 'Erelid' en 'Begunstiger'
* Thalia root/lidinfo
    Met één string-attribuut dat je gebruikersnaam voor Thalia bevat
    Met dit attribuut ben je dus te identificeren (iets dat in sommige gevallen nodig is).

Met **Thalia leeftijd** kan je op borrels bewijzen dat je, wat wettelijke leeftijdsgrens betreft, alcohol mag drinken. Met **Thalia membertype** kan je bewijzen dat je Thalialid bent, en dus aan Thalia-activiteiten deel mag nemen.

De Identificaatcie zet momenteel een Raspberry Pi in, waarmee je op borrels met je IRMA-kaart kunt bewijzen dat je Thalia-lid bent, als alternatief voor de zojuist geïntroduceerde ledenstickers.

# Kan ik mijn IRMA-kaart zelf ook uitlezen?
Momenteel is er al software beschikbaar voor verschillende platformen. We zullen hier kort het command line Linux/OSX-programma Silvia en twee Android applicaties bespreken. 

Windows-gebruikers hebben helaas pech: op de java-applet van de student card credential na is er nog niet veel software beschikbaar voor dit platform. Momenteel is een groepje enthousiaste mensen echter wel bezig met het porten van (een deel van) Silvia naar Windows, dus met een beetje geluk verbetert de ondersteuning voor Windows binnenkort.

## Android-applicaties
Voor Android zijn er naast de IRMA Card proxy app (die bij het student card credential gezien hebben) nog twee andere apps, namelijk:

* IRMA Verifier
  Met deze app kan je zelf attributen verifiëren/bewijzen. Zo kan je dus controleren of je Surfnet Root hebt en of dat je het student card credential goed op je kaart hebt gezet. Helaas kan deze app nog geen Thalia-attributen verifi&#0235;ren, maar daar wordt momenteel door ons aan gewerkt. De app is te vinden op:
  https://github.com/credentials/irma_android_verifier/releases/download/0.8-beta0/org.irmacard.pilot.android_verifier-0.8_beta0.apk

* IRMA Management
  Met deze app kan je zien wat voor credentials er allemaal op je kaart staan. Daarnaast kan je met deze app je pincode wijzigen. WIJZIG DEZE PINCODE ZO SNEL MOGELIJK! De originele management-app crasht als hij een IRMA-kaart met Thalia credentials tegenkomt. Daarom stelt de Identificaatcie een aangepaste versie beschikbaar. Deze kan je vinden op:
  http://rded.nl/imgmt.apk

## Silvia
Silvia is een zeer krachtig commandline-programma, dat alle functionaliteit van de Android apps combineert. Daarnaast kan Silvia ook nieuwe credentials en attributen aanmaken en op je kaart laden.

Het nadeel is dus wel dat Silvia alleen op Linux/OSX werkt en het enkel via de command line werkt.

Silvia is te vinden op:
https://github.com/credentials/silvia

## Broncode
De broncode van alle IRMA-software is te vinden op Github:
https://github.com/credentials

Sommige software is aangepast door Thalia, deze aanpassingen zijn te vinden op:
https://github.com/identificaatcie

# Nabije toekomst
De Identificaatcie test momenteel een Raspberry Pi en werkt aan een voor Thalia credentials werkende IRMA verifier applicatie.

Daarna gaan we kijken hoe we het gebruik van de IRMA-kaart binnen Thalia kunnen uitbreiden. We zitten bijvoorbeeld te denken aan het aanmelden voor R&BO lunchlezingen met een IRMA-kaart. Mocht je zelf nog ideeën hebben mag je ons natuurlijk altijd aanspreken of mailen!

Mocht je vragen hebben, neem dan gerust contact met ons op. Wij zijn per e-mail te bereiken op identificaatcie [at] thalia [dot] nu.

Studievereniging Thalia's Identificaatcie<br>
Thom Wiggers, *voorzitter*<br>
Sjors Clabbers<br>
Wietse Kuipers<br>
Stijn Meijer<br>
Bram in 't Zandt<br>
Koen van Ingen
