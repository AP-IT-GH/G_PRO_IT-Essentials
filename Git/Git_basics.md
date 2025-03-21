### Werken met Git

Om efficiënt met Git te werken, is het belangrijk om te begrijpen hoe Git onze bestanden beheert. Git kent drie *'states'* waarin bestanden zich kunnen bevinden:

1. De **working directory**: Dit is de map op je computer waarin je aanpassingen maakt aan bestanden.
2. De **staging area**: Hier voeg je specifieke bestanden toe voordat je een commit maakt. Dit stelt je in staat om gecontroleerd wijzigingen vast te leggen.
3. De **repository**: Wanneer je een commit uitvoert, worden de bestanden definitief opgeslagen in de repository, inclusief een unieke referentie naar deze versie.

![Git states](/images/git-areas.png)


De basisworkflow binnen Git ziet er als volgt uit:

1. Je bewerkt een bestand in de werkdirectory.
2. Wanneer je tevreden bent met de wijziging, voeg je het bestand toe aan de staging area met het commando:
   ```bash
   git add bestandsnaam
   ```
3. Vervolgens sla je de wijziging definitief op in de repository met:
   ```bash
   git commit -m "Duidelijke beschrijving van de wijziging"
   ```
4. Indien je samenwerkt met anderen en een centrale repository gebruikt, kun je je commits naar een remote repository sturen met:
   ```bash
   git push
   ```

Zoals je ziet werkt Git op basis van tekstcommando's die we uitvoeren in de terminal. Laten we even de belangrijkste commando's en principes overlopen.

#### Git-commando's en principes
Om efficiënt met Git te werken, is het handig om de basiscommando’s goed te begrijpen. Hieronder volgt een overzicht van de belangrijkste commando’s die je nodig hebt om een project te beheren.

--- 

**1. Een Git-repository initialiseren**
Voordat je Git kunt gebruiken in een project, moet je een repository initialiseren. Dit doe je met:
```bash
git init
```
Dit commando zet een verborgen `.git`-map op in je projectfolder, waarin Git alle versies en wijzigingen bijhoudt. Vanaf nu is je project een Git-repository.

--- 

**2. De status van je repository controleren**
Voordat je wijzigingen commit of toevoegt, is het handig om te controleren welke bestanden gewijzigd zijn. Dit doe je met:
```bash
git status
```
Dit commando geeft een overzicht van:

- Gewijzigde bestanden die nog niet zijn toegevoegd aan de staging area.
- Nieuwe bestanden die nog niet worden gevolgd door Git.
- Bestanden die klaarstaan om gecommit te worden.

Gebruik dit regelmatig om te weten in welke staat je project zich bevindt.

---

**3. Bestanden toevoegen aan de staging area**
Wanneer je een bestand hebt gewijzigd of een nieuw bestand hebt toegevoegd, moet je het eerst klaarzetten voor committen. Dit doe je met:

```bash
git add bestandsnaam
```
Wil je alle gewijzigde of nieuwe bestanden in één keer toevoegen? Gebruik dan:
```bash
git add .
```
`.` verwijst hier naar de huidige folder. Dit betekend dat alle gewijzigde of nieuwe bestanden in de huidige folder dus in één keer toegevoegd worden.

De bestanden bevinden zich nu in de staging area, wat betekent dat ze klaar zijn om gecommit te worden.

---

**4. Wijzigingen bekijken voordat je commit**
Soms wil je controleren welke wijzigingen er precies zijn gemaakt voordat je commit. Dit kan met:

```bash
git diff
```
- Dit toont alle aanpassingen sinds de laatste commit.
- Wil je enkel wijzigingen zien van bestanden die al in de staging area staan? Gebruik dan:
   ```bash
   git diff --staged
   ```

---

**5. Wijzigingen ongedaan maken (restore)**
Als je wijzigingen hebt gemaakt in een bestand, maar deze ongedaan wilt maken voordat je commit, gebruik dan:
```bash
git restore bestandsnaam
```
- Dit herstelt het bestand naar de laatste gecommit-te versie.
- Wil je ook wijzigingen uit de staging area halen? Gebruik dan:
   ```bash
   git restore --staged bestandsnaam
   ```

Let op: **Dit kan wijzigingen onherroepelijk verwijderen!** Gebruik `git diff` eerst om te controleren wat er veranderd is.

---

**6. Wijzigingen opslaan met een commit**
Zodra je bestanden in de staging area staan, kun je de wijziging definitief opslaan in de repository met:

```bash
git commit -m "Duidelijke beschrijving van de wijziging"
```
- De `-m` tag wordt gebruikt om een commitbericht toe te voegen. Dit bericht beschrijft welke wijzigingen zijn aangebracht.
- Elke commit krijgt een unieke ID en wordt bewaard in de geschiedenis van het project.

Wil je direct alle gewijzigde bestanden committen zonder eerst `git add` te gebruiken? Dan kun je dit doen met:

```bash
git commit -a -m "Commitbericht"
```
Let op: Dit werkt alleen voor bestanden die al eerder getrackt werden door Git.

---

**7. Commitgeschiedenis bekijken**
Om een overzicht te krijgen van de gemaakte commits, gebruik je:

```bash
git log
```
Dit toont een lijst van alle commits, inclusief de unieke commit-ID, de auteur en de datum van de commit.

Wil je een kortere weergave? Gebruik dan:
```bash
git log --oneline
```
Dit toont enkel de commit-ID en het commitbericht, wat handig is voor een snelle blik op de geschiedenis.

--- 

**8. Bestanden verwijderen uit Git**
Soms wil je een bestand verwijderen uit je repository. Dit doe je met:

```bash
git rm bestandsnaam
```
- Dit verwijdert het bestand uit de werkdirectory én uit Git.
- Vergeet niet de wijziging te committen met:
   ```bash
   git commit -m "Bestand verwijderd"
   ```
- Wil je het bestand alleen uit Git verwijderen, maar op je computer behouden? Gebruik dan:
   ```bash
   git rm --cached bestandsnaam
   ```
