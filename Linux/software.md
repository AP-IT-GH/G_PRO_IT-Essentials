## Software installatie en management

Iedere keer als je een spel, een app of een programma op je computer gebruikt, draait dat dankzij software-installatie. Maar software komt niet zomaar op je computer terecht; het moet eerst geïnstalleerd worden. 

### Wat is Software en Hoe Werkt Installatie?

Software bestaat uit instructies die de computer vertellen wat hij moet doen. Wanneer je software installeert, kopieert het installatiesysteem alle benodigde bestanden, afbeeldingen, geluiden en instellingen naar jouw computer zodat het programma kan draaien. Als je bijvoorbeeld een game installeert, worden alle afbeeldingen, geluiden en code op je harde schijf gezet. Hierdoor kan het spel snel en correct opstarten.

#### Het Gebruik van Packages

In plaats van losse bestanden te installeren, worden deze vaak gebundeld in wat we **packages** noemen. Een package is als een verzameldoos waarin:
- De hoofdcode van het programma zit.
- Alle extra onderdelen (zoals bibliotheken die nodig zijn voor bepaalde functies) inbegrepen zijn.
- Informatie staat over welke versies en afhankelijkheden er nodig zijn om het programma soepel te laten werken.

Door software in packages aan te bieden, worden veel handmatige stappen overbodig. Zorgvuldig samengestelde packages zorgen ervoor dat je altijd de juiste bijkomende onderdelen krijgt; dat maakt automatische updates makkelijker en voorkomt conflicten tussen verschillende versies van software. 

#### Installatie op Linux

Op Linux werken we met **package managers** zoals APT (bijvoorbeeld op Ubuntu), DNF of Pacman. Deze hulpmiddelen maken het heel eenvoudig:
- Je geeft een opdracht (zoals `sudo apt install firefox`) in de terminal.
- De package manager zoekt de juiste software op in centrale opslagplaatsen, de zogenaamde *repositories*.
- Niet alleen wordt het hoofdprogramma geïnstalleerd, maar ook alle extra onderdelen die het nodig heeft (*dependencies*).

Dit centrale systeem zorgt ervoor dat alles consistent, veilig en automatisch up-to-date blijft. Dankzij deze aanpak weten gebruikers vrijwel zeker dat alle onderdelen van een programma compatibel zijn, en dat updates probleemloos verlopen.

##### Low-Level Package Managers

Low-level package managers vormen de kern van de software-installatie in een Linux-distributie. Zij werken direct met de pakketbestanden (zoals `.deb`-bestanden op Debian-systemen of `.rpm`-bestanden op Red Hat-gebaseerde systemen) en voeren de feitelijke installatie, verwijdering of informatieopvraging uit zonder veel extra “intelligentie”. Veel low-level tools zorgen er niet automatisch voor dat alle benodigde afhankelijkheden geïnstalleerd worden; als een pakket bijvoorbeeld een andere bibliotheek nodig heeft, komt de verantwoordelijkheid vaak bij de beheerder of bij een high-level tool om dit op te lossen.

**Voorbeelden:**
- **dpkg**: Wordt gebruikt op Debian en Ubuntu om .deb-pakketten te installeren, verwijderen of informatie over te vragen.
- **rpm**: Gebruikt door distributies zoals Fedora, CentOS en openSUSE om .rpm-pakketten te beheren.

**Hoe gebruik je ze?**
Stel dat je een .deb-bestand hebt gedownload, dan installeer je het via dpkg met het commando:
```bash
sudo dpkg -i pakketnaam.deb
```
Het commando installeert het pakket, maar als er afhankelijkheden ontbreken, moet je deze apart oplossen (vaak met een high-level package manager).

Op een RPM-gebaseerd systeem installeer je een pakket met:
```bash
sudo rpm -i pakketnaam.rpm
```
Hiermee wordt het pakket geïnstalleerd zonder de verpakking van extra functionaliteit.

##### High-Level Package Managers

