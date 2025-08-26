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
