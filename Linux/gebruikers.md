## Gebruikers en Groepen

Een **gebruiker** in een besturingssysteem zoals Linux is een **identiteit** die toegang heeft tot het systeem. Elke gebruiker heeft zijn eigen **account**, bestanden, instellingen en rechten. Zo kunnen gebruikers elkaars bestanden niet zomaar bekijken of aanpassen.

Linux is van nature een **multi-user** OS, wat betekent dat meerdere gebruikers tegelijk op hetzelfde systeem kunnen werken — fysiek of via een netwerk.

##### Types gebruikers

- **Normale gebruikers:** Voor dagelijks gebruik. Beperkte rechten.
- **Root (beheerder):** Superuser met alle rechten. Mag alles op het systeem.
- **System users:**  Een speciale gebruiker die niet bedoeld is voor echte mensen, maar voor programma’s of diensten die op je computer draaien.

### Gebruikersbeheer

Elke gebruiker in Linux heeft een unieke gebruikersnaam en een bijhorende **UID** (user ID). Wanneer je een nieuwe gebruiker aanmaakt, worden zijn of haar gegevens verdeeld over een paar bestanden in `/etc`.

##### `/etc/passwd` – bevat info over gebruikers (naam, UID, shell, etc.)

Voor elke gebruiker wordt een regel bij aangemaakt met volgende info:
```bash
jan:x:1001:1001::/home/jan:/bin/bash
```
Deze lijn bevat 7 velden, gescheiden door een dubbele punt (`:`).

| Veld                | Voorbeeld       | Uitleg                                                                 |
|---------------------|------------------|------------------------------------------------------------------------|
| 1. gebruikersnaam   | p151886          | De loginnaam van de gebruiker                                          |
| 2. wachtwoord       | x                | Staat hier niet meer; het echte (versleutelde) wachtwoord zit in `/etc/shadow` |
| 3. UID              | 3001             | User ID: uniek nummer dat het systeem gebruikt om de gebruiker te identificeren |
| 4. GID              | 3001             | Group ID: primaire groep van de gebruiker                             |
| 5. beschrijving     | leeg (`::`)      | Extra info over de gebruiker, zoals volledige naam (kan leeg zijn)    |
| 6. homedir          | /home/p151886    | De thuismap van de gebruiker                                          |
| 7. shell            | /bin/bash        | De standaard shell die gebruikt wordt wanneer de gebruiker inlogt     |


##### `/etc/shadow` – bevat versleutelde wachtwoorden

Het wachtwoord (versleuteld!) van een gebruiker wordt niet in `/etc/passwd` bewaard, maar in `/etc/shadow`.
```bash
jan:$6$zud...hashedwachtwoord...:19439:0:99999:7:::
```

##### `/etc/group` – bevat info over groepen

Wanneer we een gebruiker aanmaken wordt deze toevoegd aan een groep. Alle groepen in ons besturingssysteem worden getoond in `/etc/group`, waarin elke regel één groep bevat:
```bash
groepsnaam:x:GID:leden
```

#### Belangrijke commando's
##### Gebruiker aanmaken (`adduser`, `useradd`)  

Maakt een nieuwe gebruiker aan.  
`adduser` is gebruiksvriendelijker en stelt ook een wachtwoord en home folder in.

```bash
sudo adduser jan
```

Voor scripts gebruik je eerder `useradd`, maar dan wordt niet alles standaard voor je ingesteld en moet je zelf extra opties opgeven om bijvoorbeeld een home folder aan te maken.

```bash
sudo useradd -m -s /bin/bash jan
```

De `-m` optie maakt een home directory aan, en `-s` stelt de standaard shell in.




##### Gebruiker verwijderen (`userdel`)  

Verwijdert een gebruiker van het systeem.

```bash
sudo userdel jan
```

Wil je ook de home directory en bestanden verwijderen, gebruik dan de `-r` optie:

```bash
sudo userdel -r jan
```


##### Wachtwoord instellen of wijzigen (`passwd`)  

Stelt een wachtwoord in voor een gebruiker.

```bash
sudo passwd jan
```

De gebruiker wordt dan gevraagd om tweemaal een nieuw wachtwoord in te geven.