High-level package managers draaien bovenop de low-level tools. Ze zorgen niet alleen voor de installatie en verwijdering van pakketten, maar zorgen ook voor extra functies zoals:
- **Automatische dependency resolving**: Ze zoeken en installeren alle aanvullende software waar een pakket van afhankelijk is.
- **Repository beheer**: Ze werken met gecentraliseerde opslagplaatsen (repositories) waar pakketten worden bewaard en automatisch bijgewerkt.
- **Gemakkelijk systeemmanagement**: Met één of enkele commando's kun je je hele systeem bijwerken, nieuwe software installeren en beveiligingspatches toepassen.

**Voorbeelden:**
- **APT** (Advanced Packaging Tool): Gebruikt op Debian en Ubuntu. APT werkt samen met dpkg. Om een pakket te installeren gebruik je:
    ```bash
    sudo apt update          # Update de lijst van beschikbare pakketten
    sudo apt install pakketnaam
    ```
    Voor het verwijderen van een pakket, gebruik je:
    ```bash
    sudo apt remove pakketnaam
    ```

- **DNF/YUM**: Gebruikt op Fedora, CentOS of Red Hat. Deze tools beheren .rpm-pakketten en hun afhankelijkheden. Installatie via DNF gebeurd als volgt:
    ```bash
    sudo dnf install pakketnaam
    ```

- **Pacman**: De high-level package manager van Arch Linux, die alles centraal beheert. Installeren via Pacman gebeurt met:
    ```bash
    sudo pacman -S pakketnaam
    ```


**Hoe gebruik je ze?**
High-level tools zijn meestal gebruiksvriendelijker en verbergen de complexiteit van de low-level commando’s. Over het algemeen werk je volgens dit patroon:
- **Update de pakketdatabase**: Zorg dat de lijst van beschikbare pakketten up-to-date is met een commando als sudo apt update (of sudo pacman -Syu in Arch Linux).
- **Installeer een pakket**: Roep het installcommando op, zoals sudo apt install pakketnaam of sudo dnf install pakketnaam. De tool zoekt automatisch de benodigde afhankelijkheden en installeert alles wat nodig is.
- **Verwijder of upgrade pakketten**: Eveneens met eenvoudige commando’s kun je pakketten verwijderen of bijwerken, zoals sudo apt remove pakketnaam of sudo apt upgrade.

--- 

**Samengevat**
Low-Level Package Managers:
- Werken direct met pakketbestanden (bijv. dpkg, rpm).
- Hebben vaak beperkte ondersteuning voor afhankelijkheidsbeheer.
- Zijn handig voor het direct installeren van een enkel pakketbestand.

High-Level Package Managers:
- Bieden extra functionaliteiten zoals automatisch oplossen van afhankelijkheden en beheer van repositories (bijv. apt, dnf, pacman).
- Vergemakkelijken het updateren en onderhouden van het hele systeem.
- Zijn de voorkeurstool voor dagelijkse software-installatie en systeembeheer.

---

#### Installatie op Windows

Traditioneel werkten Windows-gebruikers met installatieprogramma’s die je downloadt als `.exe`- of `.msi`-bestanden. Deze installers lopen vaak door verschillende stappen:
- Eerst kies je een installatielocatie.
- daarna worden er handmatige keuzes gemaakt, afhankelijk van wat de maker van de software heeft bedacht.
- Als een programma extra bibliotheken nodig heeft, moet je deze soms apart installeren.

Meer recentelijk is er ook op Windows een centraler systeem ontstaan, zoals de Microsoft Store en package managers als **Chocolatey** of winget. Deze moderne systemen lijken op de aanpak die Linux gebruikt: ze halen de software op uit centrale repositories en zorgen voor automatische updates en installatie van alle benodigde onderdelen.

Met Chocolatey kan je software beheren via een paar eenvoudige commando’s. Voor de **installatie** van software gebruik je het commando:
```bash
choco install [pakketnaam]
```

Voorbeeld:
Om Google Chrome te installeren, typ: 
```bash
choco install googlechrome
```
Chocolatey zoekt naar het pakket in de repository, downloadt het en installeert het automatisch, samen met alle benodigde afhankelijkheden.

Om software te **updaten** gebruik je:
```bash
choco upgrade [pakketnaam]  # één enkel pakket bijwerken
choco upgrade all           # alles bijwerken
```

