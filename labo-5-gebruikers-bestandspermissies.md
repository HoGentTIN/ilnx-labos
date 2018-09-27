# Labo 5: Bestandspermissies

Als je gebruik maakt van andere bronnen (bv. blog-artikel of HOWTO die je op het Internet vond), voeg die dan toe aan het einde van dit document. Zo kan je het later terug vinden.

Maak ter voorbereiding zeker de oefeningen in Linux Fundamentals (Paul Cobbaut) over dit onderwerp (pp. 222 en 228).


## Algemene permissies

Geef in de volgende oefeningen telkens het commando dat nodig is om de taak uit te voeren en ook het resultaat.

1. Log in als gewone gebruiker. Wat is de waarde van umask?

    ```
    $ COMMANDO
    UITVOER
    ```

2. Maak een directory `oefenenMetPermissies` aan. Welke octale permissies verwacht je voor deze nieuwe directory?

    ```
    $ COMMANDO
    UITVOER
    ```

3. Controleer dit door de *symbolische* permissies op te vragen.

    ```
    $ COMMANDO
    UITVOER
    ```

4. Controleer of de symbolische waarden en octale waarden overeen komen!
5. Stel nu de umask waarde zo in dat niemand permissies heeft op de bestanden en directories die je aanmaakt, behalve jijzelf.

    ```
    $ COMMANDO
    UITVOER
    ```

6. Maak nu een bestand aan met de naam `vanmij`, in de directory `oefenenMetPermissies` met als inhoud de tekst: `echo "Waarschuwing: eigendom van ${USER}!"` Schrijf neer hoe je dit bestand gemaakt hebt. Controleer de permissies; schrijf ze neer en was dit wat je verwachtte? Verklaar!

    ```
    $ COMMANDO
    UITVOER
    ```

7. Verander nu de permissies van het bestand `vanmij` zodat je zelf het bestand kan uitvoeren. Geef het gebruikte commando (op de octale manier) en test het resultaat.

    ```
    $ COMMANDO
    UITVOER
    ```

8. Log in als de gebruiker `alice` (als je deze niet meer hebt, maak je die aan en voorzie de gebruiker van een eenvoudig paswoord), maar zorg dat je niet verandert van directory. Kan `alice` het bestand `vanmij` uitvoeren? Verklaar!

    ```
    $ COMMANDO
    UITVOER
    ```

9. Verander nu de permissies van het bestand vanmij zodat iedereen het bestand kan uitvoeren. Geef het gebruikte commando (op de symbolische manier) en test het resultaat.

    ```
    $ COMMANDO
    UITVOER
    ```

## Geavanceerde permissies

