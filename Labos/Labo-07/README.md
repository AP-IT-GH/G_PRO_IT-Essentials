# Labo-06: Werken met bestanden in Linux

### Leerstof
- [Gebruikers en Groepen](/Linux/gebruikers.md)
- [Rechten](/Linux/rechten.md)

--- 

## Oefening 1: Het Geheime Gilde van Gebruikers 🧙‍♂️
Je wordt ingewijd als systeembeheerder in het Geheime Gilde. Je eerste taak is het aanmaken en beheren van nieuwe leden.

**Stap 1: Een nieuwe gebruiker aanmaken**
1. Maak een nieuwe gebruiker `arthur` aan.
2. Stel een wachtwoord in voor `arthur`.
3. Bekijk de gegevens van `arthur` in het systeem.

**Stap 2: De gebruikerslijst verkennen**
1. Open het bestand waarin alle gebruikers staan geregistreerd.
2. Filter enkel de gebruikers die een home directory hebben onder `/home`.

---

## Oefening 2: De Orde van de Groepen 🛡️
Je bent aangesteld als groepsbeheerder en moet gebruikers op de juiste plaats in de Orde zetten.

**Stap 1: Groepen aanmaken**
1. Maak een groep `ridders` aan.
2. Maak een tweede groep `tovernaars`.

**Stap 2: Gebruikers toevoegen aan groepen**
1. Voeg `arthur` toe aan de groep `ridders`.
2. Controleer of `arthur` in de juiste groepen zit.

**Stap 3: Ledenlijst van een groep bekijken**
1. Open het bestand met de groepsinformatie.
2. Zoek naar alle gebruikers in de groep `ridders`.

---

## Oefening 3: Missie Superuser 🚀
In deze missie leer je commando’s uitvoeren met verhoogde rechten en van identiteit wisselen.

**Stap 1: Beheerrechten gebruiken**
1. Installeer software (zoals `htop`) met rootrechten.
2. Bekijk systeemprocessen als superuser.

**Stap 2: Switchen van gebruiker**
1. Wissel naar gebruiker `arthur`.
2. Maak als `arthur` een bestand aan in zijn home directory.
3. Ga terug naar je eigen gebruiker (typ `exit` in de shell).

**Stap 3: Voer een commando uit als `arthur` zonder te wisselen**
1. Bekijk de bestanden in zijn home-directory als jezelf.

--- 

## Oefening 4: The Avengers Assemble! 🦸‍♂️🦸‍♀️  
Je bent door Nick Fury aangesteld als systeembeheerder van de Avengers Tower. Je taak is om de Avengers correct in te delen in hun teams en toegang te geven tot hun gedeelde bestanden.

**Stap 1: Teams aanmaken**

Nick wil dat de teams netjes gescheiden zijn per specialiteit.

1. Maak een groep `tech` voor de technologisch onderlegde helden:
2. Maak een groep `magic` voor magisch getrainde helden:
3. Maak een groep `combat` voor helden met gevechtsskills:

**Stap 2: Helden toevoegen aan hun team**

1. Voeg **tony** toe aan `tech`:
2. Voeg **stephen** toe aan `magic`:
3. Voeg **natasha** toe aan `combat`:
4. Voeg **peter** toe aan zowel `tech` als `combat`:

**Stap 3: Controleren of het team compleet is**

1. Bekijk de groepen van **peter**:
2. Zoek alle leden van het `tech` team op:

**Stap 4: Avengers-bestanden beveiligen**

1. Maak een map aan voor technologische bestanden:
2. Wijs de map toe aan de groep `tech`:
3. Sta enkel groepsleden toe om deze map te lezen en schrijven:

---

## Oefening 5: The Batcave Protocols 🦇  
Batman heeft jouw hulp nodig om de Batcave digitaal te beveiligen. Elke held krijgt specifieke rechten in hun eigen domein.

**Stap 1: Groepen voor de Batfamilie**

1. Maak een groep `detectives` aan voor Batman en Robin:
2. Maak een groep `gadgets` aan voor Lucius Fox:
3. Maak een groep `vigilantes` aan voor Nightwing en Batgirl:

**Stap 2: Gebruikers toevoegen aan groepen**

1. Voeg **bruce** toe aan `detectives`:
2. Voeg **tim** toe aan `detectives`:
3. Voeg **lucius** toe aan `gadgets`:
4. Voeg **barbara** en **dick** toe aan `vigilantes`:

**Stap 3: Mappen aanmaken en beveiligen**

1. Maak de map `/batcave/dossiers` en stel `detectives` in als groepseigenaar:
2. Maak de map `/batcave/lab` voor `gadgets`:
3. Maak de map `/batcave/training` voor `vigilantes`:
