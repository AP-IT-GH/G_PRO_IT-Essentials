## Archiveren en Compressie

### Wat is een archief?

Een archief is eigenlijk een enkel bestand dat meerdere bestanden en mappen bevat. Het is net als een gereedschapskist waarin je diverse tools bewaart. Het idee hierachter is om alles wat samen hoort in één pakket samen te brengen, zodat het eenvoudiger is om het te bewaren of te versturen. Een archief verandert op zich niets aan de grootte van de individuele bestanden (tenzij er compressie wordt toegepast); het bundelt ze gewoon bij elkaar.

### Wat is compressie?

Compressie is het proces waarbij de grootte van bestanden of een archief wordt verkleind. Dit gebeurt door gebruik te maken van slimme algoritmes die redundante data verwijderen of efficiënter coderen. Denk bijvoorbeeld aan het vacuüm verpakken van je kleren wanneer je op reis gaat zodat er meer in je valies past. 

Het doel is om minder opslagruimte te gebruiken of om bestanden sneller te verzenden via internet. Er zijn twee belangrijke dingen om in gedachten te houden:
- Niet elk archief is per definitie gecomprimeerd.
- Comprimeren kan wel zorgen voor wat kwaliteitsverlies in bepaalde media (bijvoorbeeld bij audio of video), maar bij tekst en programma’s gebeurt dit meestal zonder verlies van informatie.

### Hoe werkt dit in Windows?

Windows heeft ingebouwde ondersteuning voor ZIP-bestanden. Je kunt bijvoorbeeld een map selecteren, met de rechtermuisknop klikken en kiezen voor "Verzenden naar > Gecomprimeerde (gezipte) map". Dit pakt de bestanden samen in één ZIP-bestand en past tegelijkertijd compressie toe, zodat de totale grootte kleiner wordt. Het archiveren en comprimeren van je bestanden gebeurd dus in één stap.

Naast de standaardmethode gebruiken veel mensen ook andere programma’s zoals 7-Zip of WinRAR. Deze programma’s ondersteunen bovendien andere archiefformaten (zoals RAR of 7z) en bieden vaak meer opties voor het aanpassen van de mate van compressie en andere instellingen.

### Hoe werkt dit in Linux?

In Linux is het archiveren en comprimeren van bestanden een afzonderlijk process. Het is gebruikelijk om eerst met het `tar` commando een archief te maken van meerdere bestanden of mappen. Het resultaat is typisch een `.tar`-bestand. Op dit `tar`-bestand wordt vervolgens compressie toegepast met tools zoals `gzip` of `bzip2`. Dit levert bestandsnamen op zoals `.tar.gz` of `.tar.bz2`. Een typisch commando ziet er als volgt uit:

```bash
tar -czvf archief.tar.gz mapnaam
```

Hierbij staat:
- `c` voor create (aanmaken van een archief),
- `z` voor gzip compressie,  
- `v` voor verbose (zodat je ziet wat er gebeurt),
- `f` voor file (waarna je de naam van het archief invult).

Een groot voordeel van archiveren met tar in Linux is dat het de bestandsrechten en metadata (zoals datum en eigenaar) behoudt.

#### Comprimeren zonder te archiveren

Compressie hoeft niet altijd te betekenen dat je tegelijkertijd bestanden samenvoegt tot één archief. In Linux kun je een enkel bestand direct comprimeren met behulp van commando's zoals `gzip`, `bzip2` of `xz`. Deze tools passen een algoritme toe om de bestandsgrootte te verkleinen zonder eerst de bestanden te bundelen.

**voorbeeld**
Stel je hebt een tekstbestand genaamd `bestand.txt`. Als je dit bestand wilt comprimeren, typ je in de terminal:
```bash
gzip bestand.txt
```

Dit commando vervangt `bestand.txt` door een gecomprimeerd bestand met de naam `bestand.txt.gz`. Hiermee wordt de oorspronkelijke inhoud efficiënter opgeslagen. Om het bestand weer terug te zetten naar de originele vorm, gebruik je:
```bash
gunzip bestand.txt.gz
```

Bij deze werkwijze wordt het bestand op zichzelf gecomprimeerd, zonder dat je het combineert met andere bestanden in één enkel archiefbestand. Wanneer je echter meerdere bestanden in één keer wil comprimeren, bundel je deze best eerst tot een archief alvorens je compressie toepast.

#### Compressie algoritmes

##### gzip
gzip is zeer snel bij zowel het comprimeren als het de-comprimeren van bestanden. Dit maakt het ideaal voor scenario's waarin snelheid belangrijk is, zoals bij webservers die vaak data moeten comprimeren en versturen. Hoewel gzip snel is, is de verkregen compressieverhouding gemiddeld. Dit betekent dat de bestandsgrootte wel vermindert, maar vaak minder dan wat met bzip2 of xz mogelijk is.

**voorbeeld**
```bash
gzip bestand.txt
```

zal `bestand.txt` comprimeren naar `bestand.txt.gz`.

##### bzip2
bzip2 is over het algemeen langzamer dan gzip, zowel bij het comprimeren als bij het de-comprimeren van bestanden. Dit merk je vooral bij grotere bestanden of uitgebreide mappen. Het voordeel van bzip2 ligt in een betere compressieverhouding. De bestanden worden doorgaans kleiner gecomprimeerd dan bij gzip, wat handig is als opslagruimte een belangrijke factor is.

**voorbeeld**
```bash
bzip2 bestand.txt
```

zal `bestand.txt` comprimeren naar `bestand.txt.bz2`.


##### xz
xz is vaak de traagste optie tijdens het comprimeren, terwijl de de-compressiesnelheid relatief beter is, maar niet zo snel als gzip. Dit betekent dat xz vooral opvalt als je bereid bent meer tijd te investeren voor een optimaal resultaat. xz biedt doorgaans de beste compressieverhouding van de drie. Dit leidt tot aanzienlijk kleinere bestanden, wat ideaal is als je echt elke byte wilt besparen. Het kan echter meer geheugen en verwerkingstijd vereisen.

**voorbeeld**
```bash
xz bestand.txt
```

zal `bestand.txt` comprimeren naar `bestand.txt.xz`. 