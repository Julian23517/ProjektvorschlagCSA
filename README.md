# Projektvorschlag Dofus Ressourcenplaner

**Hochschule Worms CSA 151 WS 2018/19**

Gruppe "Wir haben Gruppennummern?"

Jennifer Nguyen
inf2735@hs-worms.de
Matrikelnummer: 672286

Julian Schulzeck
inf2834@hs-worms.de
Matrikelnummer: 672912

---

## Abstract

Da wir beide das Online MMORPG "Dofus" spielen, sind wir auf die Idee gekommen einen Ressourcenplaner für das Spiel umzusetzen.
Nun was ist denn ein "Ressourcenplaner" für dieses "Dofus"?

Dazu müssen wir kurz einen Teilaspekt von Dofus näher erläutern und zwar das Herstellen von Gegenständen.
Es gibt 13 Berufe bei denen man Gegenstände herstellen kann. Jeder Beruf hat seine jeweiligen Gegenstandstypen die er herstellt.
Welche Gegenstände man herstellen kann, hängt von dem erreichten Level in dem jeweiligen Beruf ab (Min Level: 1, Max Level: 200 bei jeweils allen Berufen) und natürlich
ob man die benötigten Ressourcen für den Gegenstand besitzt. Die Ressourcen können ebenfalls Gegenstände sein, die man herstellen muss oder auch einfach
Ressourcen, die man von Monstern bekommt. Um einen Beruf zu Leveln, muss man Gegenstände herstellen.

Wenn man nun einen Beruf von 1 auf Level 200 Leveln möchte, muss man ziemlich viele Gegenstände herstellen und man verliert leicht den Überblick,
welche Ressourcen man jetzt schon hat und welche nicht. Gerade wenn man für die Herstellung eines Gegenstandes Gegenstände benötigt, die ebenfalls hergestellt werden müssen.

Um das ganze besser planbar und übersichtlich zu machen, wollen wir den Ressourcenplaner entwerfen. Der Benutzer kann also unserem Programm sagen, welche Gegenstände er gerne herstellen
würde, und unser Programm erstellt automatisch eine Liste von allen Ressourcen, die benötigt werden um alle Gegenstände auf der Liste herzustellen, in einer übersichtlichen Liste.
Wie dieser Clientseitig umgesetzt werden soll, wird im Abschnitt "Abstract Client" näher beschrieben.


## Abstract Client
Verantwortlicher: Jennifer Nguyen

### Menüpunkt "Übersicht"

Nachdem der Benutzer sich Registriert und eingeloggt hat, befindet er sich auf dem Menüpunkt "Übersicht". Dort sieht er eine Übersicht von allen herstellbaren Gegenständen
im Spiel. Diese kann er nach Level und/oder Beruf filtern, oder auch nach einem bestimmten Gegenstand suchen.
Für jeden der angezeigten Gegenständen hat er nun über Buttons die Möglichkeit, sich entweder die Rezeptur anzeigen zu lassen (also die Ressourcen die zur Herstellung des Gegenstandes
benötigt werden), oder ihn in eine Liste hinzuzufügen. Wenn der Benutzer noch keine Liste angelegt hat, oder es in einer neuen Liste speichern möchte, hat er hier gleich die
Möglichkeit eine neue Liste anzulegen.

### Menüpunkt "Meine Listen"

Hier hat der Benutzer eine Übersicht von all seinen erstellten Listen. Über einen Button hat der Benutzer die Möglichkeit die jeweiligen Listen zu löschen.
Wenn er auf eine seiner Listen klickt, wird ihm der Reiter Gegenstand (auf dem er sich direkt befindet) und der Reiter Ressourcen angezeigt.

#### Reiter "Gegenstand"

Hier wird eine Übersicht der in der Liste hinzugefügten Items angezeigt. Pro Item wird Anzahl (wie oft soll der Gegenstand hergestellt werden?), Level des Gegenstandes,
der Beruf der den entsprechenden Gegenstand herstellen kann und die Ressourcen, die für den Gegenstand benötigt werden, angezeigt.

#### Reiter "Ressourcen"

Hier hat der Benutzer eine Übersicht über alle Ressourcen die er benötigt um die auf der Liste hinzugefügten Items herzustellen. Es ist möglich die Anzahl an bereits gesammelten
Ressourcen einzutragen und wenn die benötigte Anzahl einer Ressource erreicht wurde, wird dies kenntlich gemacht. So hat der Benutzer eine gute Übersicht was er bereits gesammelt hat
und was er noch besorgen muss. Gegenstände die eine eigene Rezeptur benötigen, werden ebenfalls gekennzeichnet und über einen klick, werden die dafür benötigten
Gegenstände mit auf die Liste geschrieben.

