# Projektvorschlag Dofus Ressourcenplaner

**Hochschule Worms CSA 151 WS 2018/19**

Gruppe X  

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

Assumenda beatae deleniti distinctio earum eligendi harum illum in labore magni molestias nam, neque quaerat, quo sint sit totam voluptate voluptatum! Aliquam delectus dolorem ex laborum nihil odit tempora temporibus? Adipisci amet beatae culpa quae voluptatibus.


![](wireframes/medium.jpeg)

## Desktop

Consequuntur incidunt iste neque nihil nulla omnis quam, saepe veritatis. Corporis labore maiores modi.

### Homepage

Lorem ipsum dolor sit amet, consectetur.

![](wireframes/Homepage.png)

### Pricing

Cumque delectus laboriosam magnam maxime nam porro possimus quos recusandae!

![](wireframes/Pricing.png)

### Signup

Autem cupiditate eius est ex iure necessitatibus officiis omnis porro quod sequi?
![](wireframes/Signup.png)

### Registered

Lorem ipsum dolor sit amet, consectetur.

![](wireframes/Registered.png)

### Support

Consequuntur incidunt iste neque nihil nulla omnis quam, saepe veritatis. Corporis labore maiores modi.


![](wireframes/Support.png)


## Abstract Server
Verantwortlicher: Julian Schulzeck

Lorem ipsum dolor sit amet, consectetur adipisicing elit. Consequuntur incidunt iste neque nihil nulla omnis quam, saepe veritatis. Corporis labore maiores modi.


## UML

Hier ein UML Diagramm von den Objekten, die wir benötigen werden.
Ein **User** Objekt hat eine Liste von beliebig vielen **ItemListe** Objekten. Eine **ItemListe** enthält beliebig viele **Item** Objekte. Ein **Item** Objekt besitzt keine (wenn das Item nicht
herstellbar ist) bis eine **Rezeptur**. Ein **Item** besitzt außerdem die Attribute name, id, level, beruf, icon und anzahlBenoetigt. "level" bildet das Level des Items ab, "beruf" speichert
den Beruf mit dem man den Gegenstand herstellen kann und "icon" speichert das .png zu dem jeweiligen Item. Eine **Rezeptur** besteht aus eins bis acht **RezepturItem** Objekten.
**RezepturItem** erbt alle Attribute von **Item** und hat zusätzlich noch "anzahlBenoetigt" als Attribut, welches beschreibt, wie oft das Item für die Rezeptur benötigt wird.

![](uml/uml_diagramm_dofus_ressourcenplaner.svg)


## API-Beschreibung
Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ad consequuntur, doloribus hic impedit quaerat quam quas qui voluptas voluptatibus! Eius facere harum nisi repellendus vel.

### `GET /foo`
In dieser Route nimmt der Server Lorem entgegen.
Als Antwort liefert er ein ipsum dolor sit amet, consectetur adipisicing elit. Ad consequuntur, doloribus hic impedit quaerat quam quas qui voluptas voluptatibus! Eius facere harum nisi repellendus vel.

### `POST /foo`
Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ad consequuntur, doloribus hic impedit quaerat quam quas qui voluptas voluptatibus! Eius facere harum nisi repellendus vel.

### `PUT /foo`
Animi aspernatur commodi consequatur libero nesciunt nisi, praesentium quidem repellendus sit sunt. Maiores, officia omnis!

### `DELETE /foo`
Consequuntur incidunt iste neque nihil nulla omnis quam, saepe veritatis. Corporis labore maiores modi.

### Template Object

Animi aspernatur commodi consequatur libero nesciunt nisi, praesentium quidem repellendus sit sunt. Maiores, officia omnis!


```javascript
{
  success: false,
  msg: "...."
}
```

Cumque delectus laboriosam magnam maxime nam porro possimus quos recusandae!

```javascript
{
  success: true,
  foo: "$bar"
}
```

## Aufwandsschätzungen

### Frontend

Verantwortlicher: Peter Schmidt

#### Projektvorbereitung 

Cumque delectus laboriosam magnam maxime nam porro possimus quos recusandae!

