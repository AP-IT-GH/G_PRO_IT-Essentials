# Labo-06: Werken met bestanden in Linux

### Leerstof
- [Gebruikers en Groepen](/Linux/gebruikers.md)
- [Rechten](/Linux/rechten.md)

--- 

## Oefening 1: Het Geheime Gilde van Gebruikers 🧙‍♂️
Je wordt ingewijd als systeembeheerder in het Geheime Gilde. Je eerste taak is het aanmaken en beheren van nieuwe leden.

**Stap 1: Een nieuwe gebruiker aanmaken**
1. Maak een nieuwe gebruiker `arthur` aan.
   ```bash
   sudo adduser arthur
   ```

2. Stel een wachtwoord in voor `arthur`.
   ```bash
   sudo passwd arthur
   ```

3. Bekijk de gegevens van `arthur` in het systeem.
   ```bash
   id arthur
   ```

**Stap 2: De gebruikerslijst verkennen**
1. Open het bestand waarin alle gebruikers staan geregistreerd.
   ```bash
   cat /etc/passwd
   ```

2. Filter enkel de gebruikers die een home directory hebben onder `/home`.
   ```bash
   grep "/home" /etc/passwd
   ```

---

## Oefening 2: De Orde van de Groepen 🛡️
Je bent aangesteld als groepsbeheerder en moet gebruikers op de juiste plaats in de Orde zetten.

**Stap 1: Groepen aanmaken**
1. Maak een groep `ridders` aan.
   ```bash
   sudo groupadd ridders
   ```

2. Maak een tweede groep `tovernaars`.
   ```bash
   sudo groupadd tovernaars
   ```

**Stap 2: Gebruikers toevoegen aan groepen**
1. Voeg `arthur` toe aan de groep `ridders`.
   ```bash
   sudo usermod -aG ridders arthur
   ```

2. Controleer of `arthur` in de juiste groepen zit.
   ```bash
   groups arthur
   ```

**Stap 3: Ledenlijst van een groep bekijken**
1. Open het bestand met de groepsinformatie.
   ```bash
   cat /etc/group
   ```

2. Zoek naar alle gebruikers in de groep `ridders`.
   ```bash
   grep "ridders" /etc/group
   ```

---

## Oefening 3: Missie Superuser 🚀
In deze missie leer je commando’s uitvoeren met verhoogde rechten en van identiteit wisselen.

**Stap 1: Beheerrechten gebruiken**
1. Installeer software (zoals `htop`) met rootrechten.
   ```bash
   sudo apt install htop
   ```

2. Bekijk systeemprocessen als superuser.
   ```bash
   sudo htop
   ```

**Stap 2: Switchen van gebruiker**
1. Wissel naar gebruiker `arthur`.
   ```bash
   su arthur
   ```

2. Maak als `arthur` een bestand aan in zijn home directory.
   ```bash
   touch ~/arthur_verslag.txt
   ```

3. Ga terug naar je eigen gebruiker (typ `exit` in de shell).
   ```bash
   exit
   ```

**Stap 3: Voer een commando uit als `arthur` zonder te wisselen**
1. Bekijk de bestanden in zijn home-directory als jezelf.
   ```bash
   sudo -u arthur ls /home/arthur
   ```

## Oefening 4: The Avengers Assemble! 🦸‍♂️🦸‍♀️  
Je bent door Nick Fury aangesteld als systeembeheerder van de Avengers Tower. Je taak is om de Avengers correct in te delen in hun teams en toegang te geven tot hun gedeelde bestanden.

**Stap 1: Teams aanmaken**

Nick wil dat de teams netjes gescheiden zijn per specialiteit.

1. Maak een groep `tech` voor de technologisch onderlegde helden:
   ```bash
   sudo groupadd tech
   ```

2. Maak een groep `magic` voor magisch getrainde helden:
   ```bash
   sudo groupadd magic
   ```

3. Maak een groep `combat` voor helden met gevechtsskills:
   ```bash
   sudo groupadd combat
   ```

**Stap 2: Helden toevoegen aan hun team**

1. Voeg **tony** toe aan `tech`:
   ```bash
   sudo usermod -aG tech tony
   ```

2. Voeg **stephen** toe aan `magic`:
   ```bash
   sudo usermod -aG magic stephen
   ```

3. Voeg **natasha** toe aan `combat`:
   ```bash
   sudo usermod -aG combat natasha
   ```

4. Voeg **peter** toe aan zowel `tech` als `combat`:
   ```bash
   sudo usermod -aG tech,combat peter
   ```

**Stap 3: Controleren of het team compleet is**

1. Bekijk de groepen van **peter**:
   ```bash
   groups peter
   ```

2. Zoek alle leden van het `tech` team op:
   ```bash
   grep "tech" /etc/group
   ```

**Stap 4: Avengers-bestanden beveiligen**

1. Maak een map aan voor technologische bestanden:
   ```bash
   sudo mkdir /home/avengers/techfiles
   ```

2. Wijs de map toe aan de groep `tech`:
   ```bash
   sudo chown :tech /home/avengers/techfiles
   ```

3. Sta enkel groepsleden toe om deze map te lezen en schrijven:
   ```bash
   sudo chmod 770 /home/avengers/techfiles
   ```

---

## Oefening 5: The Batcave Protocols 🦇  
Batman heeft jouw hulp nodig om de Batcave digitaal te beveiligen. Elke held krijgt specifieke rechten in hun eigen domein.

**Stap 1: Groepen voor de Batfamilie**

1. Maak een groep `detectives` aan voor Batman en Robin:
   ```bash
   sudo groupadd detectives
   ```

2. Maak een groep `gadgets` aan voor Lucius Fox:
   ```bash
   sudo groupadd gadgets
   ```

3. Maak een groep `vigilantes` aan voor Nightwing en Batgirl:
   ```bash
   sudo groupadd vigilantes
   ```

**Stap 2: Gebruikers toevoegen aan groepen**

1. Voeg **bruce** toe aan `detectives`:
   ```bash
   sudo usermod -aG detectives bruce
   ```

2. Voeg **tim** toe aan `detectives`:
   ```bash
   sudo usermod -aG detectives tim
   ```

3. Voeg **lucius** toe aan `gadgets`:
   ```bash
   sudo usermod -aG gadgets lucius
   ```

4. Voeg **barbara** en **dick** toe aan `vigilantes`:
   ```bash
   sudo usermod -aG vigilantes barbara
   sudo usermod -aG vigilantes dick
   ```

**Stap 3: Mappen aanmaken en beveiligen**

1. Maak de map `/batcave/dossiers` en stel `detectives` in als groepseigenaar:
   ```bash
   sudo mkdir -p /batcave/dossiers
   sudo chown :detectives /batcave/dossiers
   sudo chmod 770 /batcave/dossiers
   ```

2. Maak de map `/batcave/lab` voor `gadgets`:
   ```bash
   sudo mkdir -p /batcave/lab
   sudo chown :gadgets /batcave/lab
   sudo chmod 770 /batcave/lab
   ```

3. Maak de map `/batcave/training` voor `vigilantes`:
   ```bash
   sudo mkdir -p /batcave/training
   sudo chown :vigilantes /batcave/training
   sudo chmod 770 /batcave/training
   ```
