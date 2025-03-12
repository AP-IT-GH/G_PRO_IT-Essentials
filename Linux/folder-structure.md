## Het foldersysteem in Linux en navigeren met tekstcommando’s

Het **bestandssysteem** in Linux is hiërarchisch en begint bij de zogenaamde **root directory**, aangeduid met een `/` (forward slash). Dit betekent dat alle bestanden en mappen zich in een boomstructuur onder de root bevinden:

```bash
/
├── bin/            # Essentiële binaire bestanden (zoals ls, cat, mkdir)
├── boot/           # Opstartbestanden, kernel en bootloader (GRUB)
├── dev/            # Apparaatbestanden (schijven, USB, toetsenbord, etc.)
├── etc/            # Configuratiebestanden van het systeem
├── home/           # Gebruikersmappen (bv. /home/jannes/)
│   ├── jannes/     # Home-directory van gebruiker "jannes"
│   │   ├── Desktop/      # Bureaublad
│   │   ├── Documents/    # Documenten
│   │   ├── Downloads/    # Gedownloade bestanden
│   │   ├── Pictures/     # Afbeeldingen
│   │   ├── Videos/       # Video’s
│   │   ├── .config/      # Verborgen configuratiebestanden
│   │   └── .bashrc       # Verborgen shell-instellingen
│   ├── andere_gebruiker/
│   └── nog_een_gebruiker/
├── lib/            # Bibliotheken voor systeembinaries
├── media/          # Automatisch aangekoppelde media (bv. USB-sticks)
├── mnt/            # Handmatig aangekoppelde bestandssystemen
├── opt/            # Optionele softwarepakketten
├── proc/           # Virtuele bestanden met procesinformatie
├── root/           # Home-directory van de root-gebruiker
├── run/            # Tijdelijke systeemprocessen en sockets
├── sbin/           # Systeembinaries (voor root-gebruikers)
├── srv/            # Bestanden van servers zoals Apache of FTP
├── sys/            # Virtueel bestandssysteem met hardware-informatie
├── tmp/            # Tijdelijke bestanden (wordt geleegd bij herstart)
├── usr/            # Gebruikersprogramma's en bibliotheken
│   ├── bin/        # Niet-essentiële binaries voor gebruikers (Firefox, nano)
│   ├── lib/        # Bibliotheken voor gebruikersprogramma’s
│   ├── local/      # Software geïnstalleerd door de gebruiker
│   ├── share/      # Gedeelde bestanden (documentatie, icons, fonts)
│   └── include/    # Headerbestanden voor compileren van software
├── var/            # Variabele bestanden (logbestanden, databases, cache)
│   ├── log/        # Systeem- en applicatielogs
│   ├── mail/       # E-mailsystemen
│   ├── spool/      # Wachtrijen voor taken (bijv. printopdrachten)
│   ├── www/        # Webserverbestanden voor Apache/Nginx
│   └── cache/      # Tijdelijke cachegegevens
└── lost+found/     # Herstelbare bestanden na een crash (alleen op ext4)
```


### Navigeren met tekstcommando's

In de terminal kun je door het bestandssysteem navigeren met enkele eenvoudige commando’s.

**Huidige locatie bekijken**
```bash
pwd
```

`pwd` (print working directory) toont in welke map je je momenteel bevindt.

**Inhoud van een map weergeven**
```bash
ls
```

Dit geeft een lijst van bestanden en mappen in de huidige directory.

Handige opties:
- `ls -l` → Laat details zien zoals rechten, grootte en datum.
- `ls -a` → Toont ook verborgen bestanden (die beginnen met .).
- `ls -lh` → Toont de bestandsgrootte in een leesbaar formaat (KB, MB, GB).

Voorbeeld:
```bash
ls -lh /home/jannes/
```

**Naar een andere map gaan**
```bash
cd <mapnaam>
```

Het `cd` (change directory) commando laat je van map veranderen.

voorbeelden:
```bash
cd /home/jannes/Documenten   # Ga naar de Documenten map
cd ..                        # Ga één niveau hoger (terug)
cd /                         # Ga naar de root-directory
cd ~                         # Ga naar je home-directory (/home/jannes)
```

**Bestanden en mappen maken**
```bash
mkdir <mapnaam>  # Nieuwe map maken
touch <bestand>  # Leeg bestand maken
```

Voorbeeld:
```bash
mkdir nieuwe_map
touch nieuwe_map/voorbeeld.txt
```
Dit maakt een map `nieuwe_map` en een leeg bestand `voorbeeld.txt` daarin.

**Bestanden en mappen verwijderen**
```bash
rm <bestand>  # Verwijder een bestand
rmdir <map>   # Verwijder een lege map
rm -r <map>   # Verwijder een map inclusief inhoud
```

⚠️ Wees voorzichtig met `rm -r`, want het verwijdert alles binnen de map onomkeerbaar!

