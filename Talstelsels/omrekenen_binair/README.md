# Talstelsels omrekenen naar binair

## 1. Decimaal naar binair

Het **binaire talstelsel** gebruikt alleen de cijfers **0** en **1**. In dit systeem betekent **elke positie** een **macht van 2**. We kunnen een **decimaal getal** omzetten naar binair met behulp van **herhaalde deling door 2**.

### Methode: Deel herhaaldelijk door 2 en noteer de rest

1. **Deel het getal door 2** en noteer de **rest** (dit wordt een binair cijfer).
2. **Herhaal dit met het quotiënt** (de uitkomst van de deling) totdat je **0** bereikt.
3. De **binaire notatie lees je van onder naar boven**.


### Voorbeeld: Zet **23₁₀** om naar binair

We gebruiken **herhaalde deling door 2**:

| Stap | Deling   | Quotiënt | Rest (binaire cijfer) |
|------|---------|---------|------------------|
| 1    | 23 ÷ 2  | 11      | **1**            |
| 2    | 11 ÷ 2  | 5       | **1**            |
| 3    | 5 ÷ 2   | 2       | **1**            |
| 4    | 2 ÷ 2   | 1       | **0**            |
| 5    | 1 ÷ 2   | 0       | **1**            |

**Binaire weergave (lees van onder naar boven):**  
\[
23_{10} = 10111_2
\]

### Voorbeeld: Zet **45₁₀** om naar binair

| Stap | Deling   | Quotiënt | Rest (binaire cijfer) |
|------|---------|---------|------------------|
| 1    | 45 ÷ 2  | 22      | **1**            |
| 2    | 22 ÷ 2  | 11      | **0**            |
| 3    | 11 ÷ 2  | 5       | **1**            |
| 4    | 5 ÷ 2   | 2       | **1**            |
| 5    | 2 ÷ 2   | 1       | **0**            |
| 6    | 1 ÷ 2   | 0       | **1**            |

**Binaire weergave (lees van onder naar boven):**  
\[
45_{10} = 101101_2
\]

---

## 2. Octaal naar Binair

Er is een **snelle methode** om octale (**₈**) en hexadecimale (**₁₆**) getallen om te zetten naar binair (**₂**) zonder te delen door 2. Dit werkt door **elk cijfer te vervangen door een vaste binaire groep**.

In het **octaal** talstelsel komt elk octaal cijfer **(0-7)** overeen met exact 3 binaire cijfers.

| Octaal | Binair |
|--------|--------|
| 0₈     | 000₂  |
| 1₈     | 001₂  |
| 2₈     | 010₂  |
| 3₈     | 011₂  |
| 4₈     | 100₂  |
| 5₈     | 101₂  |
| 6₈     | 110₂  |
| 7₈     | 111₂  |

**Voorbeeld:** Zet **247₈** om naar binair.

1. Schrijf elk cijfer om naar 3 binaire cijfers:
   - **2₈** → **010₂**
   - **4₈** → **100₂**
   - **7₈** → **111₂**

2. Plak alles aan elkaar:
   \[
   247₈ = 010100111₂
   \]


---

## 3. Hexadecimaal naar binair

In het **hexadecimaal** talstelsel komt elk hexadecimaal cijfer **(0-9, A-F)** overeen met exact 4 binaire cijfers.

| Hexadecimaal | Binair |
|-------------|--------|
| 0₁₆        | 0000₂  |
| 1₁₆        | 0001₂  |
| 2₁₆        | 0010₂  |
| 3₁₆        | 0011₂  |
| 4₁₆        | 0100₂  |
| 5₁₆        | 0101₂  |
| 6₁₆        | 0110₂  |
| 7₁₆        | 0111₂  |
| 8₁₆        | 1000₂  |
| 9₁₆        | 1001₂  |
| A₁₆ (10)   | 1010₂  |
| B₁₆ (11)   | 1011₂  |
| C₁₆ (12)   | 1100₂  |
| D₁₆ (13)   | 1101₂  |
| E₁₆ (14)   | 1110₂  |
| F₁₆ (15)   | 1111₂  |

**Voorbeeld:** Zet **3F₂₁₆** om naar binair.

1. Schrijf elk cijfer om naar 4 binaire cijfers:
   - **3₁₆** → **0011₂**
   - **F₁₆ (15)** → **1111₂**
   - **2₁₆** → **0010₂**

2. Plak alles aan elkaar:
   \[
   3F2₁₆ = 001111110010₂
   \]