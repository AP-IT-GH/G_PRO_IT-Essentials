## Werken met bestanden in Linux

In Linux kunnen we bestanden openen, lezen, filteren, bewerken en analyseren met verschillende commando's. 

### Bestanden Lezen en Filteren

##### Concatenate (`cat`) 

Toont de inhoud van een bestand
```bash
cat bestand.txt
```

Handig om een volledig bestand in één keer te tonen. Voor lange bestanden gebruik je `less` of `more`.
```bash
less bestand.txt
```

##### Eerste regels tonen (`head`)

Toont standaard de eerste 10 regels van een bestand.
```bash
head bestand.txt
```

Je kan ook zelf het aantal regels kiezen met de `-n` optie.
```bash
head -n 5 bestand.txt   # Toont de eerste 5 regels
```

##### Laatste regels tonen (`tail`)

Toont standaard de laatste 10 regels.
```bash
tail bestand.txt
```

Ook hier kan je een specifiek aantal regels tonen:
```bash
tail -n 4 bestand.txt   # Toont de laatste 4 regels
```

Voor real-time updates (bijvoorbeeld voor logbestanden) gebruik je de `-f` optie:
```bash
tail -f /var/log/syslog # Volgt updates van het syslog bestand
```

##### Zoeken in bestanden (`grep`)

Zoekt naar specifieke tekst in een bestand.
```bash
grep "zoekterm" bestand.txt
```

Wanneer je naar een woord wil zoeken zonder rekening te houden met hoofdletters zoek je case-insentive, en gebruik je de optie `-i`:
```bash
grep -i "linux" bestand.txt
```

Wil je meer context kan je er voor kiezen om ook een aantal regels voor en na de match te tonen met de `-C` optie:
```bash
grep -C 3 "error" logbestand.txt
```

Indien je in één keer alle bestanden wil doorzoeken in een map geef je een map op (eindigd op `/`) in plaats van een bestand, en gebruik je de `-r` optie:
```bash
grep -r "foutmelding" /var/log/
```

##### Kolommen uit tekst halen

Stel je werkt met een tabel die opgeslagen is in een CSV bestand, dan kan je enkel de kolommen uit de tabel gaan halen waarin je geïnteresseerd bent.

💡 Een **CSV (comma seperated values)** bestand is een bestand waarin data wordt opgeslagen in een tabel. Elke lijn in de CSV file vertegenwoordigd een rij in de tabel, en de kolommen worden gescheiden door een 'delimiter', in dit geval een komma.

**tabel.csv**
```Bash
index,voornaam,achternaam
0,Glenn,Van Loon
1,Nick,Van Acker
2,Jannes,Peeters
```

**kolommen `-f`**
```bash
cut -d ',' -f 2 tabel.csv
# voornaam
# Glenn
# Nick
# Jannes
```

- `-d ','`stelt de delimiter in op komma (,)
- `-f 2` selecteerd de tweede kolom.



Wanneer je werkt met bestanden die een vaste breedte hebben kan je er ook voor kiezen geen rekening te houden met de delimiter en de `-c` optie gebruiken. Hiermee selecteer je bepaalde tekens op een vaste positie in elke regel.
```bash
cut -c 3-7 tabel.csv
# dex,v
# Glenn
# Nick,
# Janne
```

##### Sorteren (`sort`)

We kunnen regels gaan sorteren in onze bestanden, standaard gebeurd dit alfabetisch.

**gemeenten.txt**
```bash
Brussel
Gent
Antwerpen
Hasselt
Leuven
```

Met het `sort` commando kunnen we de file gaan sorteren:
```bash
sort gemeenten.txt

# Antwerpen
# Brussel
# Gent
# Hasselt
# Leuven
```

Om te sorteren in omgekeerde volgorde gebruiken we `-r`:
```bash
sort -r gemeenten.txt

# Leuven
# Hasselt
# Gent
# Brussel
# Antwerpen
```

We kunnen ook complexere sorteringen gaan uitvoeren door opties te gaan combineren. Stel dat we een lijst van pokemons hebben waarvan we een sortering willen maken op basis van HP.

**pokemon.txt**
```bash
Pikachu;Electric;35
Charizard;Fire/Flying;78
Bulbasaur;Grass/Poison;45
Squirtle;Water;44
Gengar;Ghost/Poison;60
Snorlax;Normal;160
Jigglypuff;Normal/Fairy;115
Eevee;Normal;55
Lucario;Fighting/Steel;70
Gyarados;Water/Flying;95
```

```bash
sort -t';' -k3 -n -r pokemon.txt
```

- `-t';'` zorgt ervoor dat ';' gebruikt wordt als scheidingsteken om kolommen te vormen.
- `-k3` neemt de derde kolom om op te sorteren.
- `n` zorgt er voor dat we op getallen (numeric) gaan sorteren in plaats van alfabetisch.
- `-r` zorgt ervoor dat we sorteren van hoog naar laag.


##### Dubbele lijnen verwijderen

Met behulp van het `uniq` commando kunnen we dubbele lijnen gaan verwijderen.
```bash
uniq bestand.txt
```

Met behulp van de `-c` (count) optie kunnen we ook het aantal dubbele lijnen gaan tellen:
```bash
uniq -c bestand.txt
```

##### Aantal woorden, regels en tekens tellen

Het `wc` commando toont ons het aantal woorden, regels en tekens in een bestand.
```bash
wc pokemon.txt
# 10 10 226 pokemon.txt
```

In het `pokemon.txt` bestand zitten 10 lijnen, 10 woorden en 226 karakters.

Je kan dit commando gebruiken met de volgende opties wanneer je enkel geïnteresseerd bent in één of enkele:
- `wc -l`: tel enkel aantal lijnen
- `wc -w`: tel enkel aantal woorden
- `wc -c`: tel enkel aan karakters


### Bestanden bewerken met Nano en Vi

##### Nano

Nano is een eenvoudige editor die makkelijk te gebruiken is.

Om een bestand te openen in nano gebruik je het volgende commando:
```bash
nano bestand.txt
```

Onderaan je tekst editor zie je de opties die je kan gebruiken om onder andere je bestand op te slaan of je editor te sluiten.

![nano tekst editor](/images/nano.png)

##### Vi

Vi en Vim zijn krachtigere editors, maar moeilijker voor beginners.

Een bestand openen in vi doe je met het commando:
```bash
vi bestand.txt
```

![vi tekst editor](/images/vi.png)

In Vi wordt er gewerkt met **modi**, er zijn er drie:
- **Command Mode** (standaardmodus): Hiermee geef je commando’s in
- **Insert Mode (`i`)**: Hiermee kan je tekst invoeren
- **Ex Mode (`:`)**: Voor bestandsbeheer (opslaan, afsluiten)

Let op, Vi toont je niet welke commando's er voor je beschikbaar zijn zoals in nano. Hier zijn enkele belangrijke commando's voor als je met Vi zou willen werken:
- `i`: Ga naar Insert Mode (begin met typen)
- `ESC`: Terug naar Command Mode
- `:w`: Opslaan
- `:q`: Afsluiten
- `:q!`: Afsluiten zonder opslaan
- `dd`: Verwijder een volledige regel
- `yy`: Kopieer een regel
- `p`: Plak de gekopieerde regel
- `/woord`: Zoek een woord