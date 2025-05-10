# Computer Hardware

Computers bestaan uit verschillende onderdelen die samenwerken om taken uit te voeren. Elk onderdeel heeft een specifieke functie en draagt bij aan de algehele werking van het systeem.

## Welke onderdelen vind je in een computer

### Moederbord

Het moederbord is het centrale schakelpunt van de computer. Alle andere hardwarecomponenten worden hierop aangesloten. Het bevat belangrijke onderdelen zoals de chipset, aansluitingen voor de processor, geheugenmodules, uitbreidingskaarten en opslag.

#### Printed Circuit Board (PCB) met uitbreidingsmogelijkheden
Het moederbord is een **geprinte schakeling** (PCB) die alle componenten van een computer met elkaar verbindt. Moderne moederborden bevatten **uitbreidingsslots** zoals PCIe (Peripheral Component Interconnect Express), waarmee extra hardware kan worden toegevoegd, zoals grafische kaarten, geluidskaarten en netwerkkaarten.

Daarnaast heeft het moederbord **aansluitingen voor opslag** (SATA, NVMe), externe apparaten (USB, Thunderbolt) en RAM-slots voor geheugenuitbreiding. Sommige moederborden hebben ingebouwde Wi-Fi en Bluetooth modules, terwijl andere een aparte kaart vereisen.

#### Bevat ROM met Firmware
Het moederbord bevat **ROM-geheugen** (Read-Only Memory) waarin de firmware is opgeslagen. Dit is een klein stukje software dat de hardware initialiseert en zorgt voor de communicatie met het besturingssysteem.
- **Initialisatie van hardware**: Bij het opstarten controleert de firmware of alle componenten goed functioneren, zoals de processor, RAM en opslag.
- **Opstarten van het besturingssysteem**: De firmware zoekt naar een besturingssysteem op de harde schijf of SSD en start dit op.
- **BIOS of UEFI**:
    - **BIOS** (Basic Input/Output System) is een oudere firmware-versie die de computer initialiseert.
    - **UEFI** (Unified Extensible Firmware Interface) is de moderne vervanger van BIOS, met een grafische interface en ondersteuning voor grotere schijven en snellere opstartprocessen.

#### Verschillende formfactors
De grootte en indeling van een moederbord worden bepaald door de **formfactor**. Dit bepaalt welke behuizing en componenten compatibel zijn. Veelvoorkomende formfactors zijn:
- **ATX**: Standaardformaat voor desktops, met veel uitbreidingsmogelijkheden.
- **Micro ATX**: Compacte versie van ATX met iets minder uitbreidingsslots.
- **Mini ITX**: Klein formaat, geschikt voor compacte systemen en stille computers.
- **Nano ITX**: Nog kleiner, vaak gebruikt in embedded systemen.
- **Pico ITX**: Ultracompact, bedoeld voor gespecialiseerde toepassingen zoals industriële apparatuur.


### Processor

De processor, ook wel gekend als de 'central processing unit (CPU)', is het brein van de computer en voert berekeningen uit. Hoe sneller en efficiënter de CPU werkt, hoe beter de computer kan reageren op opdrachten. Moderne CPU’s hebben meerdere kernen (cores) die tegelijk taken kunnen uitvoeren.

#### 1 of meerdere Cores
Moderne CPU’s hebben **meerdere cores** (rekenkernen), wat betekent dat ze verschillende taken tegelijkertijd kunnen uitvoeren. Dit verhoogt de snelheid en prestaties, vooral bij multitasking en zware programma’s zoals videobewerking en gaming.
    - **Hyperthreading**: Sommige processors ondersteunen hyperthreading, een technologie waarmee één fysieke core zich kan gedragen als twee virtuele cores. Dit verhoogt de efficiëntie bij het verwerken van meerdere taken tegelijk.

#### Cache
De **cache** is een supersnel geheugen dat zich heel dicht bij de CPU bevindt. Het zorgt ervoor dat de processor minder hoeft te wachten op gegevens en instructies.
- **Instructiecache**: Opslagplaats voor veelgebruikte instructies, zodat de CPU sneller kan reageren.
- **Datacache**: Hierarchisch ingedeeld in verschillende niveaus:
- **L1-cache**: Klein, maar extreem snel; direct gekoppeld aan de cores.
- **L2-cache**: Groter dan L1, iets trager maar nog steeds dichtbij de CPU.
- **L3-cache**: De grootste en langzaamste van de drie, maar nog steeds veel sneller dan RAM.

