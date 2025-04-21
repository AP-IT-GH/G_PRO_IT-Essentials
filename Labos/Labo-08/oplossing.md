# Labo-09: Archiveren, Comprimeren, Processen

### Leerstof
- [Archieven en compressie](/Linux/archieven-en-compressie.md)
- [processen](/Linux/processen.md)

--- 

## Oefening 1: The Penguin's Encrypted Files 🐧
De Penguin heeft cruciale bestanden verstopt en versleuteld in een complexe mappenstructuur. Het is aan jou om ze te archiveren en comprimeren zodat Batman ze kan decoderen.
**Stap 1: Voorbereiding van de bestanden**
1. Maak een mapstructuur voor de bestanden:
```bash
mkdir -p ~/penguin/secrets ~/penguin/backups
```

2. Voeg enkele voorbeeldbestanden toe aan de map secrets:
```bash
echo "Top Secret Info 1" > ~/penguin/secrets/info1.txt
echo "Top Secret Info 2" > ~/penguin/secrets/info2.txt
echo "Top Secret Info 3" > ~/penguin/secrets/info3.txt
```

**Stap 2: Archiveren**
1. Archiveer alle bestanden in de map secrets:
```bash
tar -cvf ~/penguin/secrets.tar ~/penguin/secrets
```

2. Controleer de inhoud van het archief:
```bash
tar -tvf ~/penguin/secrets.tar
```

**Stap 3: Comprimeren**
1. Comprimeer het archief met gzip:
```bash
gzip ~/penguin/secrets.tar
```

2. Controleer de nieuwe gecomprimeerde bestandsgrootte:
```bash
ls -lh ~/penguin/secrets.tar.gz
```

**Stap 4: Extractie en verificatie**
1. Pak het gecomprimeerde bestand uit:
```bash
gunzip ~/penguin/secrets.tar.gz
tar -xvf ~/penguin/secrets.tar -C ~/penguin/backups
```

2. Controleer of alle bestanden correct zijn hersteld:
```bash
ls -l ~/penguin/backups/secrets
```

## Oefening 2: Joker's Encrypted Laughter 🎭
The Joker heeft chaotische bestanden verspreid die dringend moeten worden samengevoegd en beveiligd in één compacte bundle. Gebruik je archiverings- en compressievaardigheden om Gotham veiliger te maken.

**Stap 1: Voorbereiding van de bestanden**
1. Maak een mapstructuur voor de bestanden:
```bash
mkdir -p ~/joker/laughter ~/joker/storage
```

2. Voeg enkele voorbeeldbestanden toe aan de map laughter:
```bash
echo "Ha Ha Ha 1" > ~/joker/laughter/laugh1.txt
echo "Ha Ha Ha 2" > ~/joker/laughter/laugh2.txt
echo "Ha Ha Ha 3" > ~/joker/laughter/laugh3.txt
```

**Stap 2: Archiveren en comprimeren tegelijkertijd**
1. Archiveer en comprimeer de map laughter direct in één bestand:
```bash
tar -czvf ~/joker/laughter.tar.gz ~/joker/laughter
```
- `-c`: Creëert een nieuw archief.
- `-z`: Past gzip-compressie toe.
- `-v`: Toont gedetailleerde output tijdens de uitvoering.
- `-f`: Bepaalt de naam van het uitvoerbestand.

2. Controleer de inhoud van het gecomprimeerde archief:
```bash
tar -tzvf ~/joker/laughter.tar.gz
```

**Stap 3: Extractie en verificatie**
1. Pak het gecomprimeerde archief uit naar de map storage:
```bash
tar -xzvf ~/joker/laughter.tar.gz -C ~/joker/storage
```

2. Controleer of de bestanden correct zijn hersteld:
```bash
ls -l ~/joker/storage/laughter
```

## Oefening 3: Two-Face’s Split Processes ⚖️
Two-Face heeft de macht over het systeem en voert dubbel zoveel processen uit als normaal. Jouw missie is om de systeemprestaties te bewaken en de gevaarlijke processen te beëindigen.

**Stap 1: Lijst van actieve processen**
1. Toon alle actieve processen op het systeem:
```bash
ps -aux
```

2. Gebruik top om processen in real-time te bekijken:
```bash
top
```

**Stap 2: Identificeer verdachte processen**
1 Zoek processen van een specifieke gebruiker (bijvoorbeeld harvey):
```bash
ps -u harvey
```

2. Filter processen op naam, zoals malicious_script:
```bash
ps -aux | grep malicious_script
```

**Stap 3: Prioriteiten beheren**
1. Verhoog de prioriteit van een proces met renice. Gebruik de proces-ID (PID):
```bash
sudo renice -n -5 -p <PID>
```

2. Verlaag de prioriteit van een proces:
```bash
sudo renice -n 10 -p <PID>
```

**Stap 4: Een proces beëindigen**
1. Beëindig een specifiek proces met de kill-command:
```bash
sudo kill <PID>
```

2. Gebruik kill met een sterker signaal (bijvoorbeeld SIGKILL):
```bash
sudo kill -9 <PID>
```

**Stap 5: Resourcegebruik monitoren**
1. Controleer het CPU-gebruik per proces:
```bash
top
```

2. Gebruik htop (indien geïnstalleerd) voor een meer intuïtieve weergave:
```bash
htop
```