Voorbeeld:
```bash
rm -r oude_map  # Verwijdert 'oude_map' en alles erin
```

**Bestanden verplaatsen of kopiëren**
```bash
cp <bron> <doel>   # Kopieer een bestand
cp -r <bron> <doel> # Kopieer een map inclusief inhoud
mv <bron> <doel>   # Verplaats of hernoem een bestand/map
```

`<bron>` verwijst hier naar het bestand dat je wil kopieëren of verplaatsen, en `<doel>` verwijst hier naar de locatie waarin je bestand wil plakken of verplaatsen.

Voorbeelden:
```bash
cp bestand.txt /home/jannes/Backup/ # Kopieer bestand naar een andere map
mv bestand.txt nieuwe_naam.txt       # Hernoem bestand
mv bestand.txt /home/jannes/Backup/  # Verplaats bestand naar een andere map
```
Merk op dat in het tweede voorbeeld we het `mv` commando gebruiken om het bestand te hernoemen, terwijl we het in het derde voorbeeld gebruiken om het te verplaatsen naar een andere map. Wanneer we als `<doel>` een folder opgeven (eindigd op `/`) wordt het bestand louter verplaatst naar deze folder en blijft de bestandsnaam hetzelfde. Wanneer we als `<doel>` echter een nieuw bestand opgeven (bv. `/home/jannes/Backup/nieuwe_naam.txt`) verplaatsen we niet enkel het bestand, maar hernoemen we het ook.

**Terugvinden van bestanden en mappen**

Wil je **zoeken naar een bestand**?
```bash
find / -name "bestand.txt"  # Zoek naar bestand.txt in het hele systeem
```
We zoeken naar het bestand met naam `-name bestand.txt` in het hele foldersysteem (root folder `/`).

Wil je **zoeken naar een map**?
```bash
find /home/jannes -type d -name "Projecten"
```
We zoeken naar een map (`type -d`) met naam `-name Projecten` in de home directory van de gebruiker (`/home/jannes/`).

### Absolute en Relatieve paden
In Linux kunnen paden op verschillende manieren worden geschreven, afhankelijk van waar je je bevindt in het bestandssysteem. De manier waarop een pad begint, bepaalt hoe het geïnterpreteerd wordt.

#### Absolute paden
Een absoluut pad begint altijd met een `/` (forward slash). Dit betekent dat het pad wordt opgegeven vanaf de **root (`/`) van het bestandssysteem**.

Voorbeelden:
```bash
cd /home/jannes/Documents/
ls /var/log/syslog
```

- `/home/jannes/Documents/` verwijst exact naar deze locatie, ongeacht waar je je bevindt in het systeem.
- `/var/log/syslog` verwijst naar een logbestand in de systeemmap `/var/log/`.

❗**Gebruik een absoluut pad als je zeker wilt zijn dat je naar een specifieke locatie verwijst, ongeacht waar je bent.**

#### Relatieve paden
Een relatief pad is gebaseerd op de **huidige werkdirectory** (die je kunt controleren met `pwd`).

1. Een pad dat begint met `./` betekent: "**begin vanaf de huidige directory**".
    voorbeeld:
    ```bash
    cd ./Projecten/Webapp/
    ```
    Dit betekent: "**Ga naar de submap `Webapp` binnen de huidige map `Projecten`**".

2. Een pad dat begint met `../` verwijst naar de **bovenliggende map** (parent directory).

    Voorbeeld:
    ```bash
    cd ../
    ```
    Dit brengt je **één niveau hoger** in de mappenstructuur.
    ```bash
    cd ../Downloads
    ```
    Dit betekent "**Ga naar de map `Downloads`, die zich in de bovenliggendemap bevindt**".

#### Navigeren vanaf de home-directory
Het **tilde-teken (`~`)** is een speciale snelkoppeling in Linux die verwijst naar de **home-directory** van de huidige gebruiker. Dit is handig om snel naar je persoonlijke bestanden te navigeren, ongeacht waar je je in het bestandssysteem bevindt.

Elke gebruiker op een Linux-systeem heeft een eigen **home-directory** die zich standaard bevindt in `/home/<gebruikersnaam>/`.

Ik ben ingelogd onder de gebruikersnaam 'jannes', dus mijn home-directory is `/home/jannes`. Voor jou zal dit je eigen naam zijn.

Met `~` kun je hier snel naartoe:
```bash
cd ~
```
Dit brengt je altijd terug naar je home-directory, ongeacht waar je je bevindt.

Op deze manier kan je dus `~` ook gebruiken om snel bestanden of mappen binnen je home-directory te openen zonder het volledige pad te typen.

```bash
cd ~/Documents  # verwijst naar /home/jannes/Documents
ls ~/Downloads  # verwijst naar /home/jannes/Downloads
```