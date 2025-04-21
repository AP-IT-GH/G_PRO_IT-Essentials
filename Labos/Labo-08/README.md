# Labo-09: Archiveren, Comprimeren, Processen

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

## Oefening 3: Two-Face’s Split Processes ⚖️
Two-Face heeft de macht over het systeem en voert dubbel zoveel processen uit als normaal. Jouw missie is om de systeemprestaties te bewaken en de gevaarlijke processen te beëindigen.

**Stap 1: Lijst van actieve processen**
1. Toon alle actieve processen op het systeem.
2. Gebruik top om processen in real-time te bekijken.

**Stap 2: Identificeer verdachte processen**
1 Zoek processen van een specifieke gebruiker (bijvoorbeeld harvey).
2. Filter processen op naam, zoals malicious_script.

**Stap 3: Prioriteiten beheren**
1. Verhoog de prioriteit van een proces met renice. Gebruik de proces-ID (PID).
2. Verlaag de prioriteit van een proces.

**Stap 4: Een proces beëindigen**
1. Beëindig een specifiek proces met de kill-command.

2. Gebruik kill met een sterker signaal (bijvoorbeeld SIGKILL).

**Stap 5: Resourcegebruik monitoren**
1. Controleer het CPU-gebruik per proces.
2. Gebruik htop (indien geïnstalleerd) voor een meer intuïtieve weergave.