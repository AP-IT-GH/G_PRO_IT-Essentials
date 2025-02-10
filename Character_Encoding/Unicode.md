# Hoeveel bytes gebruikt een Unicode-karakter?

Je kunt bepalen hoeveel **bytes** een karakter nodig heeft in **UTF-8**, **UTF-16**, en **UTF-32** op basis van de Unicode codepoint.


## Wat is een Unicode codepoint?

Een **codepoint** is een unieke numerieke waarde die een specifiek karakter in de Unicode-standaard vertegenwoordigt. 
Codepoints worden genoteerd in de vorm `U+XXXX`, waarbij `XXXX` de hexadecimale waarde van het karakter is.

**Voorbeeld codepoints:**
- De letter **A** heeft codepoint `U+0041`.
- De letter **é** heeft codepoint `U+00E9`.
- Het euro-teken **€** heeft codepoint `U+20AC`.
- De emoji **😃** heeft codepoint `U+1F603`.

Elke Unicode-codepoint wordt vervolgens omgezet naar een binaire representatie in een bepaalde encoding zoals UTF-8, UTF-16 of UTF-32.



## Hoe werkt UTF-8?
UTF-8 is een **variabele-lengte encoding**, wat betekent dat een karakter tussen **1 en 4 bytes** kan gebruiken, afhankelijk van de Unicode codepoint.

| Codepoint Bereik     | Benodigde Bytes | Binaire structuur |
|----------------------|----------------|-------------------|
| **U+0000 – U+007F**  | 1 byte         | `0xxxxxxx`        |
| **U+0080 – U+07FF**  | 2 bytes        | `110xxxxx 10xxxxxx` |
| **U+0800 – U+FFFF**  | 3 bytes        | `1110xxxx 10xxxxxx 10xxxxxx` |
| **U+10000 – U+10FFFF** | 4 bytes     | `11110xxx 10xxxxxx 10xxxxxx 10xxxxxx` |


## Hoe wordt een Unicode codepoint omgezet naar UTF-8?

De omzetting van een Unicode codepoint naar UTF-8 gebeurt via een set regels gebaseerd op het binaire patroon:

#### **Stap 1: Codepoint in binair omzetten**
Eerst wordt de Unicode codepoint omgezet naar een binaire waarde.

#### **Stap 2: Kijken naar het bereik van de codepoint**
Afhankelijk van de grootte van de codepoint, bepaalt men hoeveel bytes nodig zijn (zie tabel hierboven).

#### **Stap 3: Bytes invullen in het juiste patroon**
De binaire waarde wordt verdeeld over het juiste aantal bytes en ingevuld in het patroon:
- 1 byte: `0xxxxxxx`
- 2 bytes: `110xxxxx 10xxxxxx`
- 3 bytes: `1110xxxx 10xxxxxx 10xxxxxx`
- 4 bytes: `11110xxx 10xxxxxx 10xxxxxx 10xxxxxx`

**Voorbeeld:** Om het karakter `€` (U+20AC) om te zetten naar UTF-8:
1. `U+20AC` = `0010 0000 1010 1100` (binaire representatie)
2. Valt in het **3-byte bereik** (U+0800 – U+FFFF)
3. Vul in het patroon `1110xxxx 10xxxxxx 10xxxxxx`:
   - `11100010 10000010 10101100`
4. UTF-8 representatie = `E2 82 AC` (hexadecimaal)

## Hoe wordt UTF-8 omgezet naar een Unicode codepoint?

De omzetting van een UTF-8 bytevolgorde terug naar een Unicode codepoint gebeurt in omgekeerde stappen:

#### **Stap 1: Bepaal het aantal bytes**
Het eerste byte geeft aan hoeveel bytes het karakter gebruikt:
- `0xxxxxxx` → 1 byte
- `110xxxxx` → 2 bytes
- `1110xxxx` → 3 bytes
- `11110xxx` → 4 bytes

#### **Stap 2: Verwijder de UTF-8 headers**
De extra bits (zoals `110`, `1110`, `11110`) worden verwijderd en de resterende bits worden samengevoegd.

#### **Stap 3: Omzetten naar decimaal**
Het binaire getal wordt omgezet naar een decimale Unicode codepoint.

**Voorbeeld:** Om `E2 82 AC` terug om te zetten naar een Unicode codepoint:
1. **E2 82 AC** in binair:
   - `E2` → `11100010`
   - `82` → `10000010`
   - `AC` → `10101100`
2. Verwijder de headers (`1110`, `10`, `10`):
   - `0010 0000 1010 1100`
3. Zet om naar decimaal: **U+20AC** (euro-teken `€`).


## Hoeveel bytes gebruikt een karakter?
Je kunt de codepoint van een karakter controleren en vergelijken met de bovenstaande ranges om te bepalen hoeveel **bytes** er nodig zijn.

#### **Voorbeelden**
- **"A"** (U+0041) → valt in **U+0000 – U+007F** → **1 byte**
- **"é"** (U+00E9) → valt in **U+0080 – U+07FF** → **2 bytes**
- **"€"** (U+20AC) → valt in **U+0800 – U+FFFF** → **3 bytes**
- **"😃"** (U+1F603) → valt in **U+10000 – U+10FFFF** → **4 bytes**


## Hoe werkt dit voor UTF-16 en UTF-32?

**UTF-16** gebruikt **2 of 4 bytes per karakter**:
- **U+0000 – U+FFFF** → 2 bytes  
- **U+10000 – U+10FFFF** → 4 bytes (gebruik van surrogate pairs)  

**UTF-32** gebruikt **altijd 4 bytes** per karakter, ongeacht de codepoint.