1. Zoek alle bestanden in het systeem waar de SUID-permissie op ingesteld staat. Schrijf het resultaat in een bestand met de naam `suidBestanden. Schrijf de fouten weg naar een `foutenBestand`. Doe dit in één commandolijn. (Tip: gebruik het commando `find` en zoek in de manpages naar de geschikte opties).

    ```
    $ COMMANDO
    UITVOER
    ```

2. Controleer het resultaat door een bestand te nemen uit `suidBestanden` en de permissies op te vragen van dat bestand.

    ```
    $ COMMANDO
    UITVOER
    ```

3. Check of het programmabestand `/usr/bin/passwd` in het bestand `suidBestanden` aanwezig is. Schrijf het gebruikte commando op. Is het aanwezig?

    ```
    $ COMMANDO
    UITVOER
    ```

## Geavanceerde permissies: setGID en de *sticky bit*

1. Ga naar de directory `oefenenMetPermissies`, als gewone gebruiker (dus niet als `root`) en kopieer het bestand `/etc/hosts` daar naartoe.

    ```
    $ COMMANDO
    UITVOER
    ```

2. Verander nu de permissies van het bestand `hosts` in directory `oefenenMetPermissies` als volgt: SGID aan, `rx` voor *others*, `rw` voor *group* en geen permissies voor de eigenaar (merk op dat deze combinatie van permissies geen praktisch nut heeft!). Geef het gebruikte commando en ook het commando om te controleren of de permissies juist ingesteld zijn.

    ```
    $ COMMANDO
    UITVOER
    ```

3. Kan de eigenaar nu het bestand bekijken? Waarom wel of niet? Noteer hoe je dit controleert:

    ```
    $ COMMANDO
    UITVOER
    ```

4. Kan de eigenaar de permissies wijzigen? Controleer.

    ```
    $ COMMANDO
    UITVOER
    ```

5. Kan de eigenaar het bestand verwijderen? Controleer.

    ```
    $ COMMANDO
    UITVOER
    ```

Kopieer als je eigen gebruiker (niet als root!) nu opnieuw het bestand `/etc/hosts` in het directory `oefenenMetPermissies` en pas de permissies opnieuw aan zoals eerder voorgeschreven. Zorg dat gebruiker `alice` lid is van de groep die groepseigenaar is van het bestand `hosts` in directory `oefenenMetPermissies`. Switch nu naar gebruiker alice.

1. Kan alice nu het bestand bekijken? Controleer.

    ```
    $ COMMANDO
    UITVOER
    ```

2. Kan alice de permissies wijzigen? Controleer.

    ```
    $ COMMANDO
    UITVOER
    ```

3. Kan alice het bestand verwijderen? Is dit de bedoeling? Controleer.

    ```
    $ COMMANDO
    UITVOER
    ```

4. Stel nu de sticky-bit in op het directory oefenenMetPermissies. Geef het geschikte commando en controleer het resultaat.

    ```
    $ COMMANDO
    UITVOER
    ```

## Eigenaars en groepseigenaars veranderen

1. Maak als `root` onder `/srv/` twee directories aan met de naam `groep/verkoop` en `groep/inkoop`. Maak ook 2 groepen aan met de namen `verkoop` en `inkoop`. Maak twee gebruikers aan, `margriet` met primaire groep `verkoop` en `roza`, die als primaire groep `inkoop` heeft. Zorg dat de groepen eigenaar zijn van de overeenkomstige directories en dat `margriet` eigenaar is van directory `verkoop` en `roza` van het directory `inkoop`. Geef de gebruikte commando’s en controleer:

    ```
    # COMMANDO
    UITVOER
    ...
    # ls -l groep/
    total 0
    drwxr-xr-x. 2 roza     inkoop  6 Sep 22 22:23 inkoop
    drwxr-xr-x. 2 margriet verkoop 6 Sep 22 22:23 verkoop
    ```

2. Zorg ervoor dat gebruikers en groepen uit de vorige stap alle permissies hebben. Geef het geschikte commando en controleer.

    ```
    $ COMMANDO
    UITVOER
    ```

3. Voeg een gebruiker, vb `alice`, toe aan de groep `inkoop` en `verkoop` en controleer. Geen van beide groepen zijn primair.

    ```
    $ COMMANDO
    UITVOER
    ```

4. Log in als `alice` en ga naar de directory verkoop. Laat de gebruiker hier een leeg bestand, `bestand1`, aanmaken in de directory verkoop. (Indien je hier problemen ondervindt, log dan in via een andere terminalvenster).

    ```
    $ COMMANDO
    UITVOER
    ```

5. Wie is nu eigenaar van `bestand1` en wie de groepseigenaar?

    ```
    $ COMMANDO
    UITVOER
    ```

6. Zorg er nu voor dat de groepseigenaar van de directory `verkoop` automatisch de groepseigenaar wordt van alle bestanden en directories die onder `verkoop` gemaakt worden. Geef de gebruikte commando’s.

    ```
    $ COMMANDO
    UITVOER
    ```

7. Doe hetzelfde voor de directory `inkoop`. Geef de gebruikte commando’s:

    ```
    $ COMMANDO
    UITVOER
    ```

8. Verander opnieuw naar gebruiker `alice` en laat deze gebruiker een leeg `bestand2` aanmaken in de directory `verkoop`. Geef de gebruikte commando’s:

    ```
    $ COMMANDO
    UITVOER
    ```

9. Wie is nu eigenaar van `bestand2` en wie groepseigenaar?

    ```
    $ COMMANDO
    UITVOER
    ```

10. Laat nu gebruiker `margriet` een leeg bestand `bestand3` aanmaken. Controleer de eigenaar van `bestand3` en de groepseigenaar.

    ```
    $ COMMANDO
    UITVOER
    ```

11. Laat nu gebruiker `alice` `bestand3` verwijderen. Lukt dit?

    ```
    $ COMMANDO
    UITVOER
    ```

12. Zorg er nu voor dat de gebruikers elkaars bestanden niet kunnen verwijderen. Als de gebruiker echter eigenaar is van het betreffende directory mag dit wel. Leg uit hoe je dit doet en controleer. Schrijf je gevolgde procedure op.

    ```
    $ COMMANDO
    UITVOER
    ```

## Gebruikte bronnen
