# Folderstructuur en Werken met de Terminal

Bij het programmeren is het belangrijk om efficiënt te werken met bestanden en mappen. In dit hoofdstuk leren we hoe de folderstructuur op een computer werkt en hoe we de terminal gebruiken om bestanden te beheren. 


## 1. Folderstructuur van een computer

### 1.1 Wat is een folderstructuur?

Een folderstructuur (of bestandsstructuur) bepaalt hoe bestanden en mappen worden georganiseerd op een computer. Je kunt dit vergelijken met een **archiefkast**:
- De **hoofdmap** is de kast zelf.
- De **submappen** zijn de lades in de kast.
- De **bestanden** zijn de documenten in de lades.

Elk bestand en elke map heeft een uniek **pad** dat aangeeft waar het zich bevindt in de structuur. Dit pad kan **absoluut** of **relatief** zijn:
- **Absoluut pad:** Begint vanaf de root-directory (bijv. `C:\Users\Jannes\Documents` op Windows of `/home/jannes/Documents` op Linux/Mac).
- **Relatief pad:** Begint vanaf de huidige locatie (bijv. `Documents/ProjectX`).

### 1.2 Belangrijke mappen en schijven

#### Root-directory (`/` of `C:\`)

De **root-directory** is de bovenste map waarin alle andere mappen en bestanden zich bevinden.
- **Op Windows:** `C:\` is de hoofdschijf waar het besturingssysteem zich bevindt.
- **Op Mac/Linux:** `/` is de root-directory waar alles start.

![Basis Folderstructuur](/images/file-system-structure.png)

#### Home-directory (`C:\Users\JouwNaam` of `/home/jouwnaam`

Dit is de **persoonlijke map van de gebruiker**, waarin alle standaardmappen zoals **Documenten, Downloads, Muziek, Afbeeldingen en Desktop** zich bevinden.

Bijvoorbeeld, op Windows bevindt de gebruikersmap zich meestal in:
```
C:\Users\JouwNaam\
```
Op Linux en Mac is dit:
```
/home/jouwnaam/
```

#### Verschillende schijven en hun gebruik

Veel computers hebben meerdere schijven of partities:
- **C-schijf (`C:\`)**: De **hoofdschijf** waar Windows en programma's zijn geïnstalleerd.
- **D-schijf (`D:\`)**: Vaak gebruikt als extra opslag voor persoonlijke bestanden.

Soms worden standaardmappen zoals Documenten en Afbeeldingen verplaatst naar de D-schijf om de C-schijf vrij te houden en de computer sneller te maken.

Het opslaan van grote bestanden op een aparte schijf helpt de prestaties van de computer te verbeteren. Windows gebruikt een deel van de C-schijf als virtueel geheugen, waardoor een volle schijf de snelheid van het systeem kan beïnvloeden.


#### Cloudopslag (Google Drive, OneDrive, Dropbox, etc.)

Cloudopslag zoals Google Drive, OneDrive en Dropbox biedt voordelen zoals automatische back-ups en toegang vanaf meerdere apparaten.

Je kan cloudopslag zien als een online harde schijf. Je slaat bestanden op via internet in plaats van op je computer. Op deze manier kan je er overal bij, zolang je internet hebt. Je bestanden blijven veilig, zelfs als je computer crasht of je telefoon kapotgaat.



Als je de desktop-app van OneDrive of Google Drive installeert, maakt die een map aan op je computer (standaard in je gebruikersmap, zoals `C:\Users\JouwNaam\OneDrive` of `C:\Users\JouwNaam\Google Drive)`. Alles wat je hierin zet, wordt gesynchroniseerd met de cloud.

**Let op!**
Het is echter niet optimaal om gebruik te gaan maken van cloudopslag zoals Google Drive of OneDrive voor onze programmeerprojecten in op te slagen. Omwille van volgende redenen doen we dit beter niet:

- **Synchronisatieconflicten**: Cloudservices proberen bestanden continu te synchroniseren, wat kan leiden tot conflicten en beschadigde bestanden.
- **Trage prestaties**: Programmeertools zoals Git en Node.js werken minder efficiënt op gesynchroniseerde mappen.
- **Onverwachte bestandswijzigingen**: OneDrive kan bestanden verplaatsen of gedeeltelijk uploaden, waardoor repositories corrupt raken.

Bewaar dus je programmeerprojecten lokaal, bijvoorbeeld in `C:\Projects` of `D:\Projects`, en gebruik **Git met een remote repository** voor back-ups. 

Voordat we Git en versiebeheer gebruiken, moeten we eerst begrijpen wat een **terminal (of command line interface, CLI)** is, en hoe we deze kunnen gebruiken om door onze bestanden en mappen te navigeren en nieuwe bestanden/mappen te maken. Dit is belangrijk, want Git werkt vooral via de terminal.



## **2. De Terminal en Navigatie**

### **2.1 Wat is de terminal?**

De terminal (ook wel command line interface - CLI) is een programma waarmee je tekstcommando’s invoert om een computer opdrachten te geven. Dit is een alternatieve manier om met bestanden en mappen te werken zonder een muis te gebruiken.

| **Besturingssysteem** | **Terminal openen** |
|----------------------|---------------------|
| **Windows** | PowerShell of Git Bash |
| **Mac** | Terminal via `Cmd + Spatie` -> "Terminal" |
| **Linux** | Terminal (`Ctrl + Alt + T`) |

### **2.2 Basiscommando’s voor navigatie**

De volgende commando’s helpen je om door mappen te navigeren:

| Commando |                            Beschrijving                           |    Voorbeeld    |
|:--------:|:-----------------------------------------------------------------:|:---------------:|
| `pwd`      | Toont de huidige map (werkt niet in Windows CMD, wel in Git Bash) | `$ pwd`           |
| `ls`       | Toont bestanden en mappen in de huidige directory                 | `$ ls`            |
| `cd <map>` | Verandert de huidige map                                          | `$ cd Documenten` |
| `cd ..`    | Gaat één map omhoog                                               | `$ cd ..`         |
| `cd /`     | Gaat naar de root van het systeem                                 | `$ cd /`          |
| `cd ~`     | Gaat naar je home-map                                             | `$ cd ~`          |

**Opmerking voor Windows-gebruikers:** Het commando pwd werkt niet in de standaard Windows CMD. Om de huidige map te bekijken, kun je cd zonder argument gebruiken:
```bash
cd
```


### 2.3 Mappen en bestanden maken

Naast navigeren kun je in de terminal ook nieuwe bestanden en mappen maken.

|           Commando          |                        Beschrijving                       |              Voorbeeld             |
|:---------------------------:|:---------------------------------------------------------:|:----------------------------------:|
| `mkdir <mapnaam>`             | Maakt een nieuwe map                                      | `$ mkdir MijnProject`                |
| `touch <bestandsnaam>`        | Maakt een nieuw, leeg bestand (werkt niet in Windows CMD) | `$ touch script.js`                  |
| `echo "tekst"` > bestandsnaam | Maakt een bestand en schrijft er iets in                  | `$ echo "Hallo wereld" > index.html` |
| `rm <bestand>`                | Verwijdert een bestand                                    | `$ rm test.txt`                      |
| `rmdir <map>`                 | Verwijdert een lege map                                   | `$ rmdir OudeMap`                    |
| `rm -r <map>`                 | Verwijdert een map en alle inhoud                         | `$ rm -r ProjectMap`                 |

**Opmerking:** In Windows (PowerShell) gebruik je in plaats van touch het volgende:

```powershell
New-Item -ItemType File index.js
```

### 2.4 Bestanden openen en bewerken in de terminal
Je kunt bestanden openen vanuit de terminal:

| Besturingssysteem | Commando om een bestand te openen |
|:-----------------:|:---------------------------------:|
| Windows           | `notepad index.js`                  |
| Mac               | `open index.js `                    |
| Linux             | `xdg-open index.js`                |

Of gebruik een code-editor zoals VS Code:

```Bash
code .
```

Dit opent de huidige map (`.`) in Visual Studio Code.

**Opmerking:** Dit werkt alleen als VS Code correct is geïnstalleerd en de code-opdracht beschikbaar is in de terminal. Als code . niet werkt, moet je VS Code handmatig toevoegen aan de PATH-instellingen.

