# Deelopdract 1: Opzetten van een Wiki met Markdown en Git

## Opdrachtbeschrijving
In deze opdracht ga je een uitgebreide **Wiki** opzetten met behulp van **Git en GitHub**. Je leert hoe je een lokale repository initialiseert, bestanden toevoegt, commits uitvoert, een nieuwe branch aanmaakt, een merge uitvoert en samenwerkt met een **remote repository**. Daarnaast zul je een **merge conflict** moeten oplossen.

Je mag zelf een thema kiezen voor je Wiki. Dit kan een serie, film, game of ander onderwerp zijn dat je interessant vindt. Denk bijvoorbeeld aan een Wiki over de wereld van **Harry Potter, The Lord of the Rings, Star Wars, Marvel, The Witcher, Zelda, Pokémon** of een andere franchise die je leuk vindt.

---

## Doelstellingen
- Een **lokale Git-repository** opzetten
- Markdown-bestanden toevoegen en aanpassen
- **Commits** uitvoeren om wijzigingen op te slaan
- Werken met **branches** en deze samenvoegen
- Een **remote repository** koppelen en synchroniseren met GitHub
- **Merge conflicts** begrijpen en oplossen

---

## Good Practices (Beoordelingscriteria)
Om goed met Git te werken en een gestructureerde repository op te zetten, wordt beoordeeld op de volgende best practices:

- **Duidelijke commit messages**: Gebruik betekenisvolle commitberichten die beschrijven wat er veranderd is.
- **Frequente commits**: Maak regelmatig commits in plaats van grote hoeveelheden wijzigingen in één keer op te slaan.
- **Correct gebruik van branches**: Werk in feature-branches en merge deze naar `main` via pull requests of merges.
- **Oplossen van merge conflicts**: Conflicten moeten op een gestructureerde manier opgelost worden zonder onnodige codeverlies.
- **Overzichtelijke repository-structuur**: Zorg ervoor dat je bestanden goed geordend zijn en de inhoud logisch is opgebouwd.
- **Consistente bestandsnamen**: Gebruik een logische en consistente naamgeving voor je Markdown-bestanden.

---

## Stap 1: Opzetten van een lokale repository
1. Maak een nieuwe map aan op je computer genaamd `wiki-project`.
2. Navigeer met de terminal naar deze map.
3. Initialiseer een nieuwe Git-repository.
4. Maak een nieuw Markdown-bestand `index.md` en voeg hierin een korte inleiding toe over jouw gekozen thema.
5. Voeg het bestand toe aan de staging area en maak een eerste commit.

---

## Stap 2: Meer content toevoegen
1. Voeg drie extra Markdown-bestanden toe, bijvoorbeeld `personages.md`, `verhaal.md` en `locaties.md`.
2. Voeg in elk bestand een titel en een korte beschrijving toe over jouw gekozen thema.
3. Update `index.md` om links naar deze bestanden toe te voegen.
4. Voeg alle wijzigingen toe aan Git en commit deze.

---

## Stap 3: Werken met branches
1. Maak een nieuwe branch aan genaamd `about-page`.
2. Schakel over naar de nieuwe branch.
3. Voeg een `about.md` bestand toe waarin je een korte beschrijving plaats over jezelf.
4. Commit de wijziging en switch terug naar de `main` branch.

---

## Stap 4: Samenvoegen van de branches
1. Merge de `about-page` branch terug in `main`.
2. Verwijder de `about-page` branch na het mergen.

---

## Stap 5: Werken met een remote repository
1. Maak een nieuwe repository aan op **GitHub** genaamd `wiki-project` (zonder README, `.gitignore` of licentiebestand).
2. Koppel je lokale repository aan GitHub.
3. Push de `main` branch naar de remote repository.

---

## Stap 6: Een merge conflict simuleren en oplossen
1. Maak een nieuwe branch `update-verhaal`.
2. Open `verhaal.md` en voeg een nieuwe paragraaf toe.
3. Commit en push deze wijziging.
4. **In de GitHub webinterface**: Open `verhaal.md` en wijzig een andere regel.
5. Commit de wijziging direct op de `main` branch via GitHub.
6. Terug in de terminal: Schakel over naar de `main` branch en haal de laatste wijzigingen op.
7. Probeer de `update-verhaal` branch te mergen met `main`.
8. Er zal een **merge conflict** ontstaan in `verhaal.md`. Open het bestand en los het conflict op door de juiste versie te behouden.
9. Voeg het bestand opnieuw toe en commit de oplossing.

---

## Inleveren
- Maak een gecomprimeerde folder (`.zip`) van je wiki-project en upload deze op Digitap. 
- Voeg de url naar je remote repository toe in de comment sectie van de upload 