Om software te **verwijderen**, gebruik je:
```bash
choco uninstall [pakketnaam]
```

Als je niet zeker weet hoe een pakket heet of wat er beschikbaar is, kun je **zoeken** met:
```bash
choco search [zoekterm]
```
Bijvoorbeeld:
```bash
choco search vlc
```
Dit geeft je een lijst met pakketten die met VLC te maken hebben.

Wil je weten welke software via Chocolatey aanwezig is, gebruik dan
```bash
:choco list --local-only
```

---

**Samengevat**:
- Software-installatie zorgt ervoor dat programma’s met al hun bestanden en instellingen correct op je computer worden gezet.
- Packages bundelen alle onderdelen die een programma nodig heeft, waardoor updates en beheer gemakkelijker en veiliger verlopen.
- Op Linux gebeurt dit via package managers die alles automatisch regelen, terwijl op Windows traditioneel meer handmatige stappen nodig waren, maar de modernere methoden nu meer lijken op de Linux-benadering.




### Wat Zijn Softwareversies?

Wanneer ontwikkelaars een programma maken, komen er door de tijd heen vaak veranderingen en verbeteringen aan te pas. Softwareversies geven aan welke “editie” van een programma je hebt, zodat gebruikers en ontwikkelaars makkelijk kunnen zien wat er veranderd is sinds de vorige versie. Versies helpen bij het beheren van updates, het oplossen van fouten en het vaststellen van compatibiliteit met andere software.

#### Semantic Versioning (SemVer)
Semantic versioning is een veelgebruikte methode om versies op te bouwen. Hierbij bestaat de versie uit drie delen, geschreven als `Major.Minor.Patch`. Bijvoorbeeld, in versie 2.5.3 betekent dit:
- Major (2): Dit nummer wordt verhoogd als er ingrijpende veranderingen plaatsvinden die niet terugwerkend compatibel zijn. Met andere woorden, oude functies kunnen verdwijnen of veranderen, waardoor programma’s die afhankelijk zijn van die functies mogelijk moeten worden aangepast.
- Minor (5): Dit nummer geeft aan dat er nieuwe functies of verbeteringen zijn toegevoegd, maar dat alle bestaande functies nog steeds werken zoals voorheen.
- Patch (3): Dit getal wordt bijgewerkt wanneer er kleine foutjes zijn opgelost of wanneer er kleine verbeteringen worden doorgevoerd zonder dat er nieuwe functies aan het programma worden toegevoegd.

Met semantic versioning zie je dus in één oogopslag hoe ingrijpend de veranderingen zijn en of je misschien bereid moet zijn om je software of projecten na de update aan te passen.

#### Calendar Versioning
Calendar versioning gaat een andere weg in het nummeren van versies. In plaats van te focussen op wat technisch is veranderd, werden bij calendar versioning de versies gebaseerd op de datum van uitgave. Hierbij zie je vaak versies als 2021.04 of 22.05 (waarbij het eerste deel het jaar aangeeft en het tweede bijvoorbeeld de maand).
- Voordeel: Je weet direct wanneer de software is uitgebracht en kun daardoor de updatecyclus of het verouderingsniveau van de software beter inschatten.
- Toepassing: Dit wordt vaak toegepast bij producten die volgens een vast schema uitkomen, zoals bepaalde besturingssystemen of bedrijfssoftware.

#### LTS (Long-Term Support)
**LTS** staat voor **Long-Term Support**, wat betekent dat een bepaalde release gedurende een langere periode ondersteuning en updates krijgt.

Waarom is dit belangrijk?
- Voor gebruikers en bedrijven die stabiliteit nodig hebben, is het fijn om te weten dat een versie voor bijvoorbeeld vijf jaar blijft worden onderhouden met beveiligingsupdates en bugfixes.
- Het voorkomt dat je constant moet upgraden naar de nieuwste versie, wat soms incompatibiliteitsproblemen kan veroorzaken.

Bij Ubuntu krijg je bijvoorbeeld vaak een LTS-versie die vijf jaar ondersteuning krijgt, waardoor het ideaal is voor servers of werkplekken waar betrouwbaarheid essentieel is.
