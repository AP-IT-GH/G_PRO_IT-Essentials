# Labo-01: Talstelsels [OPLOSSINGEN]

## Leerstof
- [Talstelsels](/Talstelsels/README.md)

## 1. Decimaal naar Binair

### 📝 **Oefening 1**
Zet **29₁₀** om naar binair.

### ✅ **Oplossing**
We gebruiken **herhaalde deling door 2**:

| Stap | Deling   | Quotiënt | Rest (binair cijfer) |
|------|---------|---------|------------------|
| 1    | 29 ÷ 2  | 14      | **1**            |
| 2    | 14 ÷ 2  | 7       | **0**            |
| 3    | 7 ÷ 2   | 3       | **1**            |
| 4    | 3 ÷ 2   | 1       | **1**            |
| 5    | 1 ÷ 2   | 0       | **1**            |

**Antwoord:**  
$$
29_{10} = 11101_2
$$

---

### 📝 **Oefening 2**
Zet **45₁₀** om naar binair.

### ✅ **Oplossing**
| Stap | Deling   | Quotiënt | Rest (binair cijfer) |
|------|---------|---------|------------------|
| 1    | 45 ÷ 2  | 22      | **1**            |
| 2    | 22 ÷ 2  | 11      | **0**            |
| 3    | 11 ÷ 2  | 5       | **1**            |
| 4    | 5 ÷ 2   | 2       | **1**            |
| 5    | 2 ÷ 2   | 1       | **0**            |
| 6    | 1 ÷ 2   | 0       | **1**            |

**Antwoord:**  
$$
45_{10} = 101101_2
$$

---

## 2. Binair naar Decimaal

### 📝 **Oefening 3**
Zet **1101₂** om naar decimaal.

### ✅ **Oplossing**

We gebruiken de **machtsvermenigvuldiging van 2**. Vermenigvuldig elk cijfer met de bijhorende macht van 2 en tel alle waarden op:

$$
(1 × 2^3) + (1 × 2^2) + (0 × 2^1) + (1 × 2^0)
$$

$$
(1 × 8) + (1 × 4) + (0 × 2) + (1 × 1) = 8 + 4 + 0 + 1 = 13
$$

**Antwoord:**  
$$
1101_2 = 13_{10}
$$

---

### 📝 **Oefening 4**
Zet **10110₂** om naar decimaal.

### ✅ **Oplossing**

Vermenigvuldig elk cijfer met de bijhorende macht van 2 en tel alle waarden op:
$$
(1 × 2^4) + (0 × 2^3) + (1 × 2^2) + (1 × 2^1) + (0 × 2^0)
$$

$$
(1 × 16) + (0 × 8) + (1 × 4) + (1 × 2) + (0 × 1) = 16 + 0 + 4 + 2 + 0 = 22
$$

**Antwoord:**  
$$
10110_2 = 22_{10}
$$

---

## 3. Binair naar Hexadecimaal

### 📝 **Oefening 5**
Zet **11110101₂** om naar hexadecimaal.

### ✅ **Oplossing**
1. Groepeer de binaire cijfers in **groepen van 4**, vanaf rechts:  
   **1111 0101**
2. Zet elke groep om naar hex (kijk hiervoor in je [tabel](/Talstelsels/omrekenen_octaal_hexadecimaal/README.md)):
   - **1111₂ = F₁₆**
   - **0101₂ = 5₁₆**

**Antwoord:**  
$$
11110101_2 = F5_{16}
$$

---

### 📝 **Oefening 6**
Zet **10010111₂** om naar hexadecimaal.

### ✅ **Oplossing**
1. Groepeer in groepen van 4:  
   **1001 0111**
2. Zet elke groep om (kijk hiervoor in je [tabel](/Talstelsels/omrekenen_octaal_hexadecimaal/README.md)):
   - **1001₂ = 9₁₆**
   - **0111₂ = 7₁₆**

**Antwoord:**  
$$
10010111_2 = 97_{16}
$$

---

## 4. Decimaal naar Octaal

### 📝 **Oefening 7**
Zet **83₁₀** om naar octaal.

### ✅ **Oplossing**

We gebruiken **herhaalde deling door 8**:

| Stap | Deling   | Quotiënt | Rest (octaal cijfer) |
|------|---------|---------|------------------|
| 1    | 83 ÷ 8  | 10      | **3**            |
| 2    | 10 ÷ 8  | 1       | **2**            |
| 3    | 1 ÷ 8   | 0       | **1**            |

**Antwoord (lees van onder naar boven):**  
$$
83_{10} = 123_8
$$

---

### 📝 **Oefening 8**
Zet **200₁₀** om naar octaal.

### ✅ **Oplossing**

We gebruiken **herhaalde deling door 8**:
| Stap | Deling   | Quotiënt | Rest (octaal cijfer) |
|------|---------|---------|------------------|
| 1    | 200 ÷ 8 | 25      | **0**            |
| 2    | 25 ÷ 8  | 3       | **1**            |
| 3    | 3 ÷ 8   | 0       | **3**            |

**Antwoord (lees van onder naar boven):**  
$$
200_{10} = 310_8
$$

---

## 5. Octaal naar Binair

### 📝 **Oefening 9**
Zet **47₈** om naar binair.

### ✅ **Oplossing**
1. Schrijf elk cijfer om naar 3 binaire cijfers:
   - **4₈** → **100₂**
   - **7₈** → **111₂**

2. Plak alles aan elkaar:
    $$
    47_8 = 100111_2
    $$

---

### 📝 **Oefening 10**
Zet **125₈** om naar binair.

### ✅ **Oplossing**
1. Schrijf elk cijfer om naar 3 binaire cijfers:
   - **1₈** → **001₂**
   - **2₈** → **010₂**
   - **5₈** → **101₂**

2. Plak alles aan elkaar:
    $$
    125_8 = 001010101_2
    $$