##### Gebruiker aanpassen (`usermod`)  

Wijzigt eigenschappen van een bestaande gebruiker.  
Bijvoorbeeld: extra groep toevoegen.

```bash
sudo usermod -aG sudo jan
```

De `-aG` optie voegt de gebruiker toe aan een groep, zonder bestaande groepen te overschrijven.


##### Huidige gebruiker tonen (`whoami`)  

Toont onder welke gebruikersnaam je momenteel bent ingelogd.

```bash
whoami
```

Handig om snel te checken of je root bent of niet.


##### Informatie over een gebruiker (`id`)  

Toont UID, GID en groepen van een gebruiker.

```bash
id jan
```

Geeft bijvoorbeeld:

```
uid=1001(jan) gid=1001(jan) groepen=1001(jan),27(sudo)
```


### Groepsbeheer

Groepen worden gebruikt om gebruikers rechten te geven over bestanden of toegang tot bepaalde functies. Elke gebruiker heeft een primaire groep en kan lid zijn van secundaire groepen. 

De **primaire groep** is de standaardgroep waartoe een gebruiker behoort. 
- Elk bestand dat je als gebruiker aanmaakt, wordt automatisch aan deze groep toegekend. 
- Deze groep wordt vermeld in `/etc/passwd` (vierde veld - GID). 
- Vaak heeft elke gebruiker een eigen groep met dezelfde naam als de gebruikersnaam.

Een **secundaire groep** is een extra groep waartoe een gebruiker behoort, naast de primaire groep.

- Hierdoor kan de gebruiker ook rechten krijgen op bestanden of opdrachten die aan die groep gekoppeld zijn.
- Worden vermeld in `/etc/group`, als lid van een groep.


##### Praktisch voorbeeld
Stel:

- `sara` heeft als primaire groep `sara`
- `sara` is ook lid van de groep `projectgroep`

Wat gebeurt er?

- Als sara een bestand maakt, is de groep-eigenaar standaard `sara`.
- Als de map `/srv/project` eigendom is van groep `projectgroep`, dan kan `sara` daar ook aan werken omdat ze secundair lid is van die groep.


#### Belangrijke commando's

##### Groep aanmaken (`groupadd`)  

Maakt een nieuwe groep aan.

```bash
sudo groupadd ontwikkelaars
```


##### Groep verwijderen (`groupdel`)  

Verwijdert een groep.

```bash
sudo groupdel ontwikkelaars
```


##### Groep aanpassen (`groupmod`)  

Wijzigt een groepsnaam of GID.

```bash
sudo groupmod -n devs ontwikkelaars
```

Hier wordt de groep `ontwikkelaars` hernoemd naar `devs`.


##### Groepen van gebruiker tonen (`groups`)  

Toont de groepen waarvan een gebruiker lid is.

```bash
groups jan
```

Geeft bijvoorbeeld:

```
jan : jan sudo docker
```


### Commando’s uitvoeren als een andere gebruiker

Wanneer je in Linux aan het werken bent zal je ongetwijfeld wel eens een commando moeten uitvoeren als een andere gebruiker.

##### Wissel van gebruiker (`su`)  

Gebruik `su` als je **volledig wilt overschakelen naar een andere gebruiker**, inclusief omgeving (zoals de shell en home folder).

```bash
su
```

Of wissel naar een specifieke gebruiker:

```bash
su jan
```

Hiervoor heb je het wachtwoord van die gebruiker nodig.


##### Commando uitvoeren als administrator (`sudo`)  

Gebruik `sudo` als je **tijdelijk een commando wilt uitvoeren met rootrechten** of namens een andere gebruiker.

```bash
sudo apt update
```

Je voert dit commando uit **alsof je de `root`-gebruiker bent**, maar **je blijft ingelogd als jezelf** en geeft je eigen wachtwoord op.

⚠️ Alleen gebruikers die in de sudo groep zitten mogen sudo gebruiken.


##### Commando uitvoeren als een andere gebruiker (`sudo -u`)  

Voer een commando uit als een andere gebruiker.

```bash
sudo -u jan ls /home/jan
```

Je voert `ls /home/jan` uit alsof je gebruiker `jan` bent.

