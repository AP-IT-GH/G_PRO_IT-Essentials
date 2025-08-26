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

We bekijken onder andere hoe we:
- een container opstarten op basis van een bestaan image,
- een eigen image maken,
- een image publiceren.

