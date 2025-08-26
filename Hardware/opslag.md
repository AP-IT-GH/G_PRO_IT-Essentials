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
