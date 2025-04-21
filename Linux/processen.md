## Processen

In een besturingssysteem is een proces simpelweg een lopend programma. Wanneer je een programma start, maakt het systeem een nieuw proces aan en krijgt het een uniek identificatienummer (PID). Processen communiceren vaak met elkaar, hebben onderlinge relaties (zoals ouder- en kindprocessen) en delen systeembronnen zoals geheugen en CPU-tijd. Op Linux heb je allerlei tools om deze processen te bekijken en te beheren. Laten we de belangrijkste commando's stap voor stap doornemen.

##### CTRL + C

Wanneer je in een terminal een programma uitvoert, werkt dit meestal in de voorgrond. Door CTRL+C in te drukken, stuur je een SIGINT (interrupt-signaal) naar dat proces. Dit signaal vraagt het programma vriendelijk om te stoppen. Niet elk proces reageert op SIGINT; sommige programma’s kunnen dit signaal negeren of anders afhandelen, maar voor de meeste standaardtoepassingen zorgt deze actie er gewoon voor dat het proces stopt.

##### ps

Het `ps`-commando geeft je een momentopname van de processen die op dat moment actief zijn. Veelgebruikte opties zijn:
- `ps aux`: Hiermee krijg je een uitgebreid overzicht van alle processen, inclusief informatie als de gebruikersnaam, PID, CPU- en geheugengebruik en de commandoregel die het proces heeft gestart.
- `ps -ef`: Geeft eveneens een overzicht van alle processen in een iets andere, maar even informatieve lay-out.

Dit is handig als je snel wilt zien welke programma’s draaien en welke PID je bijvoorbeeld nodig hebt om een bepaald proces met `kill` te stoppen.

##### pstree

Het `pstree`-commando toont je de hiërarchische structuur van alle processen in de vorm van een boom. Je ziet direct de relatie tussen ouder- en kindprocessen. Dit helpt enorm als je wilt begrijpen welke processen door andere processen zijn gestart. De "boomstructuur" maakt het visueel inzichtelijk, vooral als je een complexe situatie met veel processen wilt doorgronden.

##### kill

Met het `kill`-commando stuur je een signaal naar een of meerdere processen, meestal om ze te beëindigen. Standaard verstuurt `kill` een SIGTERM (terminate-signaal), wat een vriendelijk verzoek is om af te sluiten. Soms reageert een proces hier niet op en moet je met een krachtiger signaal, zoals SIGKILL (kill -9), het proces abrupt beëindigen. Een voorbeeld:
```bash
kill 1234
```

Hiermee stuur je een SIGTERM naar het proces met PID 1234. Wees voorzichtig: abrupt beëindigen kan leiden tot het verlies van niet-opgeslagen gegevens.

##### pgrep

Het `pgrep`-commando is een handige tool om snel de PID’s van processen te vinden door te zoeken op naam of een ander kenmerk van het proces. Stel je wilt alle processen met “firefox” opzoeken, dan gebruik je:
```bash
pgrep firefox
```

Dit commando toont dan de PID’s van alle processen die “firefox” in hun naam hebben. Zo hoef je niet handmatig door een lange lijst van processen te zoeken met `ps`.


##### pkill

Vergelijkbaar met `pgrep`, maar `pkill` stuurt een signaal naar de gevonden processen in plaats van alleen hun PID’s weer te geven. Als je bijvoorbeeld alle Firefox-processen wilt afsluiten, typ je:

```bash
pkill firefox
```

Standaard verstuurt dit commando ook een SIGTERM. Hiermee kun je snel processen afsluiten zonder eerst de PID’s op te zoeken.


### Nice Level

Het nice level (of “niceness”) is een getal dat aangeeft hoe vriendelijk een proces is voor andere processen wat betreft CPU-gebruik. Simpel gezegd bepaalt het de prioriteit waarmee een proces wordt uitgevoerd. Dankzij dit mechanisme kan het systeem ervoor zorgen dat belangrijke, interactieve taken (zoals het typen op je toetsenbord of het navigeren in een webbrowser) voldoende rekenkracht krijgen, terwijl zware achtergrondprocessen op de achtergrond blijven.

