# Character Encoding

## Wat is Character Encoding?
Character encoding (karaktercodering) is een methode om tekens (zoals letters, cijfers en symbolen) te representeren als binaire data, zodat computers ze kunnen opslaan en verwerken. Computers werken intern met enen en nullen, en character encoding bepaalt hoe deze bits en bytes worden omgezet naar leesbare tekens.

Een character encoding definieert een mapping tussen binaire waarden en de symbolen die mensen begrijpen, zoals letters (A-Z), cijfers (0-9) en speciale tekens (€, @, ñ). Bekende encodings zijn ASCII, UTF-8, UTF-16 en ISO-8859-1.

**Stel je voor:**
Je schrijft een brief aan een vriend, maar in plaats van gewone letters te gebruiken, vervang je elke letter door een nummer volgens een geheime code. Bijvoorbeeld:

A = 65
B = 66
C = 67
enzovoort...

Als je het woord "HALLO" wilt versturen, zet je het om in nummers:

H A L L O → 72 65 76 76 79

Je vriend weet dat hij deze nummers moet omzetten naar letters met dezelfde code om de boodschap te begrijpen.


**Wat heeft dit met computers te maken?**
Computers begrijpen alleen getallen, geen letters. Om tekst op te slaan en weer te geven, gebruiken ze character encoding, zoals ASCII of UTF-8, waarin elke letter of symbool een uniek nummer krijgt.

Bijvoorbeeld:

- In ASCII is de letter "A" altijd 65 en "B" altijd 66.
- In UTF-8 kunnen we ook emoji's en andere talen coderen, zoals "é" of "你好".
- Als je een tekstbestand opent en de verkeerde encoding gebruikt, kan je computer de getallen verkeerd omzetten en krijg je rare tekens zoals "Ã©" in plaats van "é".


## Waarom is Character Encoding relevant voor web- en software ontwikkelaars?

Als je character encoding niet begrijpt, krijg je rare tekens, gebroken tekst en zelfs beveiligingsproblemen. Als ontwikkelaar moet je ervoor zorgen dat alles – van je code tot je database en API’s – dezelfde encoding gebruikt.

**Enkele praktijkvoorbeelden**

- Als een database in UTF-8 is ingesteld, maar een applicatie tekst opslaat met ISO-8859-1, kunnen bepaalde tekens (zoals "é" of "ü") verkeerd worden weergegeven. Dit kan problemen opleveren bij het tonen van data in een webinterface of het verwerken van gebruikersinvoer.

- Slechte handling van encoding kan leiden tot beveiligingsrisico’s, zoals SQL-injection of Cross-Site Scripting (XSS). Als je niet goed controleert welke encoding je gebruikt, kunnen kwaadwillenden bijvoorbeeld Unicode-karakters misbruiken om je inputvalidatie te omzeilen.