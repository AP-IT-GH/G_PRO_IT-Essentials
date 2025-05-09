# Docker

Wanneer je een app maakt, kan het soms best lastig zijn om ervoor te zorgen dat alles goed werkt op verschillende computers. Misschien draait een programma prima op je eigen laptop, maar geeft het foutmeldingen op die van een collaga. Dit komt vaak door verschillen in de instellingen en programma's die nodig zijn om de app te laten werken.

Docker helpt bij dit probleem door een app en alles wat die nodig heeft in een "**container**" te stoppen. Denk aan een RPG waarin je een personage ontwikkelt met speciale vaardigheden, uitrusting en eigenschappen. Stel je voor dat je dit personage meesleept naar verschillende werelden, maar elke keer dat je een nieuwe wereld binnenstapt, moet je alle instellingen opnieuw aanpassen—je vaardigheden werken ineens anders, je wapens zijn niet compatibel, en sommige spreuken falen door verschillen in de spelregels van die wereld.

Docker werkt als een magische savegame die je personage, inclusief al zijn krachten en uitrusting, in exact dezelfde staat houdt, ongeacht in welke wereld je speelt. Zo kun je overal probleemloos doorgaan zonder je zorgen te maken over aanpassingen of incompatibiliteit.

In dit hoofdstuk ontdek je wat Docker is, waarom het zo handig is voor veel projecten, en hoe je de basiscommando’s gebruikt om zelf aan de slag te gaan.


## Wat is Docker?

Docker is een platform waarmee je applicaties en hun omgeving kunt verpakken in containers. Deze containers zorgen ervoor dat software overal op dezelfde manier werkt, ongeacht op welk systeem je ze draait. Dit maakt het eenvoudig om applicaties te ontwikkelen, testen en implementeren zonder problemen door verschillende configuraties. Docker helpt ontwikkelaars efficiënter te werken en biedt een flexibele, gestandaardiseerde oplossing voor softwaredistributie.

## Waarom Docker Gebruiken?
Docker brengt diverse voordelen met zich mee:
- **Consistentie en Betrouwbaarheid**:
Met Docker is de runtime-omgeving identiek, van ontwikkeling tot productie. Hierdoor weet je zeker dat de omgeving waarin je test precies overeenkomt met die waarin je applicatie uiteindelijk draait.
- **Efficiënte Resourcebenutting**:
In tegenstelling tot traditionele virtuele machines, maken Docker-containers gebruik van het onderliggende besturingssysteem en zijn ze daardoor lichter en sneller. Dat vertaalt zich in snellere opstarttijden en een efficiënt gebruik van hardware.
- **Eenvoudige Samenwerking**:
Wanneer je in een team werkt, zorgt Docker ervoor dat iedereen dezelfde image gebruikt. Hierdoor hoeft niemand maandenlang instellingen na te lopen of incompatibele versies te trotseren. Samenwerken wordt zo een stuk eenvoudiger.
- **Flexibiliteit en Schaalbaarheid**:
Of je nu een simpele webapplicatie of een complexe microservices-architectuur hebt, Docker maakt het makkelijk om meerdere containers samen te laten werken. Met tools als Docker Compose kun je een multi-container setup snel opzetten en beheren. Dit is echter buiten de scope van dit vak en zal je pas later tijdens het OLOD Cloud Systemen leren.
- **Reële Productiesimulatie**:
Met Docker kun je lokaal een omgeving creëren die nauw aansluit bij hoe je applicatie in productie zal draaien. Dit helpt je niet alleen bij het testen van je applicatie, maar ook bij het opsporen van eventuele problemen nog voordat de software gedeployed wordt.