Omdat cache-geheugen duur is om te produceren, heeft een processor slechts een beperkte hoeveelheid cache (vaak enkele megabytes).

#### Taak van de CPU
De CPU volgt een stappenproces om instructies uit te voeren:
- **Fetch** – Ophalen van de instructie uit het geheugen.
- **Decode** – Vertalen van de instructie naar een vorm die de processor begrijpt (elektrische signalen).
- **Execute** – Uitvoeren van de instructie en opslaan van het resultaat in het register.

Om dit proces efficiënt te laten verlopen, maakt de CPU gebruik van **registers** – kleine, supersnelle opslagplaatsen waarin belangrijke data tijdelijk wordt bewaard.

#### Arithmetic Logic Unit (ALU)
De ALU is het rekenhart van de processor en voert wiskundige en logische operaties uit op gegevens. Het krijgt instructies van de **Control Unit**, haalt benodigde data op uit registers of geheugen en slaat de resultaten op.

##### Integer Operaties
De ALU kan verschillende basisbewerkingen uitvoeren op gehele getallen:
- **Optellen (+)**
- **Aftrekken (-)**
- **Vermenigvuldigen (*)**
- **Delen (/)**
- **Modulo (%)** – Geeft de rest van een deling terug

##### Bitwise Logische Operaties
De ALU kan ook operaties uitvoeren op **binaire data** op het bitniveau:
- **NOT** – Inverteert bits (1 wordt 0, 0 wordt 1)
- **AND** – Bepaalt welke bits in beide operanden 1 zijn
- **OR** – Geeft 1 als minstens één van de operanden een 1 bevat
- **XOR** – Geeft 1 als de bits verschillend zijn
- **Shift** – Verschuift bits naar links of rechts, waardoor ze effectief worden vermenigvuldigd of gedeeld

##### Operands
De gegevens waarmee de ALU rekent kunnen afkomstig zijn uit verschillende bronnen:
- **Registers** – Direct binnen de CPU voor supersnelle toegang
- **Extern geheugen** – RAM of cache, iets langzamer dan registers
- **Door de ALU zelf gegenereerd** – Bijvoorbeeld bij het uitvoeren van een operatie waarbij een constante wordt gebruikt

##### Resultaat
Na elke bewerking produceert de ALU twee soorten resultaten:
- **Data** – Het berekende eindresultaat
- **Status** – Informatie zoals overflow, nulwaarde of negatieve waarde, die kan worden gebruikt voor verdere besluitvorming binnen de CPU

Alle resultaten worden **opgeslagen in registers**, zodat ze snel kunnen worden hergebruikt in volgende instructies.

#### Kloksnelheid van de processor
De **kloksnelheid** bepaalt hoe snel een processor instructies kan verwerken. Het wordt gemeten in **Hertz (Hz)** en meestal uitgedrukt in **gigahertz (GHz)**. Bijvoorbeeld, een CPU met een kloksnelheid van **3,5 GHz** kan **3,5 miljard cycli per seconde** uitvoeren.

##### Wat is een klokcyclus?
Een **klokcyclus** is een enkele bewerkingstijdseenheid binnen de CPU. Elke instructie die de processor uitvoert, bestaat uit meerdere stappen (fetch, decode, execute), en deze worden gecoördineerd door de **klokgenerator** van de CPU. Hoe sneller de klok, hoe sneller de processor kan werken.

##### Invloed op prestaties
- **Hogere kloksnelheid** → Snellere verwerking van instructies, wat leidt tot betere prestaties.
- **Lagere kloksnelheid** → Minder energieverbruik en minder warmteproductie, maar trager in complexe taken.

##### Turbo Boost en Overklokken
- **Turbo Boost**: Moderne CPU’s kunnen tijdelijk hun kloksnelheid **automatisch verhogen** als er meer rekenkracht nodig is.
- **Overklokken**: Geavanceerde gebruikers kunnen handmatig de kloksnelheid verhogen, maar dit vereist extra koeling en kan de levensduur van de processor verkorten.

