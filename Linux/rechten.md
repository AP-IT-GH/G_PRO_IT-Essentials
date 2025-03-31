## Rechten

Rechten in Linux zijn fundamenteel voor de veiligheid en controle over bestanden en mappen. Elke **bestand** of **map** in Linux heeft 3 soorten **gebruikerscategorieën**:

| Categorie   | Beschrijving                                      |
|-------------|---------------------------------------------------|
| Owner (u)   | De eigenaar van het bestand                       |
| Group (g)   | De gebruikersgroep waartoe de eigenaar behoort    |
| Others (o)  | Iedereen anders op het systeem                    |

Elke categorie kan drie soorten **rechten** hebben:

| Recht   | Letter | Betekenis                                         |
|---------|--------|----------------------------------------------------|
| read    | r      | Lezen van de inhoud van bestand/map               |
| write   | w      | Schrijven/wijzigen (of bestanden toevoegen in map)|
| execute | x      | Uitvoeren van een bestand / map betreden          |

Wanneer we de rechten van een bestand of map gaan bekijken door een gedetailleerde lijstweergave op te vragen van de inhoud van een map met behulp van `ls -l`, zien we iets als volgt:
```bash
-rw-r--r-- 1 jannes studenten  1024 mrt 31 10:00 bestand.txt
```

De rechten van het `bestand.txt` worden als eerste getoond. 
- `-`: geeft aan dat dit een bestand is (een `d` zou directory/map betekenen).
- `rw-`: geeft aan dat de eigenaar (`jannes`) dit bestand mag lezen en schrijven.
- `r--`: geeft aan dat de groep waartoe het bestand behoord (`studenten`) dit bestand mag lezen.
- `r--`: geeft aan dat anderen het bestand ook mogen lezen.

We knippen `-rw-r--r--` dus als het ware in 4, waarbij het eerste teken aangeeft of het om een bestand of map gaat, en de volgende 3 tekens telkens de rechten (`r`,`w`,`x`) aangeven voor de drie gebruikerscategorieën.

### Rechten aanpassen

We kunnen de rechten van een bestand of map ook aanpassen met behulp van het `chmod` commando, en wel op twee verschillende manieren.

##### Met numerieke notatie

Elke recht heeft een waarde:
- `r` (read) = 4
- `w` (write) = 2
- `x` (execute) = 1

Deze waarden kan je optellen voor het toewijzen van bepaalde rechten aan een gebruikerscategorie. 

Stel, 
- je wil de eigenaar (owner) alle rechten toekennen (`rwx`): `4 + 2+ 1 = 7`.
- de groep wil je enkel read en execute rechten toekennen (`r-x`): `4 + 0 + 1 = 5`.
- alle anderen hebben enkel leesrechten (`r--`): `4 + 0 + 0 = 4`.

Met behulp van deze optelsommen kunnen we nu de juiste rechten toekennen aan ons bestand met behulp van het `chmod` commando.
```bash
chmod 754 bestand.txt
```


##### Met symbolische notatie

Wanneer we gebruik willen maken van de symbolische notatie doen we het als volgt:
```bash
chmod u+x bestand.txt    # Voeg uitvoer toe voor eigenaar (+)
chmod g-w bestand.txt    # Haal schrijfrecht weg van groep (-)
chmod o=r bestand.txt    # Zet rechten van anderen op enkel lezen (=)
```

We kunnen deze notatie ook in één commando uitvoeren door een komma (`,`) te gebruiken als scheidingsteken tussen de gebruikerscategorieën.

```bash
chmod u=rwx,g=rx,o=r bestand.txt
```

### Rechten op mappen

Bij mappen gelden rechten net iets anders:

| Recht | Betekenis voor mappen                         |
|-------|-----------------------------------------------|
| r     | Mapinhoud bekijken (bestandsnamen)            |
| w     | Bestanden toevoegen of verwijderen            |
| x     | De map betreden (`cd mapnaam`)                |


### Eigenaar/groep wijzigen

Net zoals we de rechten van bestanden of mappen kunnen aanpassen, kunnen we ook de eigenaar of groep wijzigen waartoe een bestand of map behoord. Dit doen we met het `chown` commando.

```bash
chown jannes bestand.txt            # Verander eigenaar
chown jannes:studenten bestand.txt  # Verander eigenaar en groep
```

Je moet echter meestal wel root of sudo zijn om dit te mogen doen.
