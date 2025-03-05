### Merge Conflicts in Git

#### Wat is een Merge Conflict?
Wanneer je samenwerkt aan een project in Git, werk je vaak tegelijkertijd met anderen aan dezelfde bestanden. Git helpt om wijzigingen van verschillende mensen **samen te voegen (merge)**, maar soms lukt dat niet automatisch. Dit gebeurt wanneer **twee of meer mensen dezelfde regel in een bestand wijzigen**. Dit noemen we een **merge conflict**.

Een merge conflict betekent dat Git niet weet welke versie de juiste is, en **jij moet beslissen** welke code behouden blijft.

#### Metafoor: Een gezamenlijke tekst schrijven
Stel je voor dat jij en een vriend een verslag schrijven in een schrift. 

1. Jij schrijft op een pagina:
   ```
   Ik hou van pizza.
   ```
2. Ondertussen, zonder dat jij het weet, heeft je vriend op **dezelfde regel** geschreven:
   ```
   Ik hou van sushi.
   ```
3. Wanneer jij jouw versie inlevert, zegt de leraar:
   **"Wacht, er zijn twee versies! Welke is correct?"**

Dit is precies wat Git doet bij een **merge conflict**: het vraagt jou om te kiezen welke versie je wilt behouden.

#### Merge Conflicts in Git: Wanneer gebeuren ze?
Een merge conflict ontstaat meestal wanneer:
- Je **wijzigingen lokaal hebt gemaakt**, maar **iemand anders heeft intussen dezelfde regel gewijzigd in de remote repository**.
- Je probeert jouw code naar de server te pushen, maar Git weigert omdat er nieuwe wijzigingen zijn die je eerst moet verwerken.

#### Praktische Simulatie: Een Merge Conflict Oplossen

In deze oefening ga je een merge conflict **zelf simuleren en oplossen**. 

##### **Stap 1: Voorbereiding**
1. Open een terminal en maak een nieuwe testmap:
   ```bash
   mkdir git-merge-conflict-demo && cd git-merge-conflict-demo
   ```
2. Initialiseer een nieuwe Git-repository:
   ```bash
   git init
   ```
3. Maak een bestand `bestand.txt` en voeg de volgende regel toe:
   ```
   Hallo, dit is mijn eerste regel.
   ```
4. Voeg het bestand toe aan Git en commit:
   ```bash
   git add bestand.txt
   git commit -m "Eerste commit"
   ```
5. Koppel de repository aan een **GitHub-repository** (vervang `<URL>` door de echte URL van jouw repo):
   ```bash
   git remote add origin <URL>
   git push -u origin main
   ```

##### **Stap 2: Simuleer een wijziging op GitHub**
1. Open jouw repository op **GitHub**.
2. Bewerk `bestand.txt` direct via de GitHub-interface en wijzig de regel naar:
   ```
   Hallo, dit is een wijziging op GitHub.
   ```
3. Sla de wijziging op en commit direct naar de `main` branch.

##### **Stap 3: Simuleer een lokale wijziging**
1. Ga terug naar jouw terminal en **bewerk lokaal** `bestand.txt`.
2. Wijzig de regel naar:
   ```
   Hallo, dit is een lokale wijziging.
   ```
3. Commit jouw wijziging lokaal:
   ```bash
   git commit -am "Lokale wijziging gemaakt"
   ```
4. Probeer nu je code naar GitHub te pushen:
   ```bash
   git push origin main
   ```
**🚨 Dit zal mislukken, omdat Git detecteert dat er wijzigingen op GitHub zijn die niet lokaal zijn binnengehaald!**

##### **Stap 4: Los het merge conflict op**

1. Trek eerst de nieuwste wijzigingen op via een **rebase**:
   ```bash
   git pull --rebase origin main
   ```
2. Git zal melden dat er een **merge conflict** is:
   ```
   CONFLICT (content): Merge conflict in bestand.txt
   ```
3. Open **VS Code** en bekijk het bestand `bestand.txt`. Daar zie je iets zoals:
   ```
   <<<<<<< HEAD
   Hallo, dit is een lokale wijziging.
   =======
   Hallo, dit is een wijziging op GitHub.
   >>>>>>> main
   ```
4. **Kies de gewenste versie:**
   - Behoud jouw versie
   - Behoud de GitHub-versie
   - Combineer beide versies
5. Sla het bestand op en markeer het als opgelost:
   ```bash
   git add bestand.txt
   ```
6. Rond de rebase af:
   ```bash
   git rebase --continue
   ```
7. Push nu je code naar GitHub:
   ```bash
   git push origin main
   ```


#### Enkele leerijke video's

[Never fear merge conflicts again - git merge/pull tutorial](https://youtu.be/DloR0BOGNU0?si=QpzqxCjEqmJw3Ufx)
<iframe width="560" height="315" src="https://www.youtube.com/embed/DloR0BOGNU0?si=ptQpx7kP9MIOyrX8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

---

[git rebase - Why, When & How to fix conflicts](https://youtu.be/DkWDHzmMvyg?si=RA9lDzQq7O35_5Sk)
<iframe width="560" height="315" src="https://www.youtube.com/embed/DkWDHzmMvyg?si=OaZjcZx2_GcGAqI3" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

---