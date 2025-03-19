## Input en Output Streams in Linux

In Linux (en Unix-gebaseerde systemen) werken programma’s met streams voor het verwerken van data. 

![in- en output streams](/images/in-and-out-streams.png)


Er zijn drie standaardstreams:

- **Standaard input (stdin)** [Bestandsdescriptor 0]
    - Verwacht invoer van de gebruiker of een bestand.
    - Standaard komt de invoer van het toetsenbord      
- **Standaard output (stdout)** [Bestandsdescriptor 1]
    - Stuurt de normale uitvoer van een programma naar het scherm.
- **Standaard error (stderr)** [Bestandsdescriptor 2]
    - Stuurt foutmeldingen naar het scherm.

Linux stelt je in staat om deze streams te *'redirecten'* en met behulp van een *'pipeline'* de uitvoer van het ene programma naar het andere door te sturen. Zo kan je bijvoorbeeld een sortering uitvoeren met het `sort` commando en deze opslagen in een nieuw bestand.

### Redirection in Linux

Redirection stelt je in staat om de standaard input, output of error output om te leiden naar een bestand of een ander commando.

#### Output Redirection (`>`, `>>`)

Laten we eerst even kijken hoe we de standaardoutput naar een bestand schrijven.

##### Overschrijven (`>`)

Wanneer we standaardoutput van een commando naar een bestand willen schrijven maken we gebruik van `>`. 

```bash
echo "Hallo wereld" > bestand.txt
```
Dit schrijft "Hallo wereld" naar bestand.txt.

⚠️ Let op, indien het bestand reeds bestaat zal dit het bestand volledig overschrijven.

##### Toevoegen (`>>`)

Wanneer je bestand waarin je de uitkomst wil naartoe schrijven al bestaat, en je wil de uitkomst van de je commando toevoegen aan dit bestand zonder het te overschrijven kunnen we `>>` gebruiken.

```bash
echo "Nieuwe regel" >> bestand.txt
```

Nu wordt "Nieuwe regel" toegevoegd aan bestand.txt, zonder de vorige inhoud te verwijderen.

#### Input Redirection (`<`)

Je kunt standaard input van een bestand lezen in plaats van van het toetsenbord. Zo kunnen we bijvoorbeeld opties voor een commando opslagen in een bestand en dit bestand gebruiken als input stream wanneer we het commando uitvoeren.

**sort_opties.txt**
```bash
-t ';' 
-k 3 
-n 
-r
```

```bash
sort $(< sort_opties.txt) pokemon.txt
```

We gebruiken hier `$(< bestand)` om de inhoud van een bestand in te lezen en als een **argument** door te geven.

#### Error Redirection (`2>`, `2>>`)

Fouten (stderr) kunnen ook naar een bestand worden omgeleid.

##### Overschrijven (`2>`)

In het volgende commando proberen we een directory te tonen die niet bestaat:

```bash
ls /niet-bestaande-map 2> fouten.log
```

We sturen de foutmelding naar `fouten.log` in plaats van naar het scherm door middel van `2>`.

⚠️ Let op, indien het bestand reeds bestaat zal dit het bestand volledig overschrijven.

##### Append (`2>>`)

Wanneer we de foutmelding willen toevoegen aan een reeds bestand zonder te overschrijven gebruiken we weer twee groter dan tekens.

```bash
ls /nog-een-niet-bestaande-map 2>> fouten.log
```

Nu wordt de foutmelding toegevoegd aan fouten.log.

#### Output en Error samen redirecten (`2>&1`)

Soms wil je zowel standaardoutput als standaarderror naar hetzelfde bestand sturen.

```bash
ls /bestaande-map /niet-bestaande-map > output_en_fouten.log 2>&1
```

- `> output_en_fouten.log` stuurt stdout naar het bestand.
- `2>&1` stuurt stderr naar dezelfde bestemming als stdout.

Je kan dit ook nog korter schrijven met `&>`:

```bash
ls /bestaande-map /niet-bestaande-map &> output_en_fouten.log
```

### Combineren van Commando's

Een **pipeline (|)** stuurt de uitvoer van het ene commando naar de invoer van een ander commando.

![pipeline](/images/pipeline.png)

Op deze manier kunnen we in één taak de inhoud tonen van de `/etc`-map, en hierin filteren op bestanden die `"passwd"` bevatten:

```bash
ls -al /etc | grep "passwd"
```