##### Kloksnelheid versus aantal cores
Hoewel een **hogere kloksnelheid** betekent dat een enkele core sneller werkt, spelen ook **meerdere cores** een grote rol in prestaties. Sommige taken profiteren meer van **multicore-processors** dan van een enkele, supersnelle core.

#### Processor Socket
De **socket** is de fysieke aansluiting op het moederbord waarin de processor wordt geplaatst. Verschillende CPU’s hebben verschillende sockets, wat bepaalt welke moederborden compatibel zijn. Enkele veelvoorkomende sockets:
- **Intel**:
    - **LGA 1700** (moderne 12e/13e generatie Intel Core-processoren)
    - **LGA 1200** (10e/11e generatie)
    - **LGA 1151** (8e/9e generatie)
- **AMD**:
    - **AM5** (Ryzen 7000-serie, DDR5-geheugenondersteuning)
    - **AM4** (Ryzen 1000-5000-serie, zeer populair)
    - **TR4/SP3** (Threadripper en EPYC voor high-performance systemen)

Sockets bepalen welke koelers en moederborden compatibel zijn met een processor. **LGA (Land Grid Array)** heeft contactpunten op de CPU zelf, terwijl **PGA (Pin Grid Array)** pinnen op de processor heeft die in het moederbord worden geplaatst.

#### 32-bit vs. 64-bit
- **32-bit processors** kunnen maximaal **4 GB** RAM aanspreken en verwerken gegevens in 32-bit blokken. Dit was vroeger de standaard voor computers.
- **64-bit processors** kunnen veel meer geheugen gebruiken (tot theoretisch exabytes) en verwerken gegevens in **64-bit blokken**, wat efficiënter en krachtiger is voor moderne toepassingen.
- Moderne computers en besturingssystemen draaien vrijwel altijd op een **64-bit architectuur**, wat zorgt voor betere prestaties en ondersteuning van complexere software.

#### AMD vs. ARM
- **AMD** (en Intel) maken **x86/x64-processoren**, die krachtig zijn en geschikt voor desktops, laptops en servers. Deze chips zijn ontworpen voor hoge prestaties en ondersteunen complexere instructiesets (**CISC**).
- **ARM** maakt **energiezuinige processoren**, die veel gebruikt worden in smartphones, tablets en sommige laptops. Ze gebruiken een **RISC-architectuur** met een efficiëntere manier van instructieverwerking, waardoor ze minder stroom verbruiken.
- Tegenwoordig zien we **ARM-chips** ook opduiken in krachtige apparaten zoals Apple’s M-serie chips in MacBooks, die hoge prestaties combineren met lage energieconsumptie.



### Werkgeheugen

RAM (Random Access Memory) slaat data op die de processor nodig heeft om programma's snel uit te voeren. Omdat de CPU zelf niet genoeg werkgeheugen heeft, gebruikt hij RAM als een tussenopslag voor actieve processen en gegevens. Hoe meer RAM een computer heeft, hoe sneller en soepeler programma’s draaien, vooral bij multitasking.

#### Eigenschappen van RAM
- **Volatiel geheugen**: Zodra de computer wordt uitgeschakeld, verdwijnt alle data in het RAM-geheugen. Dit in tegenstelling tot opslag zoals SSD’s en harde schijven, die permanent gegevens bewaren.
- **Maximale snelheid**: Moderne DDR4-geheugenmodules kunnen snelheden tot **25 GB/s** halen, afhankelijk van de configuratie en het type RAM.
- **Geheugennaam en snelheid**: Bijvoorbeeld **DDR4-3200**, waarbij **3200 MT/s** (Mega Transfers per seconde) aangeeft hoeveel operaties het geheugen per seconde kan uitvoeren.

#### Geheugentimings en vertraging
RAM heeft niet alleen een kloksnelheid, maar ook **timings**, die de vertraging aangeven bij het ophalen van data. Een voorbeeld van timings: **16-18-18-38**, waarbij de waarden worden gemeten in **clock cycles** (klokcycli).
- **CAS Latency (CL)**: De tijd tussen het versturen van een geheugenadres en het ontvangen van de bijbehorende data. Lagere CAS-latency betekent snellere toegang tot data.
- **tRCD, tRP, tRAS**: RAM is georganiseerd als een grid met rijen en kolommen. Deze timings bepalen de vertraging bij het verplaatsen van data binnen dat grid.
- **tRCD (Row-to-Column Delay)**: Tijd die nodig is om van een rij naar een kolom te schakelen.
- **tRP (Row Precharge Time)**: Tijd die nodig is om een rij te sluiten voordat een nieuwe rij kan worden geopend.
- **tRAS (Row Active Time)**: Totale tijd dat een rij actief blijft voordat hij wordt afgesloten.

