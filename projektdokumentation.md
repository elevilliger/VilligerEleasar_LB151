# Projekt-Dokumentation

Villiger

| Datum    | Version | Zusammenfassung                                                   |
| -----    | ------- | ------------------------------------------------------------------|
| 12.01.23 | 0.0.1   | Ich habe die Punkte 1 -5 in der Projekt-Dokumentation ausgefüllt. |
| 19.01.23 | 0.0.2   | Ich habe das Login implementiert.                                 |
| 26.01.23 | 0.0.3   | Ich habe das ungefähre GUI implementiert.                         |
| 16.02.23 | 0.0.4   | Ich habe die Ranglisten-Anzeige implementiert.                    |
| 23.02.23 | 0.0.5   | Ich habe die Satz-Anzeige implementiert.                          |
| 02.03.23 | 1.0.0   | Ich habe die Punkte 6 - 9 in der Projekt-Dokumentation ausgefüllt.|

# 0 Ihr Projekt

Ein Glücksradspiel, in dem man verschiedene Sätze / Wörter erraten muss.

# 1 Analyse

* Tier 1 (Presentation): Glücksrad, Rate-Wand und Eingabefelder, Kontostand und Lebenspunkte.
* Tier 2 (Webserver): Eingabevalidierung, Weiterleitung der Eingabedaten, Vergleich des geratenen Buchstabens mit der Datenbank.
* Tier 3 (Application Server): , Guthaben gutschreiben, Highscorelisteneintrag tätigen.
* Tier 4 (Dataserver): Datenbanken mit Wörtern / Sprichwörtern, Benutzerdaten und Highscores verwalten.

# 2 Technologie

Mein Projekt möchte ich mittels HTML, CSS & JSF implementieren.

# 3 Datenbank

Für die Datenbank werde ich MySQL verwenden. Diesen werde ich mit JSF verbinden.

# 4.1 User Stories

✍️ Formulieren Sie klare Anforderungen in der Form von User Stories (*„als … möchte ich … damit …“*) und zu jeder Anforderung mindestens einen dazugehörigen Testfall (in Kapitel 4.2). 

✍️ Formulieren Sie weitere, eigene Anforderungen und Testfälle, wie Sie Ihre Applikation erweitern möchten. Geben Sie diesen statt einer Nummer einen Buchstaben (`A`, `B`, etc.)

| US-№ | Verbindlichkeit | Typ        | Beschreibung                       |
| ---- | --------------- | ---------- | ---------------------------------- |
| 1    | Muss            | Qualität      | Als ein Administrator möchte ich mittels Benutzernamen und Passwort anmelden können, damit sich nicht jede beliebige Person als Administrator ausgeben kann. |
| 2    | Muss            | Funktional    | Als ein Administrator möchte ich Phrasen und Rätselwörtern anlegen, ändern und löschen können, damit die Datenbank ergänzt oder verbessert werden kann. |
| 3    | Muss            | Qualität      | Als ein Administrator möchte ich Kategorien anlegen können und jedes Wort bzw. jede Frage einer Kategorie zuordnen können, damit die Datenbank schön gegliedert ist. |
| 4    | Muss            | Funktional    | Als ein Administrator möchte ich einzelne Einträge der Highscore-Liste löschen können, damit ungültige Einträge entfernt werden können. |
| 5    | Muss            | Qualität      | Als ein Kandidat möchte ich einen Namen eingeben können, damit dieser dann auf der Rangliste angezeigt werden kann. |
| 6    | Muss            | Randbedingung | Als ein Kandidat möchte ich jederzeit meinen Kontostand und meine Lebenspunkte sehen, damit ich über den aktuellen Spielstand informiert bin. |
| 7    | Muss            | Qualität      | Als ein Kandidat möchte ich, dass mein Rang, mein Name, der Zeitpunkt des Spiels, der Geldbetrag und die Anzahl Spielrunden in der Rangliste angezeigt werden, damit ich mich mit anderen Kandidaten vergleichen kann. |
| 8    | Muss            | Qualität      | Als ein Kandidat möchte ich, dass die Rangliste nach Rang, welcher durch die Höhe des Geldbetrags bestimmt wird, aufsteigend sortiert wird, damit ich eine übersichtliche Rangliste habe. |
| 9    | Muss            | Qualität      | Als ein Kandidat möchte ich dass mir Rätsel-Wörter und Phrasen nur einmal pro Spiel gestellt werden, damit die Spielbedingungen fair sind. |
| 10   | Muss            | Funktional    | Als ein Kandidat möchte ich jederzeit spielen oder aufhören können, damit ich die Kontrolle über die Dauer des Spiels habe. |
| A    | Muss            | Randbedingung | Als ein Programmierer möchte ich mein Spiel mittels JSF implementieren, damit ich Spass beim Implementieren habe. |
| B    | Muss            | Randbedingung | Als ein Kandidat möchte, dass das Spiel übersichtlich designt ist, damit ich mich gut zurechtfinden kann. |

 

# 4.2 Testfälle

