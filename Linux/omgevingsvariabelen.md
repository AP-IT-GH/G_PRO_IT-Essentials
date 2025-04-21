## Omgevingsvariabelen

Omgevingsvariabelen in een besturingssysteem zijn als kleine "settings" die programma's vertellen hoe ze zich moeten gedragen of waar ze bepaalde bestanden kunnen vinden. Je kunt ze zien als een soort van labels met bijbehorende waarden. Bijvoorbeeld, er is een variabele genaamd `USER` die je gebruikersnaam bevat, of `HOME` die aangeeft waar je persoonlijke bestanden liggen. Deze variabelen worden vaak door het systeem (en door programma’s) gebruikt om configuratiegegevens op te slaan.

Een van de belangrijkste omgevingsvariabelen is de `PATH`-variabele. Denk aan `PATH` als een lijst van mappen (of directories) waarin Linux zoekt naar programma’s als je een commando invoert in de terminal. Stel je voor dat je een commando zoals ls of python typt; de shell doorloopt de mappen die in de `PATH` variabele staan (gescheiden door een dubbele punt :) en zoekt daar naar een uitvoerbaar bestand met die naam. Dit maakt het mogelijk om commando’s zomaar in te typen zonder telkens de volledige padnaam te moeten typen.

### Hoe gebruik je omgevingsvariabelen in Linux?

##### Bekijken van de PATH-variabele
```bash
echo $PATH
```
Dit commando toont je huidige lijst van mappen waar Linux naar uitvoerbare bestanden zoekt.

##### Een tijdelijke wijziging aanbrengen
Als je een nieuwe map wilt toevoegen voor de huidige sessie (totdat je de terminal sluit), kun je de PATH variabele aanpassen met:
```bash
export PATH="/pad/naar/nieuwe/map:$PATH"
```

Wat hier gebeurt, is dat je de nieuwe map toevoegt aan het begin van de PATH-lijst. Als je liever de map aan het eind toevoegt, kun je schrijven:
```bash
export PATH="$PATH:/pad/naar/nieuwe/map"
```

Deze wijziging geldt alleen zolang de sessie open blijft.

##### Een permanente wijziging aanbrengen
Als je de wijziging wilt bewaren voor elke nieuwe sessie, moet je de exportregel toevoegen aan een configuratiebestand zoals `~/.bashrc`, `~/.bash_profile` of `~/.profile` (afhankelijk van welke shell je gebruikt). Open bijvoorbeeld `~/.bashrc` in een teksteditor en voeg de regel toe:
```bash
export PATH="$PATH:/pad/naar/nieuwe/map"
```

Sla het bestand op en laad de wijzigingen met:
```bash
source ~/.bashrc
```

Zo zal elke terminalsessie de aangepaste PATH variabele inladen.