## Wireframe


## Mobil

### Login

![](Mobil_Mockup/Anmeldung.png)

### Registrierung

![](Mobil_Mockup/Registrierung.png)

### Übersicht

![](Mobil_Mockup/Übersicht.png)

### Übersicht Filter
Das ist der Filter wenn man bei Übersicht auf "Filter" klickt

![](Mobil_Mockup/ÜbersichtFilter.png)

### Meine Listen

![](Mobil_Mockup/MeineListeÜbersicht.png)

### Meine Liste - Reiter Gegenstand

![](Mobil_Mockup/MeineListeGegenstand.png)

### Meine Listen - Reiter Ressourcen

![](Mobil_Mockup/MeineListeRessourcen.png)

## Desktop

### Anmeldung

![](Web_Mockup/Anmeldung.png)

### Registrierung

![](Web_Mockup/Registierung.png)

### Übersicht

![](Web_Mockup/Übersicht.png)

### Meine Listen

![](Web_Mockup/MeineListeÜbersicht.png)

### Meine Liste - Reiter Gegenstand

![](Web_Mockup/MeineListe.png)

### Meine Listen - Reiter Ressourcen

![](Web_Mockup/MeineListenRessourcen.png)


## Abstract Server
Verantwortlicher: Julian Schulzeck

Die Hauptaufgabe des Server wird es sein, die Datenbank, die wir mit SQLite 3 umsetzen wollen, zu verwalten und über eine API die Daten an den Client zu liefern.
Um die enorm große Datenmenge (aktuell rund 5000 herstellbare Gegenstände und 2710 unterschiedliche Ressourcen) nicht per Hand in die Datenbank eintragen zu müssen, werde ich ein
"Hilfsprogramm" mit Java (und der Bibliothek Selenium) schreiben, welche die Datenbank erstellt indem es die Daten von der Website Crawled. Wir haben uns gegen ein "echtzeit crawlen"
der Daten entschieden, da uns keine öffentliche API für die Dofus Website zur Verfügung steht und zu viele Anfragen an den Dofus Server einen temporären "Bann" mit sich zieht.


## UML

Hier ein UML Diagramm von den Objekten, die wir benötigen werden.
Ein **User** Objekt hat eine Liste von beliebig vielen **ItemListe** Objekten. Eine **ItemListe** enthält beliebig viele **Item** Objekte. Ein **Item** Objekt besitzt keine (wenn das Item nicht
herstellbar ist) bis eine **Rezeptur**. Ein **Item** besitzt außerdem die Attribute name, id, level, beruf, icon und anzahlBenoetigt. "level" bildet das Level des Items ab, "beruf" speichert
den Beruf mit dem man den Gegenstand herstellen kann und "icon" speichert das .png zu dem jeweiligen Item. Eine **Rezeptur** besteht aus eins bis acht **RezepturItem** Objekten.
**RezepturItem** erbt alle Attribute von **Item** und hat zusätzlich noch "anzahlBenoetigt" als Attribut, welches beschreibt, wie oft das Item für die Rezeptur benötigt wird.

![](diagrams/uml_diagramm_dofus_ressourcenplaner.svg)

## ER-Diagramm

Auf der Datenbank werden die Daten folgendermaßen dargestellt:

![](diagrams/er_diagramm_dofus_ressourcenplaner.svg)

## Relationales Datenbankschema

Aus dem ER-Diagramm ergibt sich der folgende Relationale Entwurf:
(Die Fettgedruckten Attribute stellen die Primärschlüssel dar)

### Entity-Typen

Users: **username: String**, passwort: String

ItemListen: **itemListeId: int**, name: String

Items: **itemId: int**, name: String, level: int, beruf: String, icon: String

### Relationship-Typen

besitztListe: **username: String**, **itemListeId: int**

enthaeltItems: **itemListeId: int**, **itemId: int**

hatAlsRezeptur: **itemId: int**, **rezepturItemId: int**, anzahlBenoetigt: int


## API-Beschreibung
Die Api bietet insgesamt fünf GET Befehle, zwei POST Befehle und ein DELETE Befehl. Die Entsprechenden Objekte sind unter dem Abschnitt "Template Object" zu finden.

