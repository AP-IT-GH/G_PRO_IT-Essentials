# Docker

In de wereld van moderne softwareontwikkeling worden we dagelijks geconfronteerd met uitdagingen zoals inconsistent werkende omgevingen, ingewikkelde afhankelijkheden en moeizame samenwerking tussen verschillende teams. Docker biedt een oplossing door een uniforme, flexibele en efficiënte manier te bieden om applicaties en hun omgeving samen te verpakken. In dit hoofdstuk leer je wat Docker precies is, waarom het in veel projecten wordt toegepast en hoe je praktisch aan de slag kunt met de basiscommando’s.

## Wat is Docker?
Docker is een platform dat gebruikmaakt van zogenaamde containers om applicaties en alle benodigde afhankelijkheden in één pakket (of image) te verpakken. Denk aan een container als een digitale lunchbox: je stopt er alles in wat je nodig hebt om je applicatie te laten draaien—van code, libraries, systeembestanden tot configuratie-instellingen. Hierdoor draait je applicatie in precies dezelfde omgeving, ongeacht of je deze lokaal, op een server of in de cloud uitvoert. Dit principe verhelpt het klassieke “het werkt op mijn machine”-probleem dat al heel wat frustraties heeft veroorzaakt in de traditionele softwareontwikkeling.

## Waarom Docker Gebruiken?
Docker brengt diverse voordelen met zich mee, zeker voor projecten op het gebied van webontwikkeling:
- **Consistentie en Betrouwbaarheid**:
Met Docker is de runtime-omgeving identiek, van ontwikkeling tot productie. Hierdoor weet je zeker dat de omgeving waarin je test precies overeenkomt met die waarin je applicatie uiteindelijk draait.
- **Efficiënte Resourcebenutting**:
In tegenstelling tot traditionele virtuele machines, maken Docker-containers gebruik van het onderliggende besturingssysteem en zijn ze daardoor lichter en sneller. Dat vertaalt zich in snellere opstarttijden en een efficiënt gebruik van hardware.
- **Eenvoudige Samenwerking**:
Wanneer je in een team werkt, zorgt Docker ervoor dat iedereen dezelfde image gebruikt. Hierdoor hoeft niemand maandenlang instellingen na te lopen of incompatibele versies te trotseren. Samenwerken wordt zo een stuk eenvoudiger.
- **Flexibiliteit en Schaalbaarheid**:
Of je nu een simpele webapplicatie of een complexe microservices-architectuur hebt, Docker maakt het makkelijk om meerdere containers samen te laten werken. Met tools als Docker Compose kun je een multi-container setup snel opzetten en beheren.
- **Reële Productiesimulatie**:
Met Docker kun je lokaal een omgeving creëren die nauw aansluit bij hoe je applicatie in productie zal draaien. Dit helpt je niet alleen bij het testen van je applicatie, maar ook bij het opsporen van eventuele problemen nog voordat de software gedeployed wordt.

## Installatie
Om Docker te gebruiken, moet je het eerst installeren op je systeem. Ga naar de officiële website van Docker en download de juiste versie voor jouw besturingssysteem (Windows, Mac of Linux). Volg de installatie-instructies en zorg ervoor dat Docker correct is geïnstalleerd.

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
- **Images**: Dit zijn blauwdrukken voor containers en bevatten alles wat nodig is om een applicatie te draaien.
- **Containers**: Dit zijn geïsoleerde omgevingen waarin een applicatie wordt uitgevoerd, gebaseerd op een image.
- **Dockerfile**: Een tekstbestand met instructies om een Docker-image te bouwen.
- **Docker Hub**: Een platform waar je kant-en-klare images kunt vinden om te gebruiken in je projecten.

## Basis Docker-commando’s in de Praktijk
Laten we nu een kijkje nemen in een aantal essentiële Docker-commando’s en hoe je deze praktisch kunt inzetten.

1. **`docker ps`**

Toont een lijst van alle actieve containers.
```bash
docker ps
```
- Voeg de optie -a toe om ook de gestopte containers te zien.

2. **`docker build`**
Bouwt een Docker image op basis van een Dockerfile.
- Voorbeeld:
Stel dat je een Dockerfile in de huidige directory hebt:
docker build -t mijn_webapp .
3. docker run
Creëert en start een container op basis van een image.
- Voorbeeld:
Start een container op de achtergrond en koppel poort 3000 van je host aan poort 3000 van de container:
docker run -d -p 3000:3000 mijn_webapp
4. docker start en docker stop
docker start herstart een eerder gestopte container, terwijl docker stop een draaiende container netjes afsluit.
- Voorbeelden:
docker stop <container_id>
docker start <container_id>
5. docker restart
Combineert het stoppen en opnieuw starten van een container in één commando.
- Voorbeeld:
docker restart <container_id>
6. docker exec
Voert een commando uit binnen een draaiende container.
- Voorbeeld:
Open een interactieve shell in een container:
docker exec -it <container_id> /bin/bash
7. docker rm
Verwijdert een of meerdere gestopte containers.
- Voorbeeld:
docker rm <container_id>
8. docker images en docker rmi
docker images toont alle lokaal beschikbare images. Met docker rmi verwijder je images.
- Voorbeelden:
docker images
docker rmi mijn_webapp
9. docker commit en docker tag
docker commit maakt een nieuwe image van een container met alle veranderingen, en docker tag geeft deze image een herkenbare naam of versie-label.
- Voorbeelden:
docker commit <container_id> mijn_gecommit_image:versie1
docker tag mijn_gecommit_image:versie1 mijngebruikersnaam/mijn_webapp:latest
10. docker login, docker push en docker pull
Gebruik docker login om in te loggen bij een Docker registry (zoals Docker Hub). Met docker push upload je een image naar het registry, en met docker pull download je een image van daar.
- Voorbeelden:
docker login
docker push mijngebruikersnaam/mijn_webapp:latest
docker pull nginx:latest

