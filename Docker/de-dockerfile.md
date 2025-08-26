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


