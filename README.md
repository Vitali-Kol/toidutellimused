# Toidutellimused

Toidutellimuste rakendus agiilse arenduse labor. See on Node.js ja Express.js põhine API toidu tellimiseks, mis võimaldab kasutajatel registreeruda, vaadata menüüd, esitada tellimusi ja jälgida nende staatust. Andmeid hoitakse mälus.

## Tehnoloogiad

* **Node.js**
* **Express.js** — Veebiraamistik API loomiseks.
* **CORS** — Cross-Origin Resource Sharing tugi.
* **Nodemon** — Arenduskeskkonna tööriist automaatseks taaskäivitamiseks failide muutumisel.

## Keskkondade erinevused

| | Dev | Prod |
|--|-----|------|
| Port | 3000 | 3001 |
| Logid | Konsoolilogid on sisse lülitatud | Logimine on välja lülitatud või minimaalne |
| Restart | Automaatne restart failimuutustel (nodemon) | Manuaalne või haldustarkvara kaudu |

## Käivitamine

### Dev keskkond

Käivitab serveri nodemon`iga, mis jälgib failimuudatusi ja logib arenduskeskkonna päringuid:
nodemon src/server.js

### Prod keskkond

Käivitab serveri tootekeskkonna režiimis (ilma automaatse taaskäivitamiseta): node src/server.js

## Testid

Testide (nt Jest või Mocha) käivitamiseks kasuta järgmist käsku: node src/test.js

## API

| Meetod | Endpoint        | Kirjeldus |
|--------|----------------|----------|
| POST   | /register      | Uue kasutaja registreerimine süsteemi |
| GET    | /menu          | Tagastab saadaoleva toidumenüü |
| POST   | /orders        | Uue toidutellimuse esitamine |
| GET    | /orders/:id    | Konkreetse tellimuse staatuse ja detailide pärimine |

## GitHub Actions

Projektis on seadistatud CI (Continuous Integration) töövoog. Kui kood lükatakse (push) GitHubi represse, käivitub automaatne protsess, mis:

Seab üles Node.js keskkonna.

Paigaldab kõik vajalikud sõltuvused.

Käivitab automaattestid, et tagada API korrapärane toimimine enne koodi liitmist peamisesse harusse.
