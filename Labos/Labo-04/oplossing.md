# Labo-04: Branching, Merging en Remote Repository

### Leerstof
- [Branches](/Git/branching.md)

## Oefening 1: Werken met Branches

1. Maak een nieuwe map aan en initialiseer een Git-repository:
    ```sh
    mkdir oefening-git && cd oefening-git
    git init
    ```
2. Maak een nieuw HTML-bestand genaamd `index.html` en voeg de volgende basisinhoud toe:
    ```html
    <!DOCTYPE html>
    <html>
    <head>
        <title>Mijn Website</title>
    </head>
    <body>
        <h1>Welkom op mijn website</h1>
    </body>
    </html>
    ```
3. Voeg het bestand toe aan Git en commit de wijziging:
    ```sh
    git add index.html
    git commit -m "Eerste commit - basis HTML"
    ```
4. Maak een nieuwe branch `nieuwe-stijl` en schakel ernaar:
    ```sh
    git branch nieuwe-stijl
    git switch nieuwe-stijl
    ```
5. Voeg een CSS-bestand toe genaamd `style.css` met deze inhoud:
    ```css
    body {
        background-color: lightblue;
    }
    ```
6. Link de CSS in `index.html` en commit de wijziging:
    ```sh
    git add .
    git commit -m "Stijl toegevoegd"
    ```
7. Schakel terug naar de `main` branch en merge de `nieuwe-stijl` branch:
    ```sh
    git switch main
    git merge nieuwe-stijl
    ```
8. Verwijder de branch na het samenvoegen:
    ```sh
    git branch -d nieuwe-stijl
    ```

---

## Oefening 2: Conflicten oplossen bij Merging

1. Start in de `main` branch en maak een nieuwe branch `tekst-update`:
    ```sh
    git branch tekst-update
    git switch tekst-update
    ```
2. Wijzig `index.html` door `<h1>Welkom op mijn geweldige website</h1>` in te voegen en commit de wijziging:
    ```sh
    git add index.html
    git commit -m "Titel bijgewerkt op tekst-update branch"
    ```
3. Schakel terug naar `main` en bewerk `index.html` opnieuw, verander de `<h1>`-tag naar:
    ```html
    <h1>Welkom op mijn fantastische website</h1>
    ```
4. Commit deze wijziging op `main`:
    ```sh
    git add index.html
    git commit -m "Titel bijgewerkt op main branch"
    ```
5. Probeer de `tekst-update` branch samen te voegen:
    ```sh
    git merge tekst-update
    ```
6. Git zal een merge-conflict melden. Open `index.html` en los het conflict op door een combinatie van beide zinnen te gebruiken.
7. Voeg de opgeloste versie toe en commit:
    ```sh
    git add index.html
    git commit -m "Merge-conflict opgelost"
    ```
8. Verwijder de `tekst-update` branch:
    ```sh
    git branch -d tekst-update
    ```

---