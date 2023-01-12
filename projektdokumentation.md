# Projekt-Dokumentation

Villiger

| Datum    | Version | Zusammenfassung                                              |
| -----    | ------- | ------------------------------------------------------------ |
| 12.01.23 | 0.0.1   | Ich habe die Punkte 1 -5 in der Projekt-Dokumentation ausgefüllt. |
|       | 0.0.2   |                                                              |
|       | 0.0.3   |                                                              |
|       | 0.0.4   |                                                              |
|       | 0.0.5   |                                                              |
|       | 0.0.6   |                                                              |
|       | 1.0.0   |                                                              |

# 0 Ihr Projekt

Ein Glücksradspiel, in dem man verschiedene Wörter schreiben kann.

# 1 Analyse

✍️ Beschreiben Sie, auf welchem Tier Sie die dynamischen Elemente der Anwendung unterbringen möchten:

* Tier 1 (Presentation): Glücksrad, Rate-Wand und Eingabefelder, Kontostand und Lebenspunkte.
* Tier 2 (Webserver): Eingabevalidierung, Weiterleitung der Eingabedaten, Vergleich des geratenen Buchstabens mit der Datenbank.
* Tier 3 (Application Server): , Guthaben gutschreiben, Highscorelisteneintrag tätigen.
* Tier 4 (Dataserver): Datenbanken mit Wörtern / Sprichwörtern, Benutzerdaten und Highscores verwalten.

# 2 Technologie

Python

# 3 Datenbank

MySQL. Python greift dabei mittels eines "MySQL driver" auf die Datenbank zu. Vermutlich werde ich dazu den "MySQL Connector" verwenden.

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

 

# 4.2 Testfälle

| TC-№ | Vorbereitung               | Eingabe | Erwartete Ausgabe |
| ---- | -------------------------- | ------- | ----------------- |
| 1.1  | Applikation ist gestartet. | 1. Auf "Als Administrator anmelden" klicken.<br>2. Benutzername "admin" und Passwort "admin1234" eingeben. | Der Adminmodus sollte nun gestartet sein. |
| 2.1  | Applikation ist gestartet. | 1. Auf "Als Administrator anmelden" klicken.<br>2. Benutzername "admin" und Passwort "admin1234" eingeben.<br>3. Auf "Datenbank bearbeiten" klicken.<br>4. Drei neue Rätselwörter namens "Hoppla", "Ups" und "Ehhh" anlegen.<br>5. Das Wort "Hoppla" zu "Hopla" verändern.<br>6. Das Wort "Ehhh" löschen. Auf "Datenbank ansehen" klicken. | In der Datenbank sollten die Wörter "Hopla" und "Ups" vorhanden sein. |
| 3.1  | Applikation ist gestartet. | 1. Auf "Als Administrator anmelden" klicken.<br>2. Benutzername "admin" und Passwort "admin1234" eingeben.<br>3. Auf "Datenbank bearbeiten" klicken.<br>4.Eine neue Kategorie namens "Test" anlegen.<br>5. Ein neues Wort "UFF" zur Kategorie hinzufügen.<br>6. Auf "Datenbank ansehen" klicken. | In der Datenbank sollte eine Kategorie namens "Test" vorhanden sein die das Wort "UFF" enthält. |
| 4.1  | Applikation ist gestartet. | 1.         |                   |
| 5.1  | Applikation ist gestartet. |         |                   |
| 6.1  | Applikation ist gestartet. |         |                   |
| 7.1  | Applikation ist gestartet. |         |                   |
| 8.1  | Applikation ist gestartet. |         |                   |
| 9.1  | Applikation ist gestartet. |         |                   |
| 10.1 | Applikation ist gestartet. |         |                   |


✍️ Die Nummer hat das Format `N.m`, wobei `N` die Nummer der User Story ist, die der Testfall abdeckt, und `m` von `1` an nach oben gezählt. Beispiel: Der dritte Testfall, der die zweite User Story abdeckt, hat also die Nummer `2.3`.

# 5 Prototyp

✍️ Erstellen Sie Prototypen für das GUI (Admin-Interface und Quiz-Seite).

# 6 Implementation

✍️ Halten Sie fest, wann Sie welche User Story bearbeitet haben

| User Story | Datum | Beschreibung |
| ---------- | ----- | ------------ |
| ...        |       |              |

# 7 Projektdokumentation

| US-№ | Erledigt? | Entsprechende Code-Dateien oder Erklärung |
| ---- | --------- | ----------------------------------------- |
| 1    | ja / nein |                                           |
| ...  |           |                                           |

# 8 Testprotokoll

✍️ Fügen Sie hier den Link zu dem Video ein, welches den Testdurchlauf dokumentiert.

| TC-№ | Datum | Resultat | Tester |
| ---- | ----- | -------- | ------ |
| 1.1  |       |          |        |
| ...  |       |          |        |

✍️ Vergessen Sie nicht, ein Fazit hinzuzufügen, welches das Test-Ergebnis einordnet.

# 9 `README.md`

✍️ Beschreiben Sie ausführlich in einer README.md, wie Ihre Applikation gestartet und ausgeführt wird. Legen Sie eine geeignete Möglichkeit (Skript, Export, …) bei, Ihre Datenbank wiederherzustellen.

# 10 Allgemeines

- [ ] Ich habe die Rechtschreibung überprüft
- [ ] Ich habe überprüft, dass die Nummerierung von Testfällen und User Stories übereinstimmen
- [ ] Ich habe alle mit ✍️ markierten Teile ersetzt
