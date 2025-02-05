# Talstelsels omrekenen naar octaal en hexadecimaal

## 1. Decimaal naar octaal of heximaal
Om een **decimaal getal** om te zetten naar het **octale** (basis 8) of **hexadecimale** (basis 16) talstelsel, gebruiken we een **herhaalde deling**.

### Methode: Deel herhaaldelijk door de nieuwe basis en noteer de rest

1. **Deel het getal door de doelsysteem-basis** (8 voor octaal, 16 voor hexadecimaal).
2. **Noteer de rest** → dit wordt een cijfer in de nieuwe notatie.
3. **Herhaal dit met het quotiënt** (de uitkomst van de deling) totdat het **0** is.
4. **Lees het resultaat van onder naar boven**.

### Voorbeeld: Zet **156₁₀** om naar octaal (₈)

We gebruiken **herhaalde deling door 8**:

| Stap | Deling   | Quotiënt | Rest (octale cijfer) |
|------|---------|---------|------------------|
| 1    | 156 ÷ 8 | 19      | **4**            |
| 2    | 19 ÷ 8  | 2       | **3**            |
| 3    | 2 ÷ 8   | 0       | **2**            |

**Octale weergave (lees van onder naar boven):**  
\[
156_{10} = 234_8
\]

✅ **Snelle controle:**  
\[
2×8^2 + 3×8^1 + 4×8^0 = 156_{10}
\]  
Dus de berekening klopt!

### Voorbeeld: Zet **512₁₀** om naar hexadecimaal (₁₆)

We gebruiken **herhaalde deling door 16**:

| Stap | Deling   | Quotiënt | Rest (hex cijfer) |
|------|---------|---------|------------------|
| 1    | 512 ÷ 16 | 32      | **0**            |
| 2    | 32 ÷ 16  | 2       | **0**            |
| 3    | 2 ÷ 16   | 0       | **2**            |

**Hexadecimale weergave (lees van onder naar boven):**  
\[
512_{10} = 200_{16}
\]

✅ **Snelle controle:**  
\[
2×16^2 + 0×16^1 + 0×16^0 = 512_{10}
\]  
De berekening klopt!

---

### Samenvatting

| Omrekening  | Methode |
|------------|---------|
| **Decimaal → Octaal** | Deel herhaaldelijk door **8** en lees de resten van onder naar boven |
| **Decimaal → Hexadecimaal** | Deel herhaaldelijk door **16** en lees de resten van onder naar boven |


## 2. Binair naar octaal of hexadecimaal

Er is een **snelle methode** om een binair (₂) getal om te zetten naar **octaal (₈)** of **hexadecimaal (₁₆)** zonder ingewikkelde berekeningen. Dit werkt door de binaire cijfers in **groepen van 3 of 4** te splitsen.

**Elke groep van 3 binaire cijfers komt overeen met exact 1 octaal cijfer.**  

| Binair  | Octaal |
|---------|--------|
| 000₂    | 0₈    |
| 001₂    | 1₈    |
| 010₂    | 2₈    |
| 011₂    | 3₈    |
| 100₂    | 4₈    |
| 101₂    | 5₈    |
| 110₂    | 6₈    |
| 111₂    | 7₈    |

### Voorbeeld: Zet **101110₂** om naar octaal

**Stap 1:** Splits de binaire cijfers in groepen van **3**, beginnend van rechts.  
**(Als de groep niet compleet is, vul dan aan met nullen aan de linkerkant.)**

**Stap 2:** Vervang elke groep door het overeenkomstige octale cijfer:

| Binair  | Octaal |
|---------|--------|
| 101₂    | 5₈    |
| 110₂    | 6₈    |

\[
101110_2 = 56_8
\]

✅ **Snelle controle:**  
\[
5×8^1 + 6×8^0 = 40 + 6 = 46_{10}
\]  
De berekening klopt!


**Elke groep van 4 binaire cijfers komt overeen met exact 1 hexadecimaal cijfer.**  

| Binair  | Hexadecimaal |
|---------|-------------|
| 0000₂   | 0₁₆        |
| 0001₂   | 1₁₆        |
| 0010₂   | 2₁₆        |
| 0011₂   | 3₁₆        |
| 0100₂   | 4₁₆        |
| 0101₂   | 5₁₆        |
| 0110₂   | 6₁₆        |
| 0111₂   | 7₁₆        |
| 1000₂   | 8₁₆        |
| 1001₂   | 9₁₆        |
| 1010₂   | A₁₆        |
| 1011₂   | B₁₆        |
| 1100₂   | C₁₆        |
| 1101₂   | D₁₆        |
| 1110₂   | E₁₆        |
| 1111₂   | F₁₆        |

### Voorbeeld: Zet **11010110₂** om naar hexadecimaal

**Stap 1:** Splits de binaire cijfers in groepen van **4**, beginnend van rechts.  
**(Als de groep niet compleet is, vul dan aan met nullen aan de linkerkant.)**

**Stap 2:** Vervang elke groep door het overeenkomstige hexadecimale cijfer:

| Binair  | Hexadecimaal |
|---------|-------------|
| 1101₂   | D₁₆        |
| 0110₂   | 6₁₆        |

\[
11010110_2 = D6_{16}
\]

✅ **Snelle controle:**  
\[
D×16^1 + 6×16^0 = 13×16 + 6 = 208 + 6 = 214_{10}
\]  
De berekening klopt!

### Samenvatting
| Omrekening  | Methode |
|------------|---------|
| **Binair → Octaal** | Splits binaire getal in **groepen van 3** en vervang door octale cijfers |
| **Binair → Hexadecimaal** | Splits binaire getal in **groepen van 4** en vervang door hexadecimale cijfers |
