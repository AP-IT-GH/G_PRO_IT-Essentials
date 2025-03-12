## Linux gebruikershandleiding en commando opties
In Linux worden **opties** (ook wel **flags** of **parameters** genoemd) gebruikt om het gedrag van een commando aan te passen. Ze worden meestal voorafgegaan door een **dash (`-`)** of **double dash (`--`)**. Er zijn twee soorten opties:

1. **Korte opties:** Dit zijn éénletterige opties, voorafgegaan door een enkele `-`. Je kunt ze vaak combineren.
    
    Voorbeeld: `ls -l -a` kan ook als `ls -la` worden geschreven.

2. **Lange opties:** Dit zijn beschrijvende opties, voorafgegaan door `--`.
    Voorbeeld: `ls --all` is hetzelfde als `ls -a`.

### Opties vinden met `man` (manual pages)
Linux heeft ingebouwde documentatie via het man-commando, waarmee je de handleiding van een commando kunt bekijken. Om de beschikbare opties van een commando op te zoeken, gebruik je:

```bash
man <commando>
```
Bijvoorbeeld, om de opties van ls te bekijken:
```bash
man ls
```
Dit opent de handleiding, waar je onder de sectie **"OPTIONS**" een lijst met beschikbare opties vindt.

In de handleiding kan je navigeren met de volgende keys:
- **Pijl omhoog/omlaag**: Scrollen door de tekst.
- `Space`: Een pagina verder.
- `q`: De man-pagina sluiten.
- `/` **+ zoekterm**: Zoeken binnen de handleiding (bv. `/recursive` om naar de optie te zoeken).

### Alternatief: `--help` gebruiken
Als je snel de opties wilt bekijken zonder de volledige handleiding, kun je de --help-optie gebruiken:
```bash
ls --help
```
Dit geeft een beknopt overzicht van de beschikbare opties.