| Aufgabe                                  | Zeit in Std |
|------------------------------------------|------------:|
| Wireframe Mobil Lorem                    |  4          |
| Wireframe Desktop Lorem                  |  4          |
| Beschreibung Funktionen Lorem            |  4          |
| Wireframe Lorem2                         |  4          |
| Beschreibung Funktionen Lorem2           |  4          |
| Wireframe Lorem3                         |  4          |
| Beschreibung Funktionen Lorem4           |  4          |
| Verfassen des Projektvorschlags          |  8          |
| ...                                      |  ...        |
| **Summe**                                |  **...**    |


#### Implementierung

| Aufgabe                                  | Zeit in Std |
|------------------------------------------|------------:|
| HTML-Grundgerüst Lorem                   |  2          |
| HTML-Grundgerüst Lorem2                  |  2          |
| HTML-Grundgerüst Lorem3                  |  1          |
| SCSS-Styling Breakpoint small            |  4          |
| SCSS-Styling Breakpoint medium           |  4          |
| SCSS-Styling Breakpoint large            |  4          |
| Implementierung Funktion Lorem           |  6          |
| Implementierung Funktion Lorem2          |  6          |
| Implementierung Funktion Lorem3          |  4          |
| ...                                      |  ...        |
| **Summe**                                |  **...**    |

#### Dokumentation / Tests

| Aufgabe                                  | Zeit in Std |
|------------------------------------------|------------:|
| Dokumentation Funktion Lorem             |  4          |
| Dokumentation Funktion Lorem2            |  1          |
| Dokumentation Funktion Lorem3            |  2          |
| ...                                      |  ...        |
| Vergleich SOLL / IST Stunden             |  1          |
| **Summe**                                |  **...**    |

#### Zusammenfassung
| Teil                                     | Zeit in Std |
|------------------------------------------|------------:|
| Projektvorbereitung                      |   30        |
| Implementierung                          |  ...        |
| Dokumentation / Tests                    |  ...        |
| **Summe**                                |  100        |

### Backend

Verantwortlicher: Johannes Meier

#### Projektvorbereitung

| Aufgabe                                  | Zeit in Std |
|------------------------------------------|------------:|
| Backend Endpunkte / API - Beschreibung   |  5          |
| ORM                                      |  3          |
| Verfassen des Projektvorschlags          |  2          |
| Verfassen ...                            |  5          |
| Markdown                                 |  8          |
| ...                                      |  ...        |
| **Summe**                                |  **...**    |

#### Implementierung und Validierung

| Aufgabe                                  | Zeit in Std |
|------------------------------------------|------------:|
| Setup Framework                          |             |
| - Framework express                      |  0.25       |
| - Framework jest                         |  0.5        |
| - Framework ...                          |  0.25       |
| DB ...                                   |  0          |
| - Setup                                  |  4          |
| Implementierung Auth                     |  4          |
| Implementierung Lorem-Route              |  2          |
| Implementierung Lorem2-Route             |  1          |
| Implementierung Lorem3-Route             |  8          |
| Implementierung Lorem4-Route             |  4          |
| Implementierung Validierungsschemata     |  2          |
| Implementierung Validierung Route 1      |  0.5        |
| Implementierung Validierung Route 2      |  0.5        |
| ...                                      |  ...        |
| **Summe**                                |  **...**    |

#### Dokumentation / Tests

| Aufgabe                                  | Zeit in Std |
|------------------------------------------|------------:|
| Setup Tests                              |  4          |
| Test DB                                  |  1          |
| Test Lorem1-Route                        |  1          |
| Test Lorem2-Route                        |  0.2        |
| Test Lorem3-Route                        |  2          |
| API-Dokumentation Lorem1-Route           |  4          |
| API-Dokumentation Lorem2-Route           |  2          |
| API-Dokumentation Lorem3-Route           |  1          |
| API-Dokumentation Lorem4-Route           |  1          |
| Dokumentation Lorem1-Route               |  0.5        |
| Dokumentation Lorem2-Route               |  1          |
| Dokumentation Lorem3-Route               |  1          |
| Dokumentation Lorem4-Route               |  0.5        |
| ...                                      |  ...        |
| Vergleich SOLL / IST Stunden             |  1          |
| **Summe**                                |  **...**    |


#### Zusammenfassung
| Teil                                     | Zeit in Std |
|------------------------------------------|------------:|
| Projektvorbereitung                      |  ...        |
| Implementierung                          |  ...        |
| Dokumentation / Tests                    |  ...        |
| **Summe**                                |  100        |