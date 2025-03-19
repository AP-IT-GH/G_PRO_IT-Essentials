# Labo-06: Werken met bestanden in Linux

### Leerstof
- [Werken met bestanden](/Linux/bestanden.md)
- [In- en output streams](/Linux/streams.md)

--- 

## Oefening 1: De Schatzoektocht van Kapitein Linux 🏴‍☠️
Je helpt Kapitein Linux bij het organiseren van zijn administratie, het analyseren van schatkaarten en het inventariseren van de buit. Onderweg oefen je met **het maken, vullen, sorteren en filteren van bestanden.**

**Stap 1: Het schip registreren**
1. Maak een nieuw bestand `bemanning.txt` waarin de namen van de bemanningsleden komen te staan.
2. Voeg handmatig de volgende bemanningsleden toe aan het bestand met `nano`:
   ```
   Kapitein Linux
   Eerste stuurman Jack
   Matroos Bob
   Matroos Anne
   Kanonnier Rick
   Navigator Sue
   ```
3. Controleer of de bemanningslijst correct is ingevuld.

**Stap 2: De schatkaart analyseren**
1. Maak een bestand `schatkaart.txt` waarin coördinaten van schatten worden bewaard.
2. Vul het bestand met de volgende schatlocaties:
   ```
   Eiland Noord; 45
   Eiland Zuid; 30
   Verborgen Baai; 70
   Oude Ruïne; 55
   Zandbank West; 20
   Legendarische Tempel; 100
   ```
3. Sorteer de schatten op **waarde** (nummer) in **oplopende volgorde**.
4. Sorteer de schatten op **waarde** in **aflopende volgorde**.

**Stap 3: De buit inventariseren**
1. Maak een bestand `schatkamer.txt` waarin de verzamelde schatten worden bijgehouden.
2. Vul het bestand met de volgende schatten en hun hoeveelheden:
   ```
   Goudstukken; 500
   Zilverstukken; 300
   Robijnen; 25
   Saffieren; 18
   Parelkettingen; 7
   Antieke munten; 50
   ```
3. Sorteer de buit op **waarde** (aantal stuks) in oplopende volgorde.
4. Toon alleen de **soort schatten** zonder aantallen.
5. Toon alleen de **aantallen**, gesorteerd van hoog naar laag.

**Stap 4: Een geheime code ontcijferen**
1. Maak een bestand `geheime_code.txt` en voeg de volgende tekst toe:
   ```
   X1B3 schat
   2J7Z verborgen
   4A9Y op
   8M2X eiland
   5K6V is
   9Q8W de
   ```
2. Filter alleen de **woorden** zonder de ruis.
3. Herschrijf de boodschap in de juiste volgorde:
   _"De schat is verborgen op het eiland."_


**Stap 5: Gevaar op zee!**
1. Een vijandelijk schip nadert en de kapitein wil snel een lijst van de bemanning met een "Matroos" filteren.
2. Controleer hoeveel bemanningsleden er in totaal zijn.
3. Kopieer de schatkaart en bewaar een back-up.
4. De kapitein beslist dat de schatkaart **vernietigd** moet worden. Verwijder het originele bestand.
5. Controleer of de schatkaart verdwenen is.


---

## Oefening 2: Tales of Middle Earth 🧙‍♂️
Je helpt de bibliothecarissen van Rivendell met het organiseren en analyseren van de historische geschriften over Middle-earth. Je zal werken met **bestanden, sorteren, filteren, het combineren van commando's met pipelines en het opslaan van resultaten met redirection.**

**Stap 1: De bibliotheek opzetten**
1. Maak een bestand `personages.txt` waarin belangrijke figuren uit Midden-aarde worden opgeslagen.
2. Vul het bestand met de volgende namen en hun rol:
   ```
   Gandalf;Wizard
   Aragorn;King
   Frodo;Hobbit
   Legolas;Elve
   Gimli;Dwarf
   Boromir;Human
   Samwise;Hobbit
   Saruman;Wizard
   Gollum;Creature
   Sauron;Dark Lord
   ```
3. Controleer of het bestand correct is opgeslagen.

**Stap 2: De kaart van Midden-aarde analyseren**
1. Maak een bestand `plaatsen.txt` met de belangrijkste locaties in Midden-aarde en hun gevaarsscore (van 1 tot 100).
2. Vul het bestand met de volgende locaties:
   ```
   Rivendell;10
   Mordor;100
   Gondor;50
   Rohan;40
   Moria;75
   Isengard;80
   The Shire;5
   ````
3. Toon alleen de eerste 3 gevaarlijkste plaatsen.
4. Toon de 2 minst gevaarlijke plaatsen.

**Stap 3: De Ringgenootschap analyseren**
1. Toon alleen de Hobbits uit het bestand `personages.txt`.
 ```
2. Tel het aantal personages in de lijst.
3. Sorteer de personages alfabetisch en sla het op in een nieuw bestand `personages_sorted.txt`.
4. Controleer of het bestand correct is opgeslagen.

**Stap 4: Het Boek van de Geschiedenis**
1. Maak een bestand `geschiedenis.txt` met de volgende tekst:
   ```
   One Ring to rule them all.
   One Ring to find them.
   One Ring to bring them all.
   And in the darkness bind them.
   ```
2. Toon alleen de eerste twee regels.
3. Toon alleen de laatste twee regels.
4. Tel het aantal woorden in de tekst.

**Stap 5: Gevaar in Midden-aarde!**
1. Filter de gevaarlijkste plaats uit `plaatsen.txt` en sla het resultaat op in `gevaarlijkste_plaats.txt`.
2. Controleer of het bestand correct is opgeslagen.
3. Combineer de informatie uit `gevaarlijkste_plaats.txt` en `personages.txt` in één bestand `gevaren_analyse.txt`.
4. Bekijk de inhoud van `gevaren_analyse.txt`.
