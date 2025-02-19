# Labo-03: Folderstructuur, Terminal en Git

### Leerstof
- [Folderstructuur en Werken met de Terminal](/Folderstructuur_Terminal/folder_structure_terminal.md)
- [Git](/Git/git_version_control.md)


### Hulpbronnen
- Maak gebruik van Windows Powershell of Git Bash om je oefeningen te maken.


### Oefening 1: Mappen en bestanden maken
1. Ga naar de Documenten-map.
2. Maak een nieuwe map aan met de naam 'TerminalOefeningen':
`mkdir TerminalOefeningen`
3. Ga naar deze map: `cd TerminalOefeningen`
4. Maak een nieuw bestand aan genaamd `oefening.txt`:
    - Linux/macOS/Git Bash: `touch oefening.txt`
    - Windows (PowerShell): `New-Item -ItemType File oefening.txt`
5. Controleer of het bestand is aangemaakt door de mapinhoud te bekijken (`ls`).
6. Open het bestand in een editor:
    - Windows: `code oefening.txt`
    - Linux/macOS: `code oefening.txt`

### Oefening 2: Een simpele projectstructuur maken

Je gaat een standaard folderstructuur voor een website bouwen met slechts een paar commando’s.

1. Ga naar je Documenten-map (`cd ~/Documents` of `cd C:\Users\JouwNaam\Documents`).
2. Maak een map 'WebsiteProject' (`mkdir WebsiteProject`) en ga ernaartoe (`cd WebsiteProject`).
3. Maak in één opdracht de volgende submappen aan: `mkdir assets css js images`
4. Maak vervolgens de volgende bestanden aan in de juiste mappen:
    - index.html (`touch index.html` of `New-Item -ItemType File index.html`)
    - css/style.css (`touch css/style.css` of `New-Item -ItemType File css/style.css`)
    - js/script.js (`touch js/script.js` of `New-Item -ItemType File js/script.js`)
    - assets/logo.png (`touch assets/logo.png` of `New-Item -ItemType File assets/logo.png`)
5. Controleer of alles correct is aangemaakt met `ls -R` (toont de structuur van de map en submappen).
6. Open de volledige map in VS Code: `code .`.

### Oefening 3: Een Wiki Creëren met Markdown en de Terminal
1. Open de terminal en ga naar je Documenten-map.
2. Maak een nieuwe map aan voor de wiki en navigeer naar de map
3. Binnen deze map maak je een basisstructuur voor de wiki
    - `pages/` bevat de verschillende wiki-pagina's.
    - `assets/` bevat eventuele afbeeldingen of extra bestanden.

    Je folderstructuur ziet er op deze moment alsvolgt uit:
    ```bash
    Documenten/
    │── WikiProject/
    │   ├── assets/
    │   ├── pages/
    ```
4. Maak nu een hoofdindex (`index.md`) die dient alss stratpagina van de wiki.
5. Maak vervolgens enkele wiki-pagina's aan binnen de `pages/` map:
    - `pages/intro.md`
    - `pages/setup/md`
    - `pages/commands.md`
    - `pages/git.md`
6. Controleer of alle bestanden en mappen correct zijn aangemaakt.
7. Open `index.md` in Visual Studio Code.
8. Voeg de volgende inhoud toe en sla op:
    ```Markdown
    # Mijn Wiki Project

    Welkom bij deze wiki! Hier vind je documentatie over het werken met de terminal en Git.

    ## 📄 Inhoud
    - [Introductie](pages/intro.md)
    - [Setup](pages/setup.md)
    - [Handige terminalcommando’s](pages/commands.md)
    - [Werken met Git](pages/git.md)
    ```
9. Open `pages/intro.md` en voeg de volgende tekst toe:
    ```Markdown
    # Introductie

    Deze wiki bevat nuttige informatie over werken met de terminal en versiebeheer met Git.
    ```
10. Open `pages/setup.md` en voeg de volgende tekst toe:
    ```Markdown
    # Setup

    ## Vereisten
    - Git geïnstalleerd
    - Basiskennis van de terminal

    ## Installatie
    1. Installeer Git via [de officiële website](https://git-scm.com/).
    2. Open de terminal en typ: `git --version`.
    ```
