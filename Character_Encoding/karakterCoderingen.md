# Soorten Character Encoding

Laten we de meest voorkomende karakter coderingen **ASCII**, **Extended ASCII**, en **Unicode** eens in detail bekijken en de verschillen duidelijk uitleggen met een focus op het aantal bits, aantal karakters, ondersteunde talen en symbolen.



## 1. ASCII (American Standard Code for Information Interchange)
➡ De basis van character encoding.

| Eigenschap | Details                                                                                                       |
|---------------------|---------------------------------------------------------------------------------------------------------------|
| Aantal bits         | 7-bits (maar vaak opgeslagen als 8-bits)                                                                      |
| Aantal karakters    | 128 (0-127)                                                                                                   |
| Opslagruimte        | 1 byte per karakter                                                                                           |
| Ondersteunde tekens | Engelse letters (A-Z, a-z), cijfers (0-9), leestekens en enkele speciale controlekarakters (bijv. Enter, Tab) |
| Ondersteunde talen  | Alleen Engels                                                                                                 |

**🔹 Beperkingen:** ASCII kan geen accenten (é, ü, ñ) of andere talen weergeven.

**Voorbeeld ASCII tabel:**
A = 65, B = 66, C = 67
Spatie = 32, Enter = 13



## 2. Extended ASCII (ISO-8859-1, Windows-1252, etc.)
➡ Een uitbreiding van ASCII met extra symbolen.

| Eigenschap          | Details                                                                         |
|---------------------|---------------------------------------------------------------------------------|
| Aantal bits         | 8-bits                                                                          |
| Aantal karakters    | 256 (0-255)                                                                     |
| Opslagruimte        | 1 byte per karakter                                                             |
| Ondersteunde tekens | Extra symbolen zoals accenten (é, ü, ñ), valuta (€) en sommige grafische tekens |
| Ondersteunde talen  | Meerdere West-Europese talen zoals Frans, Duits, Spaans, Nederlands             |

**🔹 Beperkingen:**
- Slechts 256 karakters, wat niet genoeg is voor talen zoals Chinees, Arabisch, Russisch.
- Verschillende standaarden (ISO-8859-1, Windows-1252) leiden tot compatibiliteitsproblemen.

**Voorbeeld:** In Windows-1252, het euro-teken (€) heeft code 128, maar in een andere encoding kan dat een ander symbool zijn!



## 3. Unicode (UTF-8, UTF-16, UTF-32)
➡ De wereldwijde standaard voor alle talen en symbolen.

| Eigenschap          | Details                                                                            |
|---------------------|------------------------------------------------------------------------------------|
| Aantal bits         | Variabel (8, 16 of 32 bits afhankelijk van de encoding)                            |
| Aantal karakters    | 1.5 miljoen mogelijke codes (momenteel ~140.000 karakters gedefinieerd)            |
| Opslagruimte        | Afhankelijk van de Unicode-variant                                                 |
| Ondersteunde tekens | Alle talen, emoji’s, wetenschappelijke symbolen, hiërogliefen, braille             |
| Ondersteunde talen  | Wereldwijd alle talen, incl. Arabisch, Chinees, Japans, Russisch, Hindi, emoji’s 😃 |

### Unicode Varianten
Er zijn verschillende Unicode-encodings:

| Encoding | Opslag per karakter | Omschrijving                                                                            |
|----------|---------------------|-----------------------------------------------------------------------------------------|
| UTF-8    | 1 tot 4 bytes       | Populairst, gebruikt in websites en databases. Engels: 1 byte, andere tekens: 2-4 bytes |
| UTF-16   | 2 of 4 bytes        | Veel gebruikt in Windows & Java, minder efficiënt dan UTF-8 voor Engelse tekst          |
| UTF-32   | 4 bytes             | Simpel maar inefficiënt, omdat het altijd 4 bytes gebruikt, ook voor kleine tekens      |


**Voorbeeld Unicode tabel:**
A = U+0041 (65 in ASCII)
é = U+00E9 (233 in Extended ASCII)
😃 = U+1F603 (geen ASCII-equivalent!)

**🔹 Waarom is Unicode beter?**
- Alle talen ter wereld kunnen worden weergegeven.
- Emoji’s en symbolen worden ondersteund.
- Compatibel met ASCII, want UTF-8 gebruikt exact dezelfde codes voor 0-127 als ASCII.


**Welke moet je gebruiken?**
* Voor moderne applicaties en websites → gebruik altijd UTF-8!
* Als je met oude systemen werkt → let op de encoding (bijv. Windows-1252 of ISO-8859-1)
