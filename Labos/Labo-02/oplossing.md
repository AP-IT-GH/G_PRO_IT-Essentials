# Labo-02: Character Encoding

### Leerstof
- Character Encoding

## Hulpbronnen
- [ASCI tabel](http://www.asciitabel.be/)

### Oefening 1: ASCII opzoeken

*Zoek de ASCII-code op voor de letter `Z`.*

- In de ASCII-tabel heeft `Z` de code: **90** (decimaal) of **`0x5A`** (hexadecimaal)

*Zoek het karakter op dat hoort bij ASCII-code `64`.*

- ASCII-code **64** komt overeen met het karakter: **`@`**

### Oefening 2: Unicode codepoint naar UTF-8

*Zet de codepoint `U+00A9` (©) om naar UTF-8.*
1. `U+00A9` in binair: `0000 0000 1010 1001`
2. Valt in het **2-byte bereik** (`U+0080 – U+07FF`): `110xxxxx 10xxxxxx`
3. Invullen van het patroon:
   - `11000010 10101001`
4. UTF-8 representatie = **`C2 A9`**

*Zet de codepoint `U+03C0` (π) om naar UTF-8.*
1. `U+03C0` in binair: `0000 0011 1100 0000`
2. Valt in het **2-byte bereik** (`U+0080 – U+07FF`): `110xxxxx 10xxxxxx`
3. Invullen van het patroon:
   - `11001111 10000000`
4. UTF-8 representatie = **`CF 80`**

*Zet de codepoint `U+1F600` (😀) om naar UTF-8.*
1. `U+1F600` in binair: `0001 1111 0110 0000 0000`
2. Valt in het **4-byte bereik** (`U+10000 – U+10FFFF`): `11110xxx 10xxxxxx 10xxxxxx 10xxxxxx`
3. Invullen van het patroon:
   - `11110000 10011111 10011000 10000000`
4. UTF-8 representatie = **`F0 9F 98 80`**

### Oefening 3: UTF-8 naar Unicode codepoint

*Zet de UTF-8 bytevolgorde `C3 A9` om naar een Unicode codepoint.*
1. `C3 A9` in binair:
   - `C3` → `11000011`
   - `A9` → `10101001`
2. Verwijder de headers (`110` en `10`): `0000 0000 1110 1001`
3. Omgezet naar hexadecimaal: **U+00E9** (é)

*Zet de UTF-8 bytevolgorde `E2 98 83` om naar een Unicode codepoint.*
1. `E2 98 83` in binair:
   - `E2` → `11100010`
   - `98` → `10011000`
   - `83` → `10000011`
2. Verwijder de headers (`1110`, `10`, `10`): `0010 0110 0000 0011`
3. Omgezet naar hexadecimaal: **U+2603** (☃ sneeuwpop)

*Zet de UTF-8 bytevolgorde `F0 9F 92 A9` om naar een Unicode codepoint.*
1. `F0 9F 92 A9` in binair:
   - `F0` → `11110000`
   - `9F` → `10011111`
   - `92` → `10010010`
   - `A9` → `10101001`
2. Verwijder de headers (`11110`, `10`, `10`, `10`): `0001 1111 1001 0010 1010 1001`
3. Omgezet naar hexadecimaal: **U+1F4A9** (💩)






## Oplossingen voor de oefeningen

### 1. Unicode codepoint naar UTF-8

#### **Oefening 1: U+00A9 (©) naar UTF-8**
1. `U+00A9` in binair: `0000 0000 1010 1001`
2. Valt in het **2-byte bereik** (`U+0080 – U+07FF`): `110xxxxx 10xxxxxx`
3. Invullen van het patroon:
   - `11000010 10101001`
4. UTF-8 representatie = **`C2 A9`**

#### **Oefening 2: U+03C0 (π) naar UTF-8**
1. `U+03C0` in binair: `0000 0011 1100 0000`
2. Valt in het **2-byte bereik** (`U+0080 – U+07FF`): `110xxxxx 10xxxxxx`
3. Invullen van het patroon:
   - `11001111 10000000`
4. UTF-8 representatie = **`CF 80`**

#### **Oefening 3: U+1F600 (😀) naar UTF-8**
1. `U+1F600` in binair: `0001 1111 0110 0000 0000`
2. Valt in het **4-byte bereik** (`U+10000 – U+10FFFF`): `11110xxx 10xxxxxx 10xxxxxx 10xxxxxx`
3. Invullen van het patroon:
   - `11110000 10011111 10011000 10000000`
4. UTF-8 representatie = **`F0 9F 98 80`**

---

### 2. UTF-8 naar Unicode codepoint

#### **Oefening 4: `C3 A9` naar Unicode codepoint**
1. `C3 A9` in binair:
   - `C3` → `11000011`
   - `A9` → `10101001`
2. Verwijder de headers (`110` en `10`): `0000 0000 1110 1001`
3. Omgezet naar hexadecimaal: **U+00E9** (é)

#### **Oefening 5: `E2 98 83` naar Unicode codepoint**
1. `E2 98 83` in binair:
   - `E2` → `11100010`
   - `98` → `10011000`
   - `83` → `10000011`
2. Verwijder de headers (`1110`, `10`, `10`): `0010 0110 0000 0011`
3. Omgezet naar hexadecimaal: **U+2603** (☃ sneeuwpop)

#### **Oefening 6: `F0 9F 92 A9` naar Unicode codepoint**
1. `F0 9F 92 A9` in binair:
   - `F0` → `11110000`
   - `9F` → `10011111`
   - `92` → `10010010`
   - `A9` → `10101001`
2. Verwijder de headers (`11110`, `10`, `10`, `10`): `0001 1111 1001 0010 1010 1001`
3. Omgezet naar hexadecimaal: **U+1F4A9** (💩)

