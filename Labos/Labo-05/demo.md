## Demo: Linux Navigatie en Bestandsbeheer

Een demo die in de klas gegeven kan worden ter demonstratie van de basiscommando’s voor navigatie en bestandsbeheer in Linux, gebasseert op het werken met een typische website-folderstructuur.

---

### **Stap 1: De projectstructuur opzetten**
1. Maak een nieuwe map aan waarin we de demonstratie uitvoeren. Geef deze map de naam `website_project`.
   
   **Oplossing:**
   ```bash
   mkdir website_project
   ```

2. Ga naar deze map.
   
   **Oplossing:**
   ```bash
   cd website_project
   ```

3. Binnen deze map maak je de volgende bestanden aan:
    - `index.html` (de homepage van de website)
    - `about.html` (een over-ons pagina)
    - `contact.html` (een contactpagina)

   **Oplossing:**
   ```bash
   touch index.html about.html contact.html
   ```

4. Maak daarnaast de volgende mappen aan:
    - `css/` (voor stylesheets)
    - `js/` (voor JavaScript-bestanden)
    - `img/` (voor afbeeldingen)

   **Oplossing:**
   ```bash
   mkdir css js img
   ```

---

### **Stap 2: Bestanden organiseren**
1. Maak een CSS-bestand aan en verplaats het naar de `css/` map.
   
   **Oplossing:**
   ```bash
   touch styles.css
   mv styles.css css/
   ```

2. Maak een JavaScript-bestand aan en verplaats het naar de `js/` map.
   
   **Oplossing:**
   ```bash
   touch script.js
   mv script.js js/
   ```

3. Maak een logo-afbeelding en verplaats deze naar de `img/` map.
   
   **Oplossing:**
   ```bash
   touch logo.png
   mv logo.png img/
   ```

---

### **Stap 3: Bestanden kopiëren en back-uppen**
1. Maak een back-up van `index.html` en plaats deze in een nieuwe map `backup/`.
   
   **Oplossing:**
   ```bash
   mkdir backup
   cp index.html backup/
   ```

2. Maak een kopie van `styles.css` en plaats deze ook in de `backup/` map.
   
   **Oplossing:**
   ```bash
   cp css/styles.css backup/
   ```

---

### **Stap 4: Bestanden en mappen verwijderen**
1. Een onnodig testbestand (`test.html`) is per ongeluk aangemaakt en moet verwijderd worden.
   
   **Oplossing:**
   ```bash
   touch test.html
   rm test.html
   ```

2. Een lege map `old_files/` is niet meer nodig en kan verwijderd worden.
   
   **Oplossing:**
   ```bash
   mkdir old_files
   rmdir old_files
   ```

3. Een foutieve stylesheet in de `css/` map (`old_styles.css`) moet worden verwijderd.
   
   **Oplossing:**
   ```bash
   touch css/old_styles.css
   rm css/old_styles.css
   ```

---

### **Stap 5: Controle en visualisatie**
1. Controleer of alle bestanden correct zijn verplaatst.
   
   **Oplossing:**
   ```bash
   ls css js img backup
   ```

2. Toon de volledige mappenstructuur van `website_project`.
   
   **Oplossing:**
   ```bash
   tree website_project
   ```

---

### **Samenvatting van gebruikte commando’s**
| Commando | Beschrijving |
|----------|-------------|
| `pwd` | Toon de huidige locatie |
| `ls` | Toon de inhoud van een map |
| `cd` | Navigeer tussen mappen |
| `mkdir` | Maak een nieuwe map aan |
| `touch` | Maak een nieuw bestand aan |
| `rm` | Verwijder een bestand |
| `rmdir` | Verwijder een lege map |
| `mv` | Verplaats of hernoem een bestand/map |
| `cp` | Kopieer een bestand |
| `tree` | Toon de mappenstructuur |


