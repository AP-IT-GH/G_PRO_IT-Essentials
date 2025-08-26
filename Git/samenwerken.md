### Samenwerken via aan Remote Repository

#### Wat is een Remote Repository?
Een **remote repository** is een opslagplaats voor code die zich op een externe server bevindt, zoals GitHub, GitLab of Bitbucket. In tegenstelling tot een lokale repository (die alleen op je eigen computer staat), is een remote repository toegankelijk voor meerdere ontwikkelaars, waardoor samenwerking mogelijk wordt.

#### Waarom gebruiken we een Remote Repository?
- **Samenwerking**: Ontwikkelaars kunnen gezamenlijk aan dezelfde codebase werken zonder elkaar in de weg te zitten.
- **Back-ups**: Code wordt veilig bewaard op een externe server, waardoor je minder risico loopt om gegevens te verliezen.
- **Versiebeheer**: Iedereen kan de laatste versie van de code ophalen en bijdragen zonder conflicten.

##### 1. Een bestaande repository koppelen aan een remote
Als je een lokaal project hebt en dit wilt koppelen aan een remote repository:
```sh
git remote add origin https://github.com/jouw-gebruikersnaam/jouw-repository.git
```
Dit stelt de remote repository in onder de naam `origin`.

##### 2. De remote repositories bekijken
```sh
git remote -v
```
Hiermee kun je controleren welke remotes aan je project gekoppeld zijn.

##### 3. Wijzigingen uploaden naar de remote repository
Om je lokale wijzigingen naar de remote repository te sturen:
```sh
git push origin main
```
Dit stuurt de laatste commits naar de `main` branch van de remote repository.

##### 4. De nieuwste wijzigingen van de remote ophalen
Als andere ontwikkelaars wijzigingen hebben geüpload, kun je die ophalen met:
```sh
git pull origin main
```
Dit haalt de nieuwste wijzigingen op en probeert ze samen te voegen met je lokale repository.

##### 5. Een project clonen vanuit een remote repository
Als je aan een bestaand project wilt meewerken, kun je het klonen naar je eigen computer:
```sh
git clone https://github.com/jouw-gebruikersnaam/jouw-repository.git
```
Dit maakt een lokale kopie van de remote repository.

### Samenwerken via GitHub
GitHub is een populair platform om met meerdere ontwikkelaars aan één project te werken. Hier is hoe je efficiënt samenwerkt:

##### 1. Een repository forken
Wanneer je aan een project wilt bijdragen zonder directe toegang tot de hoofdrepository, kun je deze **forken**:
```sh
# Ga naar de repository op GitHub en klik op 'Fork'
```
Hiermee maak je een eigen kopie van het project in je GitHub-account.

##### 2. Een lokale kopie maken
Clone de geforkte repository naar je computer:
```sh
git clone https://github.com/jouw-gebruikersnaam/geforkte-repository.git
```
Hiermee haal je de code binnen en kun je lokaal werken.

##### 3. Een nieuwe branch maken voor wijzigingen
Werk aan een nieuwe feature of bugfix in een aparte branch:
```sh
git checkout -b nieuwe-feature
```

##### 4. Wijzigingen committen en pushen
Voeg je wijzigingen toe en stuur ze naar je repository:
```sh
git add .
git commit -m "Nieuwe feature toegevoegd"
git push origin nieuwe-feature
```

##### 5. Een Pull Request (PR) indienen
Ga naar je repository op GitHub en dien een **Pull Request** in. Dit vraagt de originele repository-beheerder om je wijzigingen te bekijken en eventueel samen te voegen.

##### 6. Samenwerking en Code Review
Andere teamleden kunnen je Pull Request bekijken, opmerkingen toevoegen en vragen om aanpassingen voordat de code wordt geaccepteerd en samengevoegd.

##### 7. Samenvoegen met de hoofdrepository
Na goedkeuring wordt de branch samengevoegd met de hoofdbranch (`main` of `master`). Je kunt daarna je lokale repository bijwerken:
```sh
git pull upstream main
```
Hiermee haal je de nieuwste versie van de code binnen.

### Hoe werkt samenwerken met Remote Repositories?
1. **Een project wordt gehost op een platform zoals GitHub**
2. **Ontwikkelaars klonen of forken de repository naar hun eigen computer**
3. **Iedereen werkt aan eigen branches en commit wijzigingen lokaal**
4. **Wijzigingen worden gepusht naar de remote repository**
5. **Andere teamleden kunnen de wijzigingen ophalen en samenvoegen via Pull Requests**

Door een remote repository te gebruiken, kunnen teams efficiënt samenwerken, code delen en versiebeheer toepassen zonder conflicten. GitHub en andere platforms maken dit proces gestroomlijnd en overzichtelijk.
