# Server

## Verantwortlicher: Julian Schulzeck


## Version 1.0.0

## Scripts
all commands have to be executed from /server

### Basic NPM Setup
```bash
npm install
```

### Setup small Database
```bash
npm run setupTestDatabase
```
Fills the Database with the Data of the Items in the Game (https://www.dofus.com/de/mmorpg/leitfaden/ausruestung)
This command only installs a small portion of all the Items (Takes about 4 Minutes).
If the file db.sqlite3 already exists, you have to remove db.sqlite3 manually if you want to create a new Database.
If the Database is once setup, you don't have to run this command again.


### Setup full Database
```bash
npm run setupFullDatabase
```
Fills the Database with the Data of the Items in the Game (https://www.dofus.com/de/mmorpg/leitfaden/ausruestung)
This command installs all the Data of all Items in the Game (Takes about 3 hours).
If the file db.sqlite3 already exists, you have to remove db.sqlite3 manually if you want to create a new Database.
If the Database is once setup, you don't have to run this command again.


### Start server
```bash
npm start
```
Starts the Server (REST API) on Port 3010. Be sure to setup the Database first (before the first time starting the
Server).


### Tests
```bash
npm test
```
Starts all the tests in the Projects. Tests are located in server/tests. The module jest is used.

### Test-Coverage
```bash
npm run test-coverage
```
Starts all the tests in the Projects. And creates a coverage File to show how much code was covered.


### Api-Documentation
Api-Documentation is located in server/js_files/Api.js


### Documentation
Documentation of Code can be found in all .js files. To Create a Documentation directory you can run:
```bash
jsdoc js_files -r -d documentation
```
be sure to have jsdoc globally installed


## Modules

### celebrate
https://github.com/arb/celebrate
```bash
npm install celebrate
```

### cheerio
https://cheerio.js.org/
```bash
npm install cheerio
```

### cors
https://www.npmjs.com/package/cors
```bash
npm install cors
```

### express
https://www.npmjs.com/package/express
```bash
npm install express --save
```

### jest
https://jestjs.io/
```bash
npm install jest --save-dev
```

### request
https://github.com/request/request
```bash
npm install request
```

### request-promise
https://github.com/request/request-promise
```bash
npm install --save request
```

### SQLite
https://www.npmjs.com/package/sqlite3
https://github.com/mapbox/node-sqlite3/wiki
https://github.com/mapbox/node-sqlite3/wiki/API
```bash
npm install sqlite3
```


## Timetable

### Backend

Verantwortlicher: Julian Schulzeck

#### Projektvorbereitung

| Aufgabe                                       | Zeit in Std | Zeit Benötigt | Differenz |
|-----------------------------------------------|-------------|---------------|----------:|
| Projektthema überlegen + grobe Funktionen     |  8          | 8             | 0         |
| Verfassen Abstract                            |  0.75       | 0.75          | 0         |
| Verfassen Abstract Client                     |  1          | 1             | 0         |
| Verfassen Abstract Server                     |  0.25       | 0.25          | 0         |
| Datenaufbau überlegen und planen              |  3          | 3             | 0         |
| UML Diagramm                                  |  2          | 2             | 0         |
| ER Diagramm                                   |  2          | 2             | 0         |
| Relationales Datenbankschema                  |  1          | 1             | 0         |
| Backend Endpunkte / API - Beschreibung        |  4          | 4             | 0         |
| Markdown                                      |  6          | 6             | 0         |
| Aufwandseinschätzung	                        |  2          | 2             | 0         |
| **Summe**                                     |  **30**     |**30**         |**0**      |

#### Implementierung und Validierung

| Aufgabe                                                                       | Zeit in Std | Zeit Benötigt | Differenz |
|-------------------------------------------------------------------------------|------------:|---------------|----------:|
| Setup Framework                                                               |             |               |           |
| - Framework express                                                           |  0.25       | 0.1           | - 0.15    |
| - Framework jest                                                              |  0.5        | 0.2           | - 0.3     |
| - Framework sqlite3                                                           |  0.25       | 0.1           | - 0.15    |
| - Framework celebrate                                                         |  -          | 0.1           | + 0.1     |
| - Framework cheerio                                                           |  -          | 0.1           | + 0.1     |
| - Framework cors                                                              |  -          | 0.1           | + 0.1     |
| - Framework request                                                           |  -          | 0.1           | + 0.1     |
| - Framework request-promise                                                   |  -          | 0.2           | + 0.2     |
| Datenbank                                                                     |             |               |           |
| Datencrawler Implementieren                                                   |  8          | 15            | + 7       |
| Setup                                                                         |  2          | 4             | + 2       |
| Implementierung Auth                                                          |  3          | -             | - 3       |
| Implementierung GET /user                                                     |  2          | 0.5           | - 1.5     |
| Implementierung GET /user/:username                                           |  2          | 1             | - 1       |
| Implementierung GET /user/:username/itemlisten                                |  2          | 2             | + 0       |
| Implementierung GET /items                                                    |  2.5        | 3             | + 0,5     |
| Implementierung GET /berufe                                                   |  -          | 0.5           | + 0,5     |
| Implementierung GET /itemtypen                                                |  -          | 0.5           | + 0,5     |
| Implementierung GET /items/:itemId                                            |  2.5        | 1             | - 1.5     |
| Implementierung GET /items/berufe/:berufId                                    |  -          | 2             | + 2       |
| Implementierung GET /items/itemtypen/:typId                                   |  -          | 2             | + 2       |
| Implementierung GET /user/:userId/items/:itemId                               |  -          | 1             | + 1       |
| Implementierung POST /user                                                    |  2.5        | 1.5           | - 1       |
| Implementierung POST /user/:username/itemliste                                |  2.5        | 2.5           | + 0       |
| Implementierung POST /user/:userId/itemlisten/:itemListeId                    |  -          | 2.5           | + 2.5     |
| Implementierung POST /user/:userId/items                                      |  -          | 1             | + 1       |
| Implementierung DELETE /user/:username                                        |  2          | 2             | + 0       |
| Implementierung DELETE /user/:userId/itemlisten/:itemListeId                  |  -          | 2.5           | + 2.5     |
| Implementierung DELETE /user/:userId/itemlisten/:itemListeId/items/:itemId    |  -          | 2.5           | + 2.5     |
| Implementierung Validierungsschemata                                          |  3          | 3             | + 0       |
| **Summe**                                                                     |  **35**     | **54**        | **+ 19**  |

#### Dokumentation / Tests

| Aufgabe                                                                       | Zeit in Std | Zeit Benötigt | Differenz |
|-------------------------------------------------------------------------------|------------:|---------------|----------:|
| Setup Tests                                                                   |  4          | 1             | - 3       |
| Test DB                                                                       |  4          | 3             | - 1       |
| Test GET /user                                                                |  2          | 0.5           | - 1.5     |
| Test GET /user/:username                                                      |  2          | 0.5           | - 1.5     |
| Test GET /user/:username/itemlisten                                           |  2          | 1             | - 1       |
| Test GET /items                                                               |  2          | 1             | - 1       |
| Test GET /berufe                                                              |  -          | 0.5           | + 0.5     |
| Test GET /itemtypen                                                           |  -          | 0.5           | + 0.5     |
| Test GET /items/:itemId                                                       |  2          | 1             | - 1       |
| Test POST /user                                                               |  2          | 2             | + 0       |
| Test POST /user/:username/itemliste                                           |  2          | 2             | + 0       |
| Test POST /user/:userId/itemlisten/:itemListeId                               |  -          | 1.5           | + 1.5     |
| Test DELETE /user/:username                                                   |  2          | 1.5           | - 0.5     |
| Test DELETE /user/:userId/itemlisten/:itemListeId                             |  -          | 2             | + 2       |
| Test DELETE /user/:userId/itemlisten/:itemListeId/items/:itemId               |  -          | 2             | + 2       |
| API-Dokumentation GET /user                                                   |  1          | 0.5           | - 0.5     |
| API-Dokumentation GET /user/:username                                         |  1          | 0.5           | - 0.5     |
| API-Dokumentation GET /user/:username/itemlisten                              |  1          | 0.5           | - 0.5     |
| API-Dokumentation GET /items                                                  |  1          | 0.5           | - 0.5     |
| API-Dokumentation GET /berufe                                                 |  -          | 0.5           | + 0.5     |
| API-Dokumentation GET /itemtypen                                              |  -          | 0.5           | + 0.5     |
| API-Dokumentation Get /items/:itemId                                          |  1          | 0.5           | - 0.5     |
| API-Dokumentation Get /items/berufe/:berufId                                  |  -          | 0.5           | + 0.5     |
| API-Dokumentation Get /items/itemtypen/:typId                                 |  -          | 0.5           | + 0.5     |
| API-Dokumentation Get /user/:userId/items/:itemId                             |  -          | 0.5           | + 0.5     |
| API-Dokumentation POST /user                                                  |  1.5        | 0.5           | - 1       |
| API-Dokumentation POST /user/:username/itemliste                              |  1.5        | 0.5           | - 1       |
| API-Dokumentation POST /user/:userId/itemlisten/:itemListeId                  |  -          | 0.5           | + 0.5     |
| API-Dokumentation POST /user/:userId/items                                    |  -          | 0.5           | + 0.5     |
| API-Dokumentation DELETE /user/:username                                      |  1          | 0.5           | - 0.5     |
| API-Dokumentation DELETE /user/:userId/itemlisten/:itemListeId                |  -          | 0.5           | + 0.5     |
| API-Dokumentation DELETE /user/:userId/itemlisten/:itemListeId/items/:itemId  |  -          | 0.5           | + 0.5     |
| Dokumentation                                                                 |  1          | 1.5           | + 0.5     |
| Vergleich SOLL / IST Stunden                                                  |  1          | 1.5           | + 0.5     |
| **Summe**                                                                     |  **35**     | **31.5**      |**- 3.5**  |


#### Zusammenfassung
| Teil                                     | Zeit in Std | Zeit Benötigt | Differenz |
|------------------------------------------|------------:|---------------|----------:|
| Projektvorbereitung                      |  30         | 30            | + 0       |
| Implementierung                          |  35         | 54            | + 19      |
| Dokumentation / Tests                    |  35         | 31.5          | - 3.5     |
| **Summe**                                |  **100**    | **115.5**     | **+ 15.5**|
