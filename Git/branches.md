### Werken met Branches

#### Wat is een Branch in Git?
Een **branch** (vertakking) in Git is als een kopie van je project waarin je veilig kunt werken zonder de hoofdversie te veranderen. Dit is handig wanneer je nieuwe functies wilt toevoegen of iets wilt testen zonder dat het invloed heeft op de originele code.

#### Waarom gebruiken we branches?
- **Veilig experimenteren**: Je kunt nieuwe functies testen zonder de werkende code te breken.
- **Samenwerken**: Verschillende teamleden kunnen aan aparte taken werken zonder elkaar in de weg te zitten.
- **Versies beheren**: Je kunt oude en nieuwe versies van je project netjes bijhouden.

#### Basiscommando's voor Branching

![Git Branching Illustratie](/images/git_branch_merge.png)
De bovenstaande afbeelding toont hoe Git branching werkt. De `master` (of `main`) branch is de hoofdversie van het project. Wanneer je een nieuwe branch (`new_feature`) maakt, ontstaat er een aparte lijn waarin je wijzigingen kunt aanbrengen zonder de hoofdbranch te beïnvloeden. Nadat je tevreden bent met de aanpassingen, wordt de nieuwe branch samengevoegd met de hoofdbranch. Dit proces heet **merging**.

##### 1. Huidige branches bekijken
```sh
git branch
```
Dit laat zien in welke branch je nu werkt en welke andere branches er zijn.

##### 2. Een nieuwe branch maken
```sh
git branch nieuwe-feature
```
Dit maakt een nieuwe branch genaamd `nieuwe-feature`, maar je blijft nog steeds in de vorige branch. 

💡 **Let op:** Git werkt met een 'pointer'-systeem. Wanneer je een nieuwe branch aanmaakt, blijft je huidige werkplek nog steeds in de oude branch. Om echt in de nieuwe branch te gaan werken, moet je expliciet overschakelen met `git checkout` of `git switch`.

##### 3. Overschakelen naar een andere branch
```sh
git checkout nieuwe-feature
```
Of, een kortere manier in nieuwere Git-versies:
```sh
git switch nieuwe-feature
```
Hiermee wissel je naar de branch `nieuwe-feature` en kun je daar verder werken.

##### 4. Een branch maken én direct overschakelen
```sh
git checkout -b nieuwe-feature
```
Of in nieuwere versies:
```sh
git switch -c nieuwe-feature
```
Dit maakt de branch en schakelt er direct naartoe over.

##### 5. Wijzigingen opslaan in een branch
Zorg ervoor dat je je wijzigingen opslaat:
```sh
git add .
git commit -m "Nieuwe functie toegevoegd"
```

##### 6. Branch samenvoegen met de hoofdbranch (merge)
Als je tevreden bent met de wijzigingen, kun je ze terug samenvoegen met de hoofdbranch (meestal `main` of `master`):
```sh
git checkout main   # Terug naar de hoofdbranch
git merge nieuwe-feature  # Wijzigingen samenvoegen
```

##### 7. Een branch verwijderen
Als je klaar bent met een branch en deze niet meer nodig hebt:
```sh
git branch -d nieuwe-feature
```

#### Hoe werkt dit in de praktijk?
Stel je voor dat je een website bouwt. Je hebt een hoofdbranch genaamd `main` waarin de stabiele versie van je site staat. Nu wil je een nieuwe knop toevoegen zonder de bestaande website te breken:
1. Je maakt een nieuwe branch: `git branch nieuwe-knop`
2. Je schakelt naar deze branch: `git switch nieuwe-knop`
3. Je voegt de knop toe en commit je wijzigingen.
4. Als alles goed werkt, voeg je de `nieuwe-knop` branch samen met `main`.
5. Branch verwijderen als hij niet meer nodig is.

Door branches te gebruiken voor nieuwe ontwikkelingen blijft je project overzichtelijk en stabiel. Dit vermindert de kans op fouten, omdat je pas wijzigingen toevoegt aan de hoofdcode nadat alles getest en goedgekeurd is. Je voegt namelijk pas de nieuwe code toe aan je hoofdcode wanneer alles getest is en werkt.