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


