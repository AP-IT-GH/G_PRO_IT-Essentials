# Labo-05: Linux Folderstructuur & Navigatie

### Leerstof
- [Het foldersysteem in Linux en navigeren met tekstcommando’s](/Linux/navigeren.md)

## Oefening 1: De schatzoektocht van Kapitein Linux 🏴‍☠️
Je helpt Kapitein Linux bij het organiseren van zijn schip, het zoeken naar een schat en het beschermen van de buit. Onderweg oefen je met het maken, verplaatsen, kopiëren en verwijderen van bestanden en mappen.

---

### **Stap 1: De wereld opzetten**
1. Maak een nieuwe map aan waarin het avontuur zich zal afspelen. Geef deze map de naam: `kapitein_linux_schatzoektocht`.

   **Oplossing:**
   ```bash
   mkdir kapitein_linux_schatzoektocht
   ```

2. Ga naar deze map.

   **Oplossing:**
   ```bash
   cd kapitein_linux_schatzoektocht
   ```

3. Binnen deze map maak je de volgende objecten (bestanden) aan:
    - Een fles met een schatkaart
    - Het kapiteinslogboek
    - Een schatkaart
    - Een kompas
    - Een zwaard
    - Een voorraad kanonkogels
    - Een zak goudstukken
    - Een kist met juwelen
    - Een lege kist
    - Een legendarische schatkist

   **Oplossing:**
   ```bash
   touch fles_met_kaart kapiteins_logboek schatkaart kompas zwaard kanonkogels goudstukken juwelen kist_lege schatkist_legendarisch
   ```

4. Maak daarnaast de volgende locaties (mappen) aan waar objecten kunnen worden opgeslagen:
    - Een schip waarin de bemanning leeft
    - Een kajuit waar de kapitein belangrijke documenten bewaart
    - Een dek waarop navigatie-instrumenten worden geplaatst
    - Een wapenopslag waar gevechtsmateriaal wordt bewaard
    - Een eiland waar later een schat ontdekt wordt
    - Een schuilplaats die kan worden gebruikt om spullen te verbergen
    - Een schatkamer waar de buit wordt opgeborgen

   **Oplossing:**
   ```bash
   mkdir schip kajuit dek wapenopslag eiland schuilplaats schatkamer
   ```

---

### **Stap 2: Het schip organiseren**
1. Verplaats het kapiteinslogboek en de schatkaart naar de kajuit.
   
   **Oplossing:**
   ```bash
   mv kapiteins_logboek schatkaart kajuit/
   ```

2. Berg het zwaard en de kanonkogels op in de wapenopslag.
   
   **Oplossing:**
   ```bash
   mv zwaard kanonkogels wapenopslag/
   ```

3. Plaats het kompas op het dek.
   
   **Oplossing:**
   ```bash
   mv kompas dek/
   ```

4. De kapitein gooit een fles met een schatkaart overboord. Deze spoelt aan op het eiland. Zorg dat de fles zich in de map eiland bevindt.
   
   **Oplossing:**
   ```bash
   mv fles_met_kaart eiland/
   ```

5. Controleer of alles correct is verplaatst door de inhoud van de mappen te bekijken.
   
   **Oplossing:**
   ```bash
   ls kajuit wapenopslag dek eiland
   ```

---

### **Stap 3: De zoektocht naar de schat**
1. De bemanning vindt de fles met de schatkaart op het eiland en brengt deze terug naar de kajuit.
   
   **Oplossing:**
   ```bash
   mv eiland/fles_met_kaart kajuit/
   ```

2. Na een lange zoektocht vinden ze een lege schatkist in een schuilplaats. Verplaats de lege kist naar de schuilplaats.
   
   **Oplossing:**
   ```bash
   mv kist_lege schuilplaats/
   ```

3. Na verder zoeken ontdekken ze een legendarische schatkist in een verborgen ruimte. Berg deze kist op in de schatkamer.
   
   **Oplossing:**
   ```bash
   mv schatkist_legendarisch schatkamer/
   ```

4. Controleer of de schatkist correct in de schatkamer staat.
   
   **Oplossing:**
   ```bash
   ls schatkamer
   ```

---

### **Stap 4: De buit verzamelen**
1. De kapitein bergt de waardevolle spullen op. Verplaats de goudstukken en juwelen naar de schatkamer.
   
   **Oplossing:**
   ```bash
   mv goudstukken juwelen schatkamer/
   ```

2. Voor de veiligheid wordt een deel van de buit ook in de kajuit bewaard. Maak een kopie van de goudstukken en juwelen en plaats deze in de kajuit.
   
   **Oplossing:**
   ```bash
   cp schatkamer/goudstukken schatkamer/juwelen kajuit/
   ```

