# Talstelsels omrekenen naar decimaal

## 1. Binair naar decimaal

Het **binaire talstelsel** gebruikt alleen de cijfers **0** en **1**. Elke positie stelt een macht van **2** voor. 

**Voorbeeld:** Zet het binaire getal **1011₂** om naar decimaal.

| Binaire cijfer | 1 | 0 | 1 | 1 |
|---------------|---|---|---|---|
| Macht van 2   | 2³ | 2² | 2¹ | 2⁰ |
| Berekening    | 1×8 | 0×4 | 1×2 | 1×1 |

### Stap 1: Vermenigvuldig elk cijfer met de bijhorende macht van 2
- **1 × 2³ = 8**
- **0 × 2² = 0**
- **1 × 2¹ = 2**
- **1 × 2⁰ = 1**

### Stap 2: Tel alle waarden op
$$
8 + 0 + 2 + 1 = 11_{10}
$$

**Conclusie:** **1011₂ = 11₁₀** in decimale notatie.

---

## 2. Octaal naar decimaal

Het **octale talstelsel** gebruikt de cijfers **0-7** en is gebaseerd op machten van **8**.

**Voorbeeld:** Zet **442₈** om naar decimaal.

| Octaal cijfer | 4 | 4 | 2 |
|--------------|---|---|---|
| Macht van 8  | 8² | 8¹ | 8⁰ |
| Berekening   | 4×64 | 4×8 | 2×1 |

### Stap 1: Vermenigvuldig elk cijfer met de bijhorende macht van 8
- **4 × 8² = 256**
- **4 × 8¹ = 32**
- **2 × 8⁰ = 2**

### Stap 2: Tel alle waarden op
$$
256 + 32 + 2 = 290_{10}
$$

**Conclusie:** **442₈ = 290₁₀** in decimale notatie.

---

## 3. Hexadecimaal naar decimaal

Het **hexadecimale talstelsel** gebruikt **16 symbolen**: de cijfers **0-9** en de letters **A-F** (waarbij **A=10**, **B=11**, ..., **F=15**). Elke positie stelt een macht van **16** voor.

**Voorbeeld:** Zet **2F3₁₆** om naar decimaal.

| Hexadecimaal cijfer | 2 | F (15) | 3 |
|---------------------|---|------|---|
| Macht van 16       | 16² | 16¹ | 16⁰ |
| Berekening         | 2×256 | 15×16 | 3×1 |

### Stap 1: Vermenigvuldig elk cijfer met de bijhorende macht van 16
- **2 × 16² = 512**
- **15 × 16¹ = 240**
- **3 × 16⁰ = 3**

### Stap 2: Tel alle waarden op
\[
512 + 240 + 3 = 755_{10}
\]

**Conclusie:** **2F3₁₆ = 755₁₀** in decimale notatie.

---

Door deze methode te volgen, kan je elk getal omzetten naar decimaal.
