# Labo-03: Folderstructuur, Terminal en Git

### Leerstof
- [Folderstructuur en Werken met de Terminal](/folderstructuur-en-terminal.md)
- [Versiebeheer](/Git/versiebeheer.md)
- [Git Basics](/Git/git-basics.md)


### Hulpbronnen
- Maak gebruik van Windows Powershell of Git Bash om je oefeningen te maken.


### Oefening 4: Initialiseren van een Git-repository
1. Maak een nieuwe map aan op je computer genaamd `git-oefening`.
2. Navigeer met de terminal naar deze map.
3. Initialiseer een nieuwe Git-repository met het juiste commando.
4. Controleer de status van de repository en beantwoord de volgende vragen:
   - Worden er al bestanden getrackt?
   - Wat zegt Git over de status van de repository?

**Oplossing:**
```bash
mkdir git-oefening
cd git-oefening
git init
git status
```

### Oefening 5: Bestanden toevoegen en committen
1. Maak een nieuw bestand genaamd `index.html`.
2. Controleer de status van de repository. Wat zie je?
3. Voeg het bestand toe aan de staging area.
4. Controleer opnieuw de status. Wat is er veranderd?
5. Maak een commit met de boodschap `"Eerste commit: index.html toegevoegd"`.
6. Controleer de commitgeschiedenis.

**Oplossing:**
```bash
git status
git add index.html
git status
git commit -m "Eerste commit: index.html toegevoegd"
git log --oneline
```

### Oefening 6: Meerdere bestanden toevoegen en verwijderen
1. Maak drie nieuwe bestanden: `style.css`, `script.js` en `readme.md`.
2. Controleer de status van de repository.
3. Voeg alle bestanden in één keer toe aan de staging area.
4. Commit de wijzigingen met een passende commitboodschap.
5. Beslis dat `readme.md` toch niet nodig is en verwijder het zowel uit Git als van je computer.
6. Maak een nieuwe commit met een beschrijving van de verwijdering.
7. Bekijk de commitgeschiedenis.

**Oplossing:**
```bash
git status
git add .
git commit -m "Stylesheet en script toegevoegd"
git rm readme.md
git commit -m "Readme bestand verwijderd"
git log --oneline
```

### Oefening 7: Wijzigingen bekijken en herstellen
1. Open `index.html` en voeg een `<h1>`-titel toe.
2. Controleer de status van de repository. Wat zie je?
3. Bekijk de exacte wijzigingen met een Git-commando.
4. Herstel de wijzigingen en controleer opnieuw de status.

**Oplossing:**
```bash
git status
git diff
git restore index.html
git status
```

### Oefening 8: Veranderingen terugdraaien vóór een commit
1. Open `script.js` en voeg volgende lijn code toe.
    ```JavaScript
    console.log("Hello World!");
    ```
2. Voeg `script.js` toe aan de staging area.
3. Beslis dat je deze wijziging toch niet wil committen.
4. Haal `script.js` terug uit de staging area en controleer de status.

**Oplossing:**
```bash
git add script.js
git status
git restore --staged script.js
git status
```

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

**Oplossing:**
```bash
mkdir git-project
cd git-project

git init
git add .
git commit -m "Eerste versie van het project"

git status
git diff
git commit -am "Achtergrondkleur toegevoegd"
git rm script.js
git commit -m "Scriptbestand verwijderd"
git log --oneline
```