Al deze factoren bepalen de snelheid en efficiëntie van het RAM-geheugen in een computer.


### Opslag

Opslag komt in de vorm van HDD’s (Hard Disk Drives) en SSD’s (Solid State Drives). SSD’s zijn veel sneller en betrouwbaarder dan traditionele harde schijven. Dit opslaggeheugen bevat alle bestanden, programma’s en het besturingssysteem.

#### Opslag – Hard Disk Drive (HDD)
Een **HDD** (Hard Disk Drive) gebruikt **ronddraaiende platters** en een **lees-/schrijfarm** om gegevens fysiek te lezen en te schrijven. De snelheid en prestaties worden bepaald door verschillende factoren:
- **Ronddraaiende platters**: De harde schijf bestaat uit meerdere magnetische schijven (platters) die draaien met een snelheid van bijvoorbeeld **5.400 rpm** (rotaties per minuut) of **10.000 rpm**.
- **Lees-/schrijfarm**: Beweegt over de platters en gebruikt een magnetische kop om data te lezen en schrijven.
- **Error detectie en correctie**: HDD’s gebruiken technieken zoals ECC (Error Correction Code) om fouten in opgeslagen data te detecteren en corrigeren.
- **Toerental en latency**: Hoe sneller de platters draaien, hoe lager de latency (vertraging).
    - 5.400 rpm → Latency van 5,55 ms
    - 10.000 rpm → Latency van 3 ms
- **Storage density**: Hoe dichter de data op de platter staat, hoe meer opslagcapaciteit mogelijk is.
- **Locatie op platter**: Gegevens die dichter bij de rand van de platter worden opgeslagen, kunnen sneller gelezen worden.
- **Cache**: HDD’s hebben een **cachegeheugen** (meestal 8MB tot 256MB) om veelgebruikte gegevens tijdelijk op te slaan en de prestaties te verbeteren.

#### Opslag – Solid State Drive (SSD)
Een **SSD** gebruikt **NAND-geheugen** en heeft geen bewegende onderdelen, wat zorgt voor **veel hogere snelheden** en **betrouwbaarheid**.
- **NAND-geheugen**: Flash-geheugen waarin data wordt opgeslagen in geheugenblokken.
- **Beperkt aantal schrijfbewerkingen**: NAND-geheugen heeft een beperkte levensduur.
    - Voorbeeld: Een 1 TB SSD kan ongeveer 600 TB aan schrijfbewerkingen aan voordat slijtage optreedt.
- **Wear leveling & bad block mapping**:
    - Wear leveling verspreidt schrijfbewerkingen gelijkmatig over alle geheugenblokken om slijtage te minimaliseren.
    - Bad block mapping detecteert defecte geheugenblokken en voorkomt dat ze worden gebruikt.
- **Read en write cache**: SSD’s gebruiken DRAM-cache of SLC-cache om tijdelijk veelgebruikte data op te slaan en de snelheid te verhogen.
- **Error detectie en correctie**: Net als HDD’s gebruiken SSD’s foutcorrectie-algoritmes om dataverlies te minimaliseren.
- **Garbage collection**: SSD’s voeren garbage collection uit, waarbij oude, niet-gebruikte data wordt gewist om ruimte vrij te maken en de levensduur te verlengen.


### Grafische kaart

De grafische kaart verwerkt visuele informatie en is essentieel voor gaming, videobewerking en andere grafisch-intensieve taken. Sommige computers hebben geïntegreerde GPU’s (in de CPU), terwijl anderen een aparte grafische kaart hebben voor betere prestaties.

#### Kan aparte kaart zijn of onboard
- **Dedicated grafische kaart**: Dit is een **losse videokaart** die in het moederbord wordt geplaatst via een PCIe-slot. Dit type kaart heeft eigen **VRAM (Video RAM)** en biedt veel kracht voor gaming, 3D-rendering en wetenschappelijke simulaties.
- **Onboard (geïntegreerde GPU)**: Sommige processoren hebben een ingebouwde GPU die direct gebruik maakt van het systeemgeheugen. Dit is energiezuiniger en goedkoper, maar minder krachtig dan een aparte kaart.

