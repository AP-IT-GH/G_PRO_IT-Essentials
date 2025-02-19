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
    - index.html (`touch index.html`)
    - css/style.css (`touch css/style.css`)
    - js/script.js (`touch js/script.js`)
    - assets/logo.png (`touch assets/logo.png`)
5. Controleer of alles correct is aangemaakt met `ls -R` (toont de structuur van de map en submappen).
6. Open de volledige map in VS Code (als het geïnstalleerd is): `code .`.

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

### Oefening 4: Markdown Wiki [Git uitbreiding]

1. Voeg een nieuwe pagina toe aan je Wiki over een zelfgekozen onderwerp.
2. Voeg enkele afbeeldingen toe aan de `assets/` folder en toon deze in je nieuwe pagina.
3. Voeg een link toe naar een externe website.
4. Maak een Git repository aan en push je wiki naar GitHub:
    ```bash
    # initialiseer Git
    git init

    # Voeg alle folders en mappen in je project folder toe aan je staging area
    git add .

    # Maak een eerste commit
    git commit -m "Eerste versie van de wiki"

    # Voeg de link naar je remote GitHub repository toe
    git remote add origin <repo-url>

    # Push je lokale repository naar de cloud (GitHub)
    git push -u origin main
    ```

