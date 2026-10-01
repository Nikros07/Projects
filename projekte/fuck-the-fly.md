# Fuck the Fly ("Fly Tinder")

> Ein echtes Fliegenhirn swiped deine Bilder — links oder rechts.

| | |
|---|---|
| **Repo** | https://github.com/Nikros07/Fuck-the-Fly |
| **Stack** | Python, Paket [`flybrain`](https://pypi.org/project/flybrain/) |
| **Stand** | Spielerei, fertig (2026-09-18) |

## Worum es geht
Basis ist das **MaleCNS-v1.0-Konnektom**: 166.700 echte Neuronen, ~125 Mio.
Verbindungen aus dem Gehirn einer männlichen Fruchtfliege, kartiert von Google
Research, HHMI Janelia und der Uni Cambridge. Kein Training — das Netz ist fest
verdrahtet.

Zwei bekannte Schaltkreise werden zweckentfremdet:

| Input | In echt | Hier |
|---|---|---|
| `LC10a` → `DNa02` | Männchen verfolgt Weibchen | „Like"-Signal |
| `LC4` + `LPLC2` → `DNp01` | Etwas nähert sich bedrohlich (Fluchtreflex) | „Nope"-Signal |

Jedes Bild wird auf Helligkeit und Kantenreichtum reduziert, das treibt die
Neuronen an; der stärker feuernde Pfad gewinnt. Wissenschaftlich bedeutungslos,
aber ein echtes Gehirn trifft die Entscheidung.

## Das kannst du mitnehmen
- **Offene Konnektom-Daten sind ein Spielplatz:** ein `pip install` und ~260 MB
  Download, dann hast du ein echtes Gehirn zum Basteln.
- Der Weg von „lustige Idee" zu [Fly of Wallstreet](fly-of-wallstreet.md) zeigt, wie
  ein Spaßprojekt zum Forschungsprojekt werden kann: dieselbe Datenquelle, ernstere Frage.
- Für eigene Projekte: Inputs auf wenige Zahlen herunterbrechen und schauen,
  welche Schaltkreise reagieren — gute Übung für Feature-Reduktion.

## Verwandt
[Fly of Wallstreet](fly-of-wallstreet.md).