### `GET /user`
Auf dieser Route liefert der Server alle User Objekte, die in der Datenbank gespeichert sind`

### `GET /user/:username`
Auf dieser Route nimmt der Server einen usernamen entgegen.
Als Antwort liefert er das User Objekt mit dem entsprechenden usernamen.

### `GET /user/:username/itemlisten`
Auf dieser Route nimmt der Server einen usernamen entgegen.
Als Antwort liefert er alle ItemListe Objekte, die der entsprechende User gespeichert hat.

### `GET /items`
Auf dieser Route liefert der Server alle Item Objekte, die in der Datenbank gespeichert sind`

### `Get /items/:itemId`
Auf dieser Route nimmt der Server eine itemId entgegen.
Als Antwort liefert er das Item Objekt mit der entsprechenden itemId`

### `POST /user`
Auf dieser Route nimmt der Server ein User Objekt entgegen und trägt es in die Datenbank ein falls es den User noch nicht gibt.
Als Antwort liefert er ein taskSucceeded Objekt.
Wenn der username des übergebenen Users bereits in der Datenbank existiert, ist success = false ansonsten true.

### `POST /user/:username/itemliste`
Auf dieser Route nimmt der Server ein usernamen und ein ItemListe Objekt entgegen und trägt es in die Datenbank ein falls der User existiert.
Als Antwort liefert er ein taskSucceeded Objekt.
Wenn der username des übergebenen Users nicht existiert, ist success = false ansonsten true.

### `DELETE /user/:username`
Auf dieser Route nimmt der Server einen usernamen entgegen.
Falls der username existiert wird der Entsprechende User mit samt seinen Daten (ItemListen) aus der Datenbank gelöscht.
Als Antwort liefert der Server ein taskSucceeded Objekt.
Wenn der username des übergebenen Users nicht existiert, ist success = false ansonsten true.

### Template Object

#### Template Object User
Enthält username und Passwort

```javascript
{
  username: "katzenlover",
  passwort: "felixFelicis"
}
```

#### Template Objekt ItemListe
Enthält name der ItemListe und alle itemIds von Items die in der Liste gespeichert wurden

```javascript
{
  name: "SchneiderLeveln",
  items: [6,7,42]
}
```

#### Template Objekt Item
Enthält itemId, name, level, beruf der den Gegenstand herstellt, den namen des Icon.png und die RezepturItems.
Die RezepturItems sind folgendermaßen aufgebaut: {itemId, anzahlBenoetigt}.
Also benötigt man für die Herstellung unseres Template Objekt 5 x das Item mit id = 2, 10 x das Item mit id = 4 und 1x das Item mit id = 42.

```javascript
{
  itemId: 1,
  name: "Gelano",
  level: 60,
  beruf: "Juwelier",
  icon: "gelanoIcon.png",
  rezepturItems:[{2,5},{4,10},{42,1}]
}
```

#### Template Objekt taskSucceeded
Dieses Objekt wird bei den POST und DELETE befehlen zurückgegeben. Dabei gibt "success" an, ob die Aufgabe des entsprechenden Befehls erfolgreich ausgeführt werden konnte.

```javascript
{
  success: true
}
```

## Aufwandsschätzungen

### Frontend

Verantwortlicher: Jennifer Nguyen

#### Projektvorbereitung 


| Aufgabe                                       | Zeit in Std |
|-----------------------------------------------|------------:|
| Projektthema überlegen + grobe Funktionen     |  8          |
| Wireframe Mobil Registierung + Login          |  1          |
| Wireframe Mobil Übersicht + Filter            |  1          |
| Wireframe Mobil Meine Liste - Übersicht       |  1          |
| Wireframe Mobil Meine Liste - Gegenstände     |  1          |
| Wireframe Mobil Meine Liste - Ressourcen      |  1          |
| Wireframe Web Registrierung + Login           |  1          |
| Wireframe Web Übersicht                       |  1          |
| Wireframe Web Meine Liste - Übersicht	        |  1          |
| Wireframe Web Meine Liste - Gegenstände       |  1          |
| Wireframe Web Meine Liste - Ressourcen        |  1          |
| Aufwandseinschätzung	                        |  2          |
| **Summe**                                     |  **20**     |


#### Implementierung

| Aufgabe                                       | Zeit in Std |
|-----------------------------------------------|------------:|
| HTML Grundgerüst Registrierung + Login        |  2          |
| HTML Grundgerüst Übersicht                    |  2          |
| HTML Grundgerüst Meine Liste - Übersicht      |  2          |
| HTML Grundgerüst Meine Liste - Gegenstände    |  2          |
| HTML Grundgerüst Meine Liste - Ressourcen     |  2          |
| CSS-Styling Breakpoint small                  |  5          |
| CSS-Styling Breakpoint medium                 |  5          |
| CSS-Styling Breakpoint large                  |  5          |
| Implementierung Login + Registrierung	        |  6          |
| Implementierung Übersichtsseite + Filter      |  8          |
| Implementierung Übersicht über alle Listen    |  6          |
| Implementierung Gegenstände einer Liste	    |  8          |
| Implementierung Ressourcen in einer Liste     |  7          |
| **Summe**                                     |  **60**     |

#### Dokumentation / Tests

| Aufgabe                                       | Zeit in Std |
|-----------------------------------------------|------------:|
| Dokumentation Login + Registrierung           |  2          |
| Dokumentation Übersichtseite                  |  3          |
| Dokumentation Filter                          |  2          |
| Dokumentation Übersicht über alle Listen	    |  2          |
| Dokumentation über Gegenstände einer Liste    |  3          |
| Dokumentation über Ressourcen in einer Liste  |  2          |
| Dokumentation Mobil                           |  3          |
| Test der Benutzeroberfläche                   |  2          |
| Vergleich SOLL / IST Stunden                  |  1          |
| **Summe**                                     |  **20**     |

#### Zusammenfassung
| Teil                                          | Zeit in Std |
|-----------------------------------------------|------------:|
| Projektvorbereitung                           |  20         |
| Implementierung                               |  60         |
| Dokumentation / Tests                         |  20         |
| **Summe**                                     |  100        |

### Backend

Verantwortlicher: Julian Schulzeck

#### Projektvorbereitung

| Aufgabe                                       | Zeit in Std |
|-----------------------------------------------|------------:|
| Projektthema überlegen + grobe Funktionen     |  8          |
| Verfassen Abstract                            |  0.75       |
| Verfassen Abstract Client                     |  1          |
| Verfassen Abstract Server                     |  0.25       |
| Datenaufbau überlegen und planen              |  3          |
| UML Diagramm                                  |  2          |
| ER Diagramm                                   |  2          |
| Relationales Datenbankschema                  |  1          |
| Backend Endpunkte / API - Beschreibung        |  4          |
| Markdown                                      |  6          |
| Aufwandseinschätzung	                        |  2          |
| **Summe**                                     |  **30**     |

#### Implementierung und Validierung

| Aufgabe                                        | Zeit in Std |
|------------------------------------------------|------------:|
| Setup Framework                                |             |
| - Framework express                            |  0.25       |
| - Framework jest                               |  0.5        |
| - Framework sqlite3                            |  0.25       |
| Datenbank                                      |             |
| Datencrawler Implementieren                    |  8          |
| Setup                                          |  2          |
| Implementierung Auth                           |  3          |
| Implementierung GET /user                      |  2          |
| Implementierung GET /user/:username            |  2          |
| Implementierung GET /user/:username/itemlisten |  2          |
| Implementierung GET /items                     |  2.5        |
| Implementierung Get /items/:itemId             |  2.5        |
| Implementierung POST /user                     |  2.5        |
| Implementierung POST /user/:username/itemliste |  2.5        |
| Implementierung DELETE /user/:username         |  2          |
| Implementierung Validierungsschemata           |  3          |
| **Summe**                                      |  **35**     |

#### Dokumentation / Tests

| Aufgabe                                             | Zeit in Std |
|-----------------------------------------------------|------------:|
| Setup Tests                                         |  4          |
| Test DB                                             |  4          |
| Test GET /user                                      |  2          |
| Test GET /user/:username                            |  2          |
| Test GET /user/:username/itemlisten                 |  2          |
| Test GET /items                                     |  2          |
| Test Get /items/:itemId                             |  2          |
| Test POST /user                                     |  2          |
| Test POST /user/:username/itemliste                 |  2          |
| Test DELETE /user/:username                         |  2          |
| API-Dokumentation GET /user                         |  1          |
| API-Dokumentation GET /user/:username               |  1          |
| API-Dokumentation GET /user/:username/itemlisten    |  1          |
| API-Dokumentation GET /items                        |  1          |
| API-Dokumentation Get /items/:itemId                |  1          |
| API-Dokumentation POST /user                        |  1.5        |
| API-Dokumentation POST /user/:username/itemliste    |  1.5        |
| API-Dokumentation DELETE /user/:username            |  1          |
| Dokumentation                                       |  1          |
| Vergleich SOLL / IST Stunden                        |  1          |
| **Summe**                                           |  **35**     |


#### Zusammenfassung
| Teil                                     | Zeit in Std |
|------------------------------------------|------------:|
| Projektvorbereitung                      |  30         |
| Implementierung                          |  35         |
| Dokumentation / Tests                    |  35         |
| **Summe**                                |  100        |