#### Geoptimaliseerd voor grafische doeleinden
De GPU is specifiek ontworpen om complexe **beeldverwerking** te versnellen. In tegenstelling tot de CPU, die algemene berekeningen uitvoert, is de GPU geoptimaliseerd om **parallelle berekeningen** uit te voeren, wat cruciaal is voor het verwerken van grote hoeveelheden grafische data.

#### Raytracing
Raytracing is een **geavanceerde techniek** die lichtstralen simuleert en realistische schaduwen, reflecties en belichting creëert. Moderne grafische kaarten, zoals NVIDIA’s RTX-serie en AMD’s RDNA2-chips, ondersteunen **hardwarematige raytracing**, wat zorgt voor een veel realistischer beeld in games en animaties.

#### Floating Point Operaties
GPU’s zijn gespecialiseerd in **floating-point berekeningen** (decimale berekeningen), wat cruciaal is voor grafische weergave, simulaties en wetenschappelijke toepassingen. Dit maakt ze efficiënter dan CPU’s in taken die enorme hoeveelheden numerieke berekeningen vereisen.

#### Ook bruikbaar om AI’s te trainen
Door de grote parallelle rekenkracht worden GPU’s vaak ingezet voor **AI-training** en **machine learning**. Ze kunnen enorme datasets verwerken en neurale netwerken veel sneller trainen dan traditionele CPU’s.
Populaire AI-training frameworks zoals **TensorFlow** en **PyTorch** ondersteunen GPU-versnelling om berekeningen te optimaliseren.


### Voeding – Power Supply Unit (PSU)
De voeding is verantwoordelijk voor het leveren van **elektrische energie** aan alle componenten van de computer. Zonder een goede voeding kan een computer instabiel werken of zelfs niet opstarten.

#### Voldoende vermogen nodig
De PSU moet **voldoende wattage** hebben om alle onderdelen van stroom te voorzien.
- Een **basis-pc** kan genoeg hebben aan **400-600W**
- Een **gaming-pc** met krachtige GPU’s heeft vaak **650-850W**
- Voor **workstations en servers** kunnen voedingen **1000W+** nodig hebben

#### Juiste aansluitingen nodig
Een voeding moet de juiste **kabels en connectors** hebben voor het moederbord, de grafische kaart en andere componenten. Veelgebruikte aansluitingen:
- **24-pin ATX** – Hoofdconnector voor het moederbord
- **8/4-pin CPU** – Voeding voor de processor
- **PCIe 6/8-pin** – Voeding voor grafische kaarten
- **SATA & Molex** – Voor opslag en randapparatuur

#### Modulair vs. niet-modulair
- **Niet-modulair**: Alle kabels zitten vast aan de voeding, minder flexibel maar goedkoper.
- **Semi-modulair**: Basisconnectors zijn vast, maar extra kabels kunnen worden toegevoegd.
- **Modulair**: Alle kabels zijn los te koppelen, wat zorgt voor een nettere kabelbeheer en betere luchtstroom in de behuizing.

#### Efficiëntie rating – 80 PLUS certificering
De **80 PLUS** certificering geeft aan hoe efficiënt een voeding stroom omzet zonder energieverlies als warmte:
- **80 PLUS Titanium – 96% efficiëntie**, extreem energiezuinig
- **80 PLUS Platinum – 92% efficiëntie**, geschikt voor high-end systemen
- **80 PLUS Gold – 90% efficiëntie**, een goede balans tussen prestaties en kosten
- **80 PLUS Silver/Bronze** – Lagere efficiëntie, geschikt voor budget-pc’s

Een hoge efficiëntie betekent minder energieverlies en minder warmteontwikkeling, wat de levensduur van de voeding en andere componenten ten goede komt.

## Input- en output devices

Input-apparaten zorgen ervoor dat de gebruiker gegevens kan invoeren in de computer. Voorbeelden zijn toetsenborden, muizen, touchscreens en microfoons.

Output-apparaten geven informatie weer of produceren geluid. Denk aan monitors, printers en speakers.