#### Hoe werkt het nice level?
Nice levels variëren in Linux van **-20 tot 19**. Een **lage waarde** (dichterbij -20) betekent dat een proces **minder “nice”** is, oftewel het claimt meer van de beschikbare CPU-tijd en krijgt dus een hogere prioriteit. Een **hoge waarde** (dichterbij 19) geeft aan dat een proces **meer “nice”** is, waardoor het CPU-tijd minder agressief opeist. Standaard starten processen met een nice level van 0.

Stel dat je een programma hebt dat veel rekenkracht nodig heeft (zoals een videobewerkingsprogramma of een simulatie), maar je wilt niet dat het de respons van je computer of andere applicaties beïnvloedt. Dan kun je het nice level van dat programma verhogen. Dit doe je door het proces “vriendelijker” te maken: het deelt de CPU met andere programma’s en zorgt ervoor dat interactieve taken voorrang krijgen.

#### Hoe stel je het nice level in?

##### Bij het starten van een proces:
Met het nice-commando kun je direct bij het opstarten een specifiek nice level instellen. Bijvoorbeeld:
```bash
nice -n 10 ./jouw_programma
```

Dit start `jouw_programma` met een nice level van 10, waardoor het minder CPU-prioriteit krijgt dan standaard processen.

##### Aanpassen van een al draaiend proces:
Als een proces al draait, kun je het nice level aanpassen met `renice`. Stel dat je het nice level van een proces met PID 1234 wilt wijzigen naar 5, dan voer je het volgende commando uit:
```bash
renice -n 5 -p 1234
```

Houd er rekening mee dat het verlagen van het nice level (bijvoorbeeld naar een negatieve waarde) meestal beheerdersrechten (root) vereist, omdat je het prioriteitsniveau van een proces verhogend aanpast.

### Jobs

In Linux, en eigenlijk in elke Unix-achtige shell (zoals bash), zijn jobs processen die je hebt gestart vanuit jouw terminalsessie. Deze processen kunnen op verschillende manieren actief zijn: ze kunnen op de voorgrond draaien, op de achtergrond draaien of “gestopt” (ofwel gesuspendeerd) zijn. Deze functionaliteit maakt het mogelijk om meerdere taken tegelijk te beheren en te schakelen tussen wat je op het moment direct ziet en wat op de achtergrond draait.

#### Hoe ontstaan jobs?

##### Voorgrond en achtergrond:
Wanneer je een opdracht invoert zonder extra toevoegingen, wordt deze uitgevoerd als een voorgrondjob. De terminal "wacht" dan totdat dat proces klaar is voordat je een nieuw commando kunt geven. Door een opdracht af te sluiten met een `&` (bijv. `./script.sh &`), geef je aan dat je de opdracht op de achtergrond wilt draaien. Het proces krijgt hierdoor een job-nummer en draait los van de terminal, waardoor je direct weer een nieuwe prompt krijgt.

##### Jobs opschorten (suspenden):
Als je een actief proces tijdelijk wilt onderbreken, kun je in de voorgrond vaak op CTRL+Z drukken. Hiermee wordt het proces gesuspendeerd en omgezet in een job die niet actief aan de CPU wordt toegewezen. Je kunt later hiermee verder gaan.

#### Beheren van jobs

Linux biedt een aantal handige commando's om deze jobs te beheren:

##### jobs
Met dit commando krijg je een lijst van alle jobs die aan de huidige terminalsessie zijn gekoppeld. Je ziet per job het job-nummer, de status (bijvoorbeeld `Running` of `Stopped`) en de opdrachtregel die je hebt ingevoerd. Dit helpt je om snel te zien welke processen nog actief zijn of gesuspendeerd worden.


##### fg
Dit commando haalt een job naar de voorgrond. Als je bijvoorbeeld een gesuspendeerde job (bijvoorbeeld job 1) weer in de voorgrond wilt draaien, typ je:
```bash
fg %1
```
Hierdoor wordt de job hervat en ben je weer direct bezig met dat proces.

##### bg
Als je een gesuspendeerde job op de achtergrond wilt laten doorgaan, gebruik je bg gevolgd door het job-nummer. Bijvoorbeeld:
```bash
bg %1
```

Hiermee hervat de job in de achtergrond, zodat hij verder loopt zonder dat hij jouw terminal in beslag neemt.