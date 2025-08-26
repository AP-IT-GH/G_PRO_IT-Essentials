### Je eigen images publiceren

Wanneer we een eigen Docker-image maken kunnen we er voor kiezen om onze image te publiceren op een Docker registry, zoals Docker Hub, zodat anderen ze kunnen gebruiken. Om te tonen hoe dit in zijn werk gaat gebruiken we de image `mijn_nginx_site` die we zonet gemaakt hebben op basis van een Dockerfile.

##### Stap 1: Een Docker-image taggen (docker tag)
Wanneer je een image naar Docker Hub wilt uploaden, moet je deze correct taggen met een gebruikersnaam en repositorynaam.
De algemene structuur is:
```bash
docker tag <image> <gebruikersnaam>/<repository>:<versie>
```

Laten we onze `mijn_nginx_site` image taggen:
```bash
docker tag mijn_nginx_site jplectorap/nginx_site:v1
```

Wat gebeurt hier?
- `mijn_nginx_site` → Dit is de bronimage die we willen taggen.
- `jplectorap/nginx_site:v1` → Dit is de nieuwe naam van de image, inclusief een versienummer (v1).

Je kunt nu zien dat de image correct getagd is:
```bash
docker images
```

Dit zal een image tonen met de naam `jplectorap/nginx_site:v1`.

##### Stap 2: Inloggen op Docker Hub (docker login)
Voordat we de image naar Docker Hub kunnen uploaden, moeten we inloggen.
Gebruik het volgende commando:
```bash
docker login
```

Wat gebeurt hier?
- Docker vraagt om je Docker Hub-gebruikersnaam en wachtwoord.
- Na succesvolle login ben je verbonden met Docker Hub.

Als je ingelogd bent, kun je nu een image uploaden naar je repository.

##### Stap 3: Een Docker-image uploaden naar Docker Hub (docker push)
Nu gaan we de getagde image publiceren op Docker Hub.
```bash
docker push jplectorap/nginx_site:v1
```

Wat gebeurt hier?
- Docker uploadt de image naar Docker Hub.
- Iedereen kan deze image nu downloaden en gebruiken.

Je kunt controleren of de upload gelukt is door naar [hub.docker.com](hub.docker.com) te gaan en je repository te bekijken.

##### Stap 6: Overbodige images verwijderen
Indien je je image momenteel niet meer nodig hebt kan je er voor kieze de image lokaal te verwijderen aangezien je steeds weer opnieuw kan downloaden uit de Docker Hub.
```bash
docker rmi mijngebruikersnaam/nginx_site:v1
```

Wil je een image verwijderen uit Docker Hub? Ga naar [hub.docker.com](hub.docker.com), open je repository en verwijder de image handmatig.