| TC-№ | Vorbereitung               | Eingabe | Erwartete Ausgabe |
| ---- | -------------------------- | ------- | ----------------- |
| 1.1  | Applikation ist gestartet. | 1. Auf "Als Administrator anmelden" klicken.<br>2. Benutzername "admin" und Passwort "admin1234" eingeben. | Der Adminmodus sollte nun gestartet sein. |
| 2.1  | Applikation ist gestartet. | 1. Auf "Als Administrator anmelden" klicken.<br>2. Benutzername "admin" und Passwort "admin1234" eingeben.<br>3. Drei neue Rätselwörter namens "Hoppla", "Ups" und "Ehhh" anlegen.<br>4. Das Wort "Hoppla" zu "Hopla" verändern.<br>5. Das Wort "Ehhh" löschen. Auf "Datenbank ansehen" klicken. | In der Datenbank sollten die Wörter "Hopla" und "Ups" vorhanden sein. |
| 3.1  | Applikation ist gestartet. | 1. Auf "Als Administrator anmelden" klicken.<br>2. Benutzername "admin" und Passwort "admin1234" eingeben.<br>3.Eine neue Kategorie namens "Test" anlegen.<br>4. Ein neues Wort "UFF" zur Kategorie hinzufügen.<br>5. Auf "Datenbank ansehen" klicken. | In der Datenbank sollte eine Kategorie namens "Test" vorhanden sein die das Wort "UFF" enthält. |
| 4.1  | Applikation ist gestartet. | 1. Auf "Als Administrator anmelden" klicken.<br>2. Benutzername "admin" und Passwort "admin1234" eingeben.<br>3. Auf "Highscore-Liste bearbeiten" klicken.<br>4. Einen beliebigen Eintrag löschen. | Der Eintrag sollte aus der Highscore-Liste entfernt worden sein. |
| 5.1  | Applikation ist gestartet. | 1. Ein Spiel starten.<br>2. Auf "Spiel beenden" klicken.| Es sollte ein Fenster erscheinen, in dem der Namen eingegeben werden kann. |
| 6.1  | Applikation ist gestartet. | 1. Ein Spiel starten. | Auf dem Bildschirm sollten der aktuelle Kontostand und die Lebenspunkte angezeigt werden. |
| 7.1  | Applikation ist gestartet. | 1. Ein Spiel starten.<br>2. Auf "Spiel beenden" klicken.<br>3. Den Namen "Trump" eingeben.<br>4. Auf "Rangliste" klicken. | Auf der Rangliste sollte ein Eintrag mit Rang, dem Namen "Trump", der aktuelle Zeitpunkt, der letzte Geldbetrag und die Anzahl Spielrunden angezeigt werden. |
| 8.1  | Applikation ist gestartet. | 1. Auf "Rangliste" klicken. | Die Rangliste sollte aufsteigend nach Rang / Höhe des Geldbetrags sortiert angezeigt werden. |
| 9.1  | Applikation ist gestartet. | 1. Ein Spiel starten.<br>2. Einige Rätsel-Wörter / Phrasen beantworten. | Keine der Rätsel-Wörter / Phrase sollten zwei Mal vorkommen. |
| 10.1 | Applikation ist gestartet. | 1. Ein Spiel starten.<br>2. Das Spiel beenden. | Das Spiel sollte beendet werden. |

# 5 Prototyp

Admin-Interface
![grafik](https://user-images.githubusercontent.com/89772768/212046158-7e927f4c-82bc-4256-9949-5a0e1dc24d7b.png)

Quiz-Seite

![grafik](https://user-images.githubusercontent.com/89772768/212055737-a4ccfd96-27b7-4dcc-93dd-1ea634b84905.png)


# 6 Implementation

| User Story | Datum | Beschreibung |
| ---------- | ----- | ------------ |
| 1          | 19.01.23 | keine Probleme aufgetreten. |
| 5          | 26.01.23 | keine Probleme aufgetreten. |
| 6          | 26.01.23 | keine Probleme aufgetreten. |
| 8          | 16.02.23 | keine Probleme aufgetreten. |
| 10         | 16.02.23 | keine Probleme aufgetreben. |

# 7 Projektdokumentation

| US-№ | Erledigt? | Entsprechende Code-Dateien oder Erklärung |
| ---- | --------- | ----------------------------------------- |
| 1    | ja        | "Web Pages/login.xhtml" & "Source Packages/ch.bbbaden.login/LoginFilter.Java & LoginUserBean" |
| 2    | nein      | Nicht genügend Zeit.                      |
| 3    | nein      | Nicht genügend Zeit.                      |
| 4    | nein      | Nicht genügend Zeit.                      |
| 5    | ja        | "Web Pages/game.xhmtl" Z. 20              |
| 6    | ja        | "Web Pages/game.xhtml" Z. 18 & 19         |
| 7    | nein      | Nicht genügend Zeit.                      |
| 8    | ja        | "Web Pages/ranklist.xhtml"                |
| 9    | nein      | Nicht genügend Zeit, Sätze können mehrfach vorkommen. |
| 10   | ja        | "Web Pages/game.xhtml" Z. 20              |

# 8 Testprotokoll

https://clipchamp.com/watch/AsV4AMVIDuY

| TC-№ | Datum | Resultat | Tester |
| ---- | ----- | -------- | ------ |
| 1.1  | 02.03.23 | OK    | E. Villiger |
| 2.1  | 02.03.23 | N. OK | E. Villiger |
| 3.1  | 02.03.23 | N. OK | E. Villiger |
| 4.1  | 02.03.23 | N. OK | E. Villiger |
| 5.1  | 02.03.23 | OK    | E. Villiger |
| 6.1  | 02.03.23 | OK    | E. Villiger |
| 7.1  | 02.03.23 | N. OK | E. Villiger |
| 8.1  | 02.03.23 | OK    | E. Villiger |
| 9.1  | 02.03.23 | N. OK | E. Villiger |
| 10.1 | 02.03.23 | OK    | E. Villiger |

Dieses Programm ist sehr unvollständig. Nicht mal die grundlegenden-Funktionnen des Spiels wurden implementiert wodurch auch viele der Testfälle nicht durchgeführt werdenn konnten.

# 9 `README.md`

Siehe in diesem git-Projekt im main-Branch.
