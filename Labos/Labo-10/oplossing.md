# Labo-10: Docker

### Leerstof
- [Docker](/Docker/README.md)

--- 

## Oefening 1: Een eenvoudige container starten
1. Start een nieuwe container gebaseerd op Alpine Linux en voer een interactief shell-commando uit:
```bash
docker run -it alpine /bin/sh
```
2. Controleer binnen de container welke bestanden en mappen aanwezig zijn met:
```bash
ls -l /
```
3. Sluit de container af met:
```
exit
```
4. Controleer de lijst van gestopte containers:
```
docker ps -a
```


## Oefening 2: Het beheren van containers
1. Start een Nginx-webserver container en exposeer poort 8080:
```bash
docker run -d -p 8080:80 nginx
```
2. Open een browser en ga naar http://localhost:8080 om te zien of de server draait.
3. Bekijk de actieve containers:
```bash
docker ps
```
3. Stop de container:
```bash
docker stop <container_id>
```
4. Start de container opnieuw:
```bash
docker start <container_id>
```
5. Verwijder de container volledig:
```
docker rm <container_id>
```

## Oefening 3: Een eigen image maken en beheren
1. Bekijk de lokaal beschikbare Docker images:
```bash
docker images
```
2. Download een Ubuntu image:
```bash
docker pull ubuntu
```
3. Start een container en open een interactieve shell:
```bash
docker run -it ubuntu /bin/bash
```
4. Installeer een extra programma (bijv. curl) binnen de container:
```bash
apt update && apt install curl -y
```
5. Sluit de container af en commit de wijzigingen in een nieuwe image:
```bash
docker commit <container_id> mijn_ubuntu_image
```
6. Bekijk de nieuw gemaakte image:
```bash
docker images
```

## Oefening 4: Een eenvoudige Dockerfile maken
1. Maak een nieuwe map:
```bash
mkdir mijn_docker_app && cd mijn_docker_app
```
2. Maak een bestand Dockerfile met de volgende inhoud:
```Dockerfile
# Basisimage
FROM alpine:latest

# Voegt een tekstbestand toe
RUN echo "Hallo, Docker!" > /hallo.txt

# Start de container met een bericht
CMD ["cat", "/hallo.txt"]
```
3. Bouw de image:
```bash
docker build -t mijn_alpine_app .
```
4. Start een container met de nieuwe image:
```bash
docker run mijn_alpine_app
```

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
3. Bouw de Docker image:
```bash
docker build -t mijn_nginx .
```
4. Start de container en exposeer poort 8080:
```bash
docker run -d -p 8080:80 mijn_nginx
```
5. Open http://localhost:8080 in je browser en controleer of je webpagina zichtbaar is.