## Installatie
Om Docker te gebruiken, moet je het eerst installeren op je systeem. Ga naar de officiële website van [Docker](https://www.docker.com/) en download de juiste versie voor jouw besturingssysteem (Windows, Mac of Linux). Het programma dat we hiermee installeren is Docker Desktop, een applicatie die het gebruik van Docker op Windows en macOS vereenvoudigt. Het biedt een gebruiksvriendelijke interface waarmee ontwikkelaars containers kunnen beheren zonder complexe configuraties. Volg de installatie-instructies en zorg ervoor dat Docker correct is geïnstalleerd.

Na de installatie kun je controleren of Docker goed werkt door een terminal of command-line te openen en het volgende commando uit te voeren:
```bash
docker --version
```
Dit zal de geïnstalleerde versie van Docker weergeven.

Je kunt ook een testcontainer uitvoeren met:
```bash
docker run hello-world
```

Als alles goed werkt, zie je een bericht waarin Docker aangeeft dat de test geslaagd is.

## Basisbegrippen
Voordat je zelf containers gaat maken, is het handig om de basisbegrippen te begrijpen:
- **Images**: In Docker zijn images als bouwplannen voor containers. Een image bevat alles wat nodig is om een applicatie uit te voeren, zoals de code, instellingen, afhankelijkheden en het besturingssysteem. Wanneer je een container start, wordt deze gemaakt op basis van een image.

- **Containers**: Dit zijn geïsoleerde omgevingen waarin een applicatie wordt uitgevoerd, gebaseerd op een image. Wanneer je een image uitvoert, wordt een container gemaakt. De container is een actieve, geïsoleerde omgeving waarin de applicatie echt draait, gebaseerd op de instructies uit de image.
- **Dockerfile**: Een Dockerfile is een tekstbestand waarin je instructies schrijft om een Docker image te bouwen. Je kunt het zien als een recept dat aangeeft welke onderdelen en instellingen nodig zijn om een applicatie correct te draaien binnen een container.
- **Docker Hub**: Een online platform waar je kant-en-klare images kunt vinden om te gebruiken in je projecten.

## Basis Docker-commando’s in de Praktijk
Laten we nu een kijkje nemen in een aantal essentiële Docker-commando’s en hoe je deze praktisch kunt inzetten.

### Docker-containers op basis van een bestaande image uit Docker Hub
Laten we eerst even kijken hoe we een geïsoleerde Docker-container kunnen runnen op basis van een bestaande image uit Docker Hub. We gaan hiervoor de [officiële Python-image](https://hub.docker.com/_/python) gebruiken om te demonstreren hoe we binnen een container Python-code kunnen uitvoeren, zelfs als Python niet op onze eigen computer geïnstalleerd is.

##### Stap 1: De Python image downloaden
Allereerst moeten we reeds bestaande image te downloaden uit de Docker hub:
```bash
docker pull python
```
De laatste nieuwe versie van python image wordt nu gedownload en zal zodadelijk tussen je lokale images te vinden zijn.

##### Stap 2: Beschikbare Docker-images bekijken
Je kunt alle gedownloade Docker-images bekijken met:
```bash
docker images
```
Dit toont een lijst van alle beschikbare images op je systeem. Als alles goed is gegaan zou je hier nu de python image in moeten terugvinden.

##### Stap 3: De Python container runnen
Nu we image gedownload hebben kunnen we een container gaan opstarten op basis van onze Python image. Dit doen we met het volgende commando:
```bash
docker run -it --name mijn_python_container python
```
Wat gebeurt er?
- `-it` opent een interactieve terminal in de container.
- `--name` mijn_python_container geeft de container een herkenbare naam.
- python is de officiële Python-image van Docker Hub.

Zodra de container is gestart, zit je in een Python-shell binnen de container. Je kunt nu Python-code uitvoeren, zelfs als Python niet op je eigen machine geïnstalleerd is!

Probeer bijvoorbeeld:
```python
print("Hallo vanuit mijn Python Docker-container!")
```

Om de container te verlaten, gebruik je:
```bash
exit
```

Note: stel dat we stap 1 hebben overgeslagen zou bovenstaand commando alsnog werken. Dit komt omdat Docker zelf op zoek gaat naar de image in de Docker hub wanneer het de image niet lokaal kan vinden tussen je reeds gedownloade images. Je zou er dus voor kunnen kiezen stap 1 over te slagen en de kortere weg te nemen.


##### Stap 4: Draaiende containers controleren
Wil je weten welke containers actief zijn? Gebruik het volgende commando:
```bash
docker ps
```
Dit toont een lijst van alle actieve containers.

Wil je ook de gestopte containers zien? Voeg de optie `-a` toe:
```
docker ps -a
```


##### Stap 5: Een gestopte container opnieuw starten
Als je eerder een container hebt gestopt, kun je deze opnieuw starten met:
```bash
docker start mijn_python_container
```
waarbij `mijn_python_container` de naam is van de container die je opnieuw wil opstarten.

Dit brengt de container weer tot leven zonder hem opnieuw te maken.

Om terug de interactieve terminal van de container te openen:
```bash
docker exec -it mijn_python_container python
```

Hiermee start je een Python-shell binnen de draaiende container.

##### Stap 6: Een container stoppen
Wil je een draaiende container netjes afsluiten? Gebruik:
```bash
docker stop mijn_python_container
```
De container wordt gestopt, maar niet verwijderd.

##### Stap 7: Een container herstarten
Je kunt een gestopte container direct opnieuw starten met:
```bash
docker restart mijn_python_container
```
Dit stopt en start de container opnieuw in één stap.

##### Stap 8: Een container verwijderen
Wil je een container volledig verwijderen? Dan zorg je er voor dat je hem eerst stopt:
```bash
docker stop mijn_python_container
```

Vervolgens verwijder je hem met:
```bash
docker rm mijn_python_container
```
Dit verwijdert de container volledig van je systeem.

Stap 9: Een Docker-image verwijderen
Wil je een ongebruikte image verwijderen? Gebruik:
```bash
docker rmi python
```
Dit verwijdert de officiële Python-image terug van je systeem.


### Een eigen Docker-image maken met `docker commit`

Soms wil je een aangepaste versie van een image maken, waarin je extra configuraties, bestanden of software toevoegt. Dit kan met `docker commit`.

##### Stap 1: Een container starten op basis van een bestaande image
We gebruiken de officiële Ubuntu-image als basis.

Start een nieuwe container met Ubuntu:
```bash
docker run -it --name mijn_ubuntu_container ubuntu
```
Wat gebeurt er?
- `-it` zorgt ervoor dat we een interactieve terminal openen.
- `--name mijn_ubuntu_container` geeft de container een naam.
- `ubuntu` is de officiële Ubuntu-image van Docker Hub.

Je zit nu in een Ubuntu-terminal binnen de container.

##### Stap 2: Wijzigingen aanbrengen binnen de container
Nu we in de container zitten, kunnen we aanpassingen maken, zoals extra software installeren.

Installeer een pakket, bijvoorbeeld nano:
```bash
apt update && apt install -y nano
```

Dit voegt nano toe aan de container.

Je kunt ook bestanden toevoegen, bijvoorbeeld:
```bash
echo "Hallo vanuit mijn aangepaste container!" > /home/mijn_bericht.txt
```

Dit maakt een tekstbestand in de container. Als je klaar bent, typ:
```bash
exit
```
Hiermee verlaat je de container zonder hem te stoppen

##### Stap 3: De aangepaste container omzetten naar een nieuwe image
Nu we de container hebben aangepast, willen we een nieuwe image maken op basis van deze container.

Maak een nieuwe image met `docker commit`:
```bash
docker commit mijn_ubuntu_container mijn_ubuntu_v2
```
Wat gebeurt er?
- `mijn_ubuntu_container` is de broncontainer die we eerder hebben gestart.
- `mijn_ubuntu_v2` is de naam van de nieuwe image die we maken.

##### Stap 4: Onze nieuwe image bekijken
Wil je zien welke Docker-images beschikbaar zijn op je systeem? Gebruik:
```bash
docker images
```
Dit toont een lijst van alle beschikbare images, inclusief onze nieuwe `mijn_ubuntu_v2` image.


##### Stap 5: Een nieuwe container starten op basis van de aangepaste image
Nu we onze eigen image hebben gemaakt, kunnen we er een container mee starten.
```bash
docker run -it mijn_ubuntu_v2
```

De container start met alle wijzigingen die we eerder hebben toegevoegd. Je kunt controleren of nano is geïnstalleerd:
```bash
nano /home/mijn_bericht.txt
```
Je zou nu het tekstbestand moeten kunnen aanpassen via de teksteditor nano.


### Een eigen Docker-image maken met een Dockerfile

Hoewel we redelijk eenvoudig onze eigen images kunnen bouwen door het aanpassen van reeds bestaande images via de `docker commit`, is dit toch niet de meest aangeweze methode. Het is namelijk niet herbruikbaar voor onze collega's die met dezelfde projecen aan de slag gaan. We zouden hen dan moeten vertellen wat we telkens zijn gaan uitvoeren alvorens de commit plaatsvond wanneer zij de image opnieuw willen bouwen.

Een Dockerfile biedt een veel betere manier om een Docker-image systematisch en herhaalbaar te bouwen. Met een Dockerfile kun je precies definiëren hoe je image eruit moet zien, welke software moet worden geïnstalleerd, en hoe de container zich moet gedragen.

##### Stap 1: Maak een projectmap
Eerst moeten we een aparte map maken waarin we onze bestanden organiseren.
```bash
mkdir mijn_nginx_site
cd mijn_nginx_site
```

##### Stap 2: Maak de statische website
Laten we een simpele HTML-pagina maken die we gaan hosten.
```bash
mkdir site
touch site/index.html
```

Open `index.html` in een teksteditor en voeg het volgende toe:
```HTML
<!DOCTYPE html>
<html lang="nl">
<head>
    <meta charset="UTF-8">
    <title>Mijn Docker Website</title>
</head>
<body>
    <h1>Welkom bij mijn statische website!</h1>
    <p>Gehost in een Docker-container met Nginx 🚀</p>
</body>
</html>
```
Wat gebeurt hier?
- Dit is een statische HTML-pagina met een titel en een welkomstbericht.
- We gaan deze pagina hosten via **Nginx** in Docker.

##### Stap 3: Schrijf de Dockerfile
Nu maken we een `Dockerfile`, waarmee we een Docker-image kunnen bouwen.
```bash
touch Dockerfile
```

Open het bestand en voeg de volgende configuratie toe:
```Dockerfile
# Stap 1: Gebruik de officiële Nginx-image
FROM nginx:latest

# Stap 2: Kopieer de statische website naar de container
COPY site /usr/share/nginx/html

# Stap 3: Exporteer poort 80 (webserver)
EXPOSE 80
```

Wat gebeurt hier?
- `FROM nginx:latest` → We gebruiken de officiële Nginx-image van Docker Hub.
- `COPY site /usr/share/nginx/html` → We kopiëren onze website naar de standaard webmap van Nginx binnen de container.
- `EXPOSE 80` → We geven aan dat de container poort 80 gebruikt voor de webserver.

##### Stap 4: Bouw de Docker-image
Nu kunnen we onze eigen Docker-image bouwen met:
```bash
docker build -t mijn_nginx_site .
```

Wat gebeurt hier?
- `-t mijn_nginx_site` → Geeft onze image een naam.
- `.` → Geeft aan dat de Dockerfile zich in de huidige map bevindt.

Je kunt controleren of de image correct is gebouwd met:
```bash
docker images
```

##### Stap 5: Een container starten met de nieuwe image
Nu gebruiken we onze eigen image om een container te starten:
```bash
docker run -d -p 8080:80 --name mijn_webserver mijn_nginx_site
```

Wat gebeurt er?
- `-d` → Laat de container op de achtergrond draaien.
- `-p 8080:80` → Koppelt poort 8080 van de host (onze computer) aan poort 80 van de container.
- `--name mijn_webserver` → Geeft de container een herkenbare naam.
- `mijn_nginx_site` → Dit is onze custom Nginx-image.

Test de server. Ga naar je browser en typ: http://localhost:8080

Je zou nu jouw statische website moeten zien.