3. Controleer of de buit correct is verdeeld.
   
   **Oplossing:**
   ```bash
   ls schatkamer kajuit
   ```

---

### **Stap 5: Gevaar loert!**
1. Een vijandelijk schip nadert! De kapitein bereidt zich voor op een gevecht. Verplaats de kanonkogels uit de wapenopslag naar het dek.
   
   **Oplossing:**
   ```bash
   mv wapenopslag/kanonkogels dek/
   ```

2. Om de vijand te misleiden wordt de lege schatkist vernietigd. Verwijder de lege kist uit de schuilplaats.
   
   **Oplossing:**
   ```bash
   rm schuilplaats/kist_lege
   ```

3. Controleer of de lege kist niet meer aanwezig is.
   
   **Oplossing:**
   ```bash
   ls schuilplaats
   ```

---

### **Stap 6: Laat de mapstructuur zien**
1. Om te controleren of je alle stappen correct hebt uitgevoerd, toon je de volledige folderstructuur. Gebruik een commando om een boomstructuur weer te geven van de map `kapitein_linux_schatzoektocht`.
   
   **Oplossing:**
   ```bash
   tree kapitein_linux_schatzoektocht
   
--- 

## Oefening 2: De keuken en kamer oefening 🏡
Je oefent met het maken, verplaatsen, kopiëren en verwijderen van bestanden en mappen door objecten in een huis te organiseren.

---

### **Stap 1: De structuur opzetten**
1. Maak een nieuwe map aan waarin de oefening zich zal afspelen. Geef deze map de naam: `mijn_huis`.
   
   **Oplossing:**
   ```bash
   mkdir mijn_huis
   ```

2. Ga naar deze map.
   
   **Oplossing:**
   ```bash
   cd mijn_huis
   ```

3. Binnen deze map maak je de volgende objecten (bestanden) aan:
    - appel
    - banaan
    - broek
    - brood
    - choco
    - hemd
    - kaas
    - melk
    - ontbijtgranen
    - pizza
    - sinaasappel
    - t-shirt

   **Oplossing:**
   ```bash
   touch appel banaan broek brood choco hemd kaas melk ontbijtgranen pizza sinaasappel t-shirt
   ```

4. Maak daarnaast de volgende locaties (mappen) aan waar objecten kunnen worden opgeslagen:
    - fruitschaal
    - keuken
    - keukenkast
    - kleerkast
    - koelkast
    - oven
    - slaapkamer

   **Oplossing:**
   ```bash
   mkdir fruitschaal keuken keukenkast kleerkast koelkast oven slaapkamer
   ```

---

### **Stap 2: De keuken organiseren**
1. Verplaats al het fruit (appel, banaan, sinaasappel) naar de fruitschaal en plaats de fruitschaal in de keuken.
   
   **Oplossing:**
   ```bash
   mv appel banaan sinaasappel fruitschaal/
   mv fruitschaal keuken/
   ```

2. Zet de oven in de keuken en plaats de pizza erin.
   
   **Oplossing:**
   ```bash
   mv oven keuken/
   mv pizza keuken/oven/
   ```

3. Zet de melk in de koelkast en plaats de koelkast in de keuken.
   
   **Oplossing:**
   ```bash
   mv melk koelkast/
   mv koelkast keuken/
   ```

4. Zet ook de kaas in de koelkast.
   
   **Oplossing:**
   ```bash
   mv kaas keuken/koelkast/
   ```

5. Verhuis de keukenkast naar de keuken en zorg dat deze de overige voedingswaren bevat (brood, choco, ontbijtgranen).
   
   **Oplossing:**
   ```bash
   mv brood choco ontbijtgranen keukenkast/
   mv keukenkast keuken/
   ```

---

### **Stap 3: De slaapkamer organiseren**
1. Zet de kleerkast in de slaapkamer en leg alle kleren (broek, hemd, t-shirt) in deze kast.
   
   **Oplossing:**
   ```bash
   mv kleerkast slaapkamer/
   mv broek hemd t-shirt slaapkamer/kleerkast/
   ```

---

### **Stap 4: Opruimen**
1. Na al dit werk is je pizza klaar en kan je deze opeten. Verwijder het pizza-bestand.
   
   **Oplossing:**
   ```bash
   rm keuken/oven/pizza
   ```

2. Controleer of de pizza correct is verwijderd.
   
   **Oplossing:**
   ```bash
   ls keuken/oven
   ```

---

### **Stap 5: Laat de mapstructuur zien**
1. Om te controleren of je alle stappen correct hebt uitgevoerd, toon je de volledige folderstructuur. Gebruik een commando om een boomstructuur weer te geven van de map `mijn_huis`.
   
   **Oplossing:**
   ```bash
   tree mijn_huis
   
