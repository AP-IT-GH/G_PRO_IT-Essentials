# Labo-10: Docker

### Leerstof
* [Containers](/Docker/containers-en-docker.md)
* [Containers runnen](/Docker/containers-runnen.md)
* [Images maken](/Docker/images-maken.md)
* [Dockerfile](/Docker/de-dockerfile.md)
* [Images publiceren](/Docker/images-publiceren.md)


--- 

## Oefening 1: Een eenvoudige container starten
1. Start een nieuwe container gebaseerd op Alpine Linux en voer een interactief shell-commando uit.
2. Controleer binnen de container welke bestanden en mappen aanwezig.
3. Sluit de container af.
4. Controleer de lijst van gestopte containers.


## Oefening 2: Het beheren van containers
1. Start een Nginx-webserver container en exposeer poort 8080.
2. Open een browser en ga naar http://localhost:8080 om te zien of de server draait.
3. Bekijk de actieve containers.
3. Stop de container.
4. Start de container opnieuw.
5. Verwijder de container volledig.

## Oefening 3: Een eigen image maken en beheren
1. Bekijk de lokaal beschikbare Docker images.
2. Download een Ubuntu image.
3. Start een container en open een interactieve shell.
4. Installeer een extra programma (bijv. curl) binnen de container.
5. Sluit de container af en commit de wijzigingen in een nieuwe image.
6. Bekijk de nieuw gemaakte image.

## Oefening 4: Een eenvoudige Dockerfile maken
1. Maak een nieuwe map.
2. Maak een bestand Dockerfile met de volgende inhoud:
```Dockerfile
# Basisimage
FROM alpine:latest

# Voegt een tekstbestand toe
RUN echo "Hallo, Docker!" > /hallo.txt

# Start de container met een bericht
CMD ["cat", "/hallo.txt"]
```
3. Bouw de image.
4. Start een container met de nieuwe image.

## Oefening 5: Webserver bouwen met Dockerfile
1. Maak een nieuwe Dockerfile voor een eenvoudige webserver:
```Dockerfile
FROM nginx
COPY index.html /usr/share/nginx/html/
```
2. Maak een index.html bestand in dezelfde map:
```HTML
<html>
<body>
    <h1>Welkom bij mijn Docker Webserver!</h1>
</body>
</html>
```
3. Bouw de Docker image.
4. Start de container en exposeer poort 8080.
5. Open http://localhost:8080 in je browser en controleer of je webpagina zichtbaar is.