11. Vul `pages/commands.md` met basis terminalcommando’s:
    ```Markdown
    # Handige terminalcommando’s

    Hier zijn enkele nuttige commando's:

    | Commando | Beschrijving |
    |----------|-------------|
    | `pwd` | Toont de huidige directory |
    | `ls` | Toont de bestanden in de huidige directory |
    | `cd` | Verandert van directory |
    | `mkdir` | Maakt een nieuwe map aan |
    | `touch` | Maakt een nieuw bestand aan |
    ```
12. Vul `pages/git.md` met basisinformatie over Git:
    ```Markdown
    # Werken met Git

    ## Basiscommando’s
    - `git init` – Initialiseer een Git-repository
    - `git status` – Bekijk de status van de repository
    - `git add .` – Voeg bestanden in de huidige folder toe aan de staging area
    - `git commit -m "Bericht"` – Sla wijzigingen op
    ```
13. Open de volledige wiki in Visual Studio Code en druk **Ctrl + Shift + V** om een preview van de Markdown-bestanden te bekijken.

Je folderstructuur zou er nu als volgt moeten uitzien:
```
WikiProject/
│── index.md
│── assets/
│   ├── (Afbeeldingen en andere bestanden)
│── pages/
│   ├── intro.md
│   ├── setup.md
│   ├── commands.md
│   ├── git.md
```

### Oefening 4: Initialiseren van een Git-repository
1. Maak een nieuwe map aan op je computer genaamd `git-oefening`.
2. Navigeer met de terminal naar deze map.
3. Initialiseer een nieuwe Git-repository met het juiste commando.
4. Controleer de status van de repository en beantwoord de volgende vragen:
   - Worden er al bestanden getrackt?
   - Wat zegt Git over de status van de repository?

### Oefening 5: Bestanden toevoegen en committen
1. Maak een nieuw bestand genaamd `index.html`.
2. Controleer de status van de repository. Wat zie je?
3. Voeg het bestand toe aan de staging area.
4. Controleer opnieuw de status. Wat is er veranderd?
5. Maak een commit met de boodschap `"Eerste commit: index.html toegevoegd"`.
6. Controleer de commitgeschiedenis.

### Oefening 6: Meerdere bestanden toevoegen en verwijderen
1. Maak drie nieuwe bestanden: `style.css`, `script.js` en `readme.md`.
2. Controleer de status van de repository.
3. Voeg alle bestanden in één keer toe aan de staging area.
4. Commit de wijzigingen met een passende commitboodschap.
5. Beslis dat `readme.md` toch niet nodig is en verwijder het zowel uit Git als van je computer.
6. Maak een nieuwe commit met een beschrijving van de verwijdering.
7. Bekijk de commitgeschiedenis.

### Oefening 7: Wijzigingen bekijken en herstellen
1. Open `index.html` en voeg een `<h1>`-titel toe.
2. Controleer de status van de repository. Wat zie je?
3. Bekijk de exacte wijzigingen met een Git-commando.
4. Herstel de wijzigingen en controleer opnieuw de status.

### Oefening 8: Veranderingen terugdraaien vóór een commit
1. Open `script.js` en voeg volgende lijn code toe.
    ```JavaScript
    console.log("Hello World!");
    ```
2. Voeg `script.js` toe aan de staging area.
3. Beslis dat je deze wijziging toch niet wil committen.
4. Haal `script.js` terug uit de staging area en controleer de status.

### Oefening 9: Een volledige projectworkflow uitvoeren
1. Maak een nieuw project met de volgende bestanden:
   - `index.html`
   - `style.css`
   - `script.js`
2. Initialiseer een Git-repository.
3. Voeg de bestanden toe en commit ze.
4. Open `style.css` en voeg een regel toe:
   ```css
   body { background-color: lightgray; }
   ```
5. Bekijk de wijzigingen en commit de aanpassing.
6. Verwijder `script.js` uit het project en commit deze verwijdering.
7. Controleer de commitgeschiedenis en verifieer of alle stappen correct zijn uitgevoerd.