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


