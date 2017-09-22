# Labo 1: Linux installeren

## VirtualBox installeren en een nieuwe VM aanmaken

1. Download en installeer de laatste versie van VirtualBox. Als je werkt op een van de klaspc's (campus Gent), dan is VirtualBox al geïnstalleerd.
2. Maak een nieuwe virtuele machine aan om straks Linux in te installeren. Let er op dat je volgende instellingen voorziet:
    - Als je op een klaspc werkt is de naam van je VM je eigen naam, bv. PietPieters
    - Het type van de VM is “Linux”, de versie “Fedora (64 bit)”
    - RAM: minstens 1024MB
    - Virtuele harde schijf van ~20GB, dynamisch
    - Videogeheugen: zoveel mogelijk (128MB)
    - 3D acceleration aanzetten
    - Maak twee virtuele netwerkadapters aan, één van het type NAT (= standaardkeuze), en één van het type "Host only"

### Procedure

Beschrijf hier de exacte procedure hoe je dit uitgevoerd hebt. Zorg er voor dat je aan de hand van je beschrijving heel vlot de installatie later kan herhalen als dat nodig is.

1. ...

## Linux installeren in een VirtualBox VM

1. Download de laatste [Fedora Live Desktop CD](https://getfedora.org/en_GB/workstation/download/). Start je VM op met deze LiveCD als opstartschijf (het is niet nodig een fysieke cd te branden, je kan een VM rechtstreeks van de ISO booten). Let op dat je met heel de klasgroep niet het draadloos netwerk satureert...
2. Wijzig na opstarten voor het gemak de toetsenbordinstelling naar Belgische Azerty
3. Installeer Fedora naar de harde schijf van je VM (opm. dit is een volkomen veilige operatie en heeft geen enkele invloed op je hostsysteem).
    - Kies de juiste tijdzone, toetsenbordindeling en taal (bij voorkeur Engels)
    - Kies de voorgestelde partitionering van de harde schijf
    - Stel het wachtwoord van de “root” gebruiker in. LET OP: ben je zeker dat je in Azerty-indeling aan het typen bent? TIP: noteer dit wachtwoord onder “Description” in de instellingen van je VirtualBox VM. Als je het vergeet kan je het makkelijk terugvinden.
4. Herstart je VM in het geïnstalleerde systeem. Maak een nieuwe gebruiker aan voor jezelf en voeg die toe aan de “Administrators” groep. In Linux is de conventie om *enkel kleine letters* te gebruiken voor gebruikersnamen.
5. Zoek je weg in het nieuwe systeem.
    - Kan je een webbrowser opstarten? Kan je op het Internet?
    - Kan je een teksteditor (Gnome Editor of Gedit) opstarten?
    - Kan je een tekstverwerker (LibreOffice Writer) opstarten?
    - Kan je de inhoud van je “thuismap” tonen in het Linux-equivalent van Windows Verkenner?
    - Kan je een “terminal-venster” openen?
    - Kan je de screensaver uitschakelen?

**Opmerking** Als je een nieuw Linux-systeem installeert, krijg je al gauw de melding dat er heel wat updates beschikbaar zijn. Het is af te raden om dit in het klaslokaal te doen, opnieuw om de netwerkverbinding naar buiten niet te satureren. Doe dit dus liefst thuis.

### Procedure

Beschrijf hier de exacte procedure hoe je dit uitgevoerd hebt. Zorg er voor dat je aan de hand van je beschrijving deze taken later heel vlot kan herhalen als dat nodig is.

1. ...

## Nieuwe software installeren

Installeer onderstaande applicaties of “packages”. Zorg er voor dat je dit zowel via de grafische gebruikersinterface kan als vanop de command-line.

- git
- nano
- ShellCheck
- vim-enhanced
- vim-X11

Installeer optioneel de “VirtualBox Guest Additions” (zie procedure in de studiewijzer). Creëer een lokale kopie van je Github repository.

### Procedure

Beschrijf hier de exacte procedure hoe je dit uitgevoerd hebt. Zorg er voor dat je aan de hand van je beschrijving deze taken later heel vlot kan herhalen als dat nodig is.

1. ...

## Gebruikers en groepen aanmaken

Het doel van deze opgave is om de opdrachten en de begrippen met betrekking tot  gebruikers en groepen te bestuderen, binnen de context van Linux als een multi-user-systeem.

Tussen de vragen is ruimte voorzien om je antwoorden in te vullen. Het gaat telkens om zgn. codeblokken in Markdown, die starten en eindigen met drie backquotes. Binnen elk codeblok geef je telkens het commando dat je hebt ingetikt en de uitvoer die je krijgt.

1. Je hebt al een gebruiker aangemaakt voor jezelf. Log in als deze gebruiker. Geef hieronder telkens het commando en de uitvoer
    - Wat is het commando om de huidige directory op te vragen? Welke uitvoer toont het commando?

        ```
        $ COMMANDO
        UITVOER
        ```

    - Wat is het UID van deze gebruiker?

        ```
        $ COMMANDO
        UITVOER
        ```

    - Wat is het GID van deze gebruiker?

        ```
        $ COMMANDO
        UITVOER
        ```

2. Log in als de `root`-gebruiker met het commando `su -` (let op de spatie!)
    - Wat is de home-directory van `root`?

        ```
        $ COMMANDO
        UITVOER
        ```

    - Wat is het UID van deze gebruiker?

        ```
        $ COMMANDO
        UITVOER
        ```

    - Wat is het GID van deze gebruiker?

        ```
        $ COMMANDO
        UITVOER
        ```

3. Maak een nieuwe gebruiker aan met de naam `alice`, zonder specifieke opties
    - Geef het gebruikte commando:

        ```
        $ COMMANDO
        UITVOER
        ```

    - Voorzie een geschikt wachtwoord voor deze gebruiker (en vergeet het niet! Noteer het eventueel hier in je verslag of in de beschrijving van je VM)

        ```
        $ COMMANDO
        UITVOER
        ```

4. Configuratiebestanden voor gebruikersbeheer:
    - In welk bestand kan je de UID, gebruikersnaam, homedirectory, enz. van alle gebruikers terugvinden?

        ```
        /PAD/NAAR/BESTAND
        ```

    - In welk configuratiebestand kan je al de bestaande gebruikersgroepen nakijken, en ook de gebruikers die lid zijn van elke groep?

        ```
        /PAD/NAAR/BESTAND
        ```

    - In welk configuratiebestand vind je de *wachtwoorden* van alle gebruikers?

        ```
        /PAD/NAAR/BESTAND
        ```

5. Gebruikersgroepen aanmaken
    - Maak een groep aan met de naam `sporten`

        ```
        $ COMMANDO
        UITVOER
        ```

    - In welk configuratiebestand vind je het GID van deze groep terug?

        ```
        $ COMMANDO
        UITVOER
        ```

    - Wat zal het GID zijn van de groepen `zwemmen` en `judo` als je deze nu onmiddellijk zou aanmaken? Maak ze aan en controleer!

        ```
        $ COMMANDO
        UITVOER
        ```

    - Voeg de gebruiker `alice` toe aan de groepen `sporten` en `zwemmen`

        ```
        $ COMMANDO
        UITVOER
        ```

    - Log in als `alice` door in een terminal het commando `su - alice` (let op de spaties!) uit te voeren

        ```
        $ COMMANDO
        UITVOER
        ```

    - Zorg er nu voor dat de groep `sporten` de primaire groep wordt van `alice`.

        ```
        $ COMMANDO
        UITVOER
        ```

    - Zorg er voor dat `alice` uitgelogd is, ga terug naar `root`

        ```
        $ COMMANDO
        UITVOER
        ```

6. Maak nu de gebruikers in onderstaande tabel aan. Zorg er voor dat ze al meteen bij aanmaken tot de aangegeven groepen behoren. Kies zelf geschikte wachtwoorden voor deze gebruikers en vergeet ze niet (vul eventueel een kolom toe aan de tabel).

    | Gebruikersnaam | Primaire groep | Secundaire groep |
    | :---           | :---           | :---             |
    | `bob`          | `sporten`      | `judo`           |
    | `carol`        | `sporten`      | `zwemmen`        |
    | `daniel`       | `sporten`      | `judo`           |
    | `eva`          | `sporten`      | `zwemmen`        |

    - Geef de gebruikte commando's om de gebruikers aan te maken en ook om te verifiëren of dit correct gebeurd is:

        ```
        $ COMMANDO
        UITVOER
        $ COMMANDO
        UITVOER
        ...
        ```

    - Verwijder nu de *groep* `alice` en controleer.

        ```
        $ COMMANDO
        UITVOER
        ```

    - Gebruiker `daniel` gaat een tijdje niet meer sporten. Zorg er voor dat deze gebruiker tot nader order geen toegang meer kan hebben tot het systeem (zonder het wachtwoord of de gebruiker te verwijderen!).

        ```
        $ COMMANDO
        UITVOER
        ```

    - Hoe kan je controleren dat `daniel` inderdaad geen toegang meer heeft tot het systeem? In welk bestand kan dat en hoe zie je daar dan dat het account afgesloten is?

        ```
        $ COMMANDO
        UITVOER
        ```

    - Gebruiker `daniel` komt terug naar de sportclub. Geef hem opnieuw toegang tot het systeem.

        ```
        $ COMMANDO
        UITVOER
        ```

    - Gebruiker `eva` stopt helemaal met sporten. Verwijder deze gebruiker, maar doe dit zorgvuldig: zorg er in het bijzonder voor dat ook haar homedirectory verwijderd wordt.

        ```
        $ COMMANDO
        UITVOER
        ```

7. Log aan als de gebruiker `carol`

    ```
    $ COMMANDO
    UITVOER
    ```

    - Controleer of je in de “thuismap” bent van deze gebruiker. Maak onder deze map een bestand `test` aan door middel van het commando `touch`.

        ```
        $ COMMANDO
        UITVOER
        ```

    - Probeer nu als gebruiker `carol` je te verplaatsen naar de “thuismap” van `alice`.

        ```
        $ COMMANDO
        UITVOER
        ```

    - Kan je de inhoud van de mappen binnen de thuismap van `alice` bekijken?

        ```
        $ COMMANDO
        UITVOER
        ```

    - Probeer nu als `carol` onder de “thuismap” van `alice` ook een bestand `test` te maken. Lukt dit? Kan je dit verklaren?

        ```
        $ COMMANDO
        UITVOER
        ```

