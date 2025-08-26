# Labo-08: Archiveren, Comprimeren, Processen

### Leerstof
- [Archieven en compressie](/Linux/archieven-en-compressie.md)
- [processen](/Linux/processen.md)

--- 

## Oefening 1: The Penguin's Encrypted Files 🐧
De Penguin heeft cruciale bestanden verstopt en versleuteld in een complexe mappenstructuur. Het is aan jou om ze te archiveren en comprimeren zodat Batman ze kan decoderen.
**Stap 1: Voorbereiding van de bestanden**
1. Maak een mapstructuur voor de bestanden.
2. Voeg enkele voorbeeldbestanden toe aan de map secrets.

**Stap 2: Archiveren**
1. Archiveer alle bestanden in de map secrets.
2. Controleer de inhoud van het archief.

**Stap 3: Comprimeren**
1. Comprimeer het archief met gzip.
2. Controleer de nieuwe gecomprimeerde bestandsgrootte.

**Stap 4: Extractie en verificatie**
1. Pak het gecomprimeerde bestand uit.
2. Controleer of alle bestanden correct zijn hersteld.

## Oefening 2: Joker's Encrypted Laughter 🎭
The Joker heeft chaotische bestanden verspreid die dringend moeten worden samengevoegd en beveiligd in één compacte bundle. Gebruik je archiverings- en compressievaardigheden om Gotham veiliger te maken.

**Stap 1: Voorbereiding van de bestanden**
1. Maak een mapstructuur voor de bestanden.
2. Voeg enkele voorbeeldbestanden toe aan de map laughter.

**Stap 2: Archiveren en comprimeren tegelijkertijd**
1. Archiveer en comprimeer de map laughter direct in één bestand.
2. Controleer de inhoud van het gecomprimeerde archief.

**Stap 3: Extractie en verificatie**
1. Pak het gecomprimeerde archief uit naar de map storage.
2. Controleer of de bestanden correct zijn hersteld.

## Oefening 3: The Riddler’s Endless Loop 🧩
De Riddler heeft een proces gestart dat constant berichten naar het systeem stuurt. Jouw taak is om het proces te identificeren, monitoren en correct te beëindigen.

**Stap 1: Aanmaken van verdacht proces**
1. Maak een bestand genaamd malicious_script.sh met de volgende inhoud:
```bash
#!/bin/bash
while true; do echo "Harvey is watching..."; sleep 10; done &
```
2. Zorg ervoor dat je het script kan uitvoeren.
3. Start het script met het volgende commando: 
```bash
./malicious_script.sh
```

**Stap 2: Identificeren van het proces**
1. Zoek het proces met `ps` en `grep`.

**Stap 3: Beëindigen van het proces**
1. Beëindig het proces met de `kill`-command.
2. Als het proces blijft lopen, forceer beëindiging.
3. Controleer of het proces correct is gestopt.