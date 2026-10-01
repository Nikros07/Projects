# Apex Capital

> Eine Hierarchie aus 10 KI-Agenten mit eigenen Persönlichkeiten, die Aktien
> recherchieren, debattieren und auf einem Papierkonto handeln.

| | |
|---|---|
| **Repo** | https://github.com/Nikros07/Apex-Capital |
| **Stack** | Python 3.11, FastAPI (async), Docker, Railway/Render |
| **Stand** | **läuft weiterhin live**; zuletzt Kostenoptimierung am 2026-08-30 |
| **Modus** | nur Papierhandel, Echtdaten, Spielgeld |

## Worum es geht
Echte Marktdaten, falsches Geld: Man soll zusehen können, wie eine Strategie sich
über Zeit schlägt, bevor irgendetwas Echtes riskiert wird. Die Agenten haben
Rollen und Charakter, damit sie sich wirklich widersprechen statt dasselbe zu
sagen.

## Das Team

| Agent | Rolle |
|---|---|
| Elena | Makroökonomin, setzt das Marktregime |
| Kai | Technischer Analyst („The tape never lies") |
| Sophie | Fundamentalanalystin (Cashflow über alles) |
| Alex | Research, findet, was andere übersehen |
| Jordan | Social Sentiment (Reddit/StockTwits) |
| Viktor | Risikomanager, sagt zuerst nein |
| Leo / Nina | Bullen- bzw. Bärenanwalt |
| Marcus | CIO, Urteil INVEST / PASS / WAIT |
| Dante | Advocatus Diaboli nach jedem INVEST |

## Wie eine Entscheidung entsteht
Recherche → Debatte (Bulle gegen Bär) → Risikoprüfung → CIO-Urteil →
Teufelsanwalt → Ausführung. Details im
[README des Repos](https://github.com/Nikros07/Apex-Capital#how-a-decision-gets-made).

## Was funktioniert / was nicht
- **Funktioniert:** Rollen-Debatte, Dashboard, 24/7-Betrieb mit gestaffeltem
  Monitor-Zeitplan, günstiger Betrieb.
- **Hat nicht funktioniert:** Der Bot war gebaut, um zu handeln. Vier
  voneinander unabhängige `run_forced_trade`-Pfade garantierten mindestens einen
  Trade pro Scan; ein Stage-2-Bypass übersprang sogar das Sprachmodell und
  reichte ein `fake_result` mit `verdict: INVEST` an den Kauf weiter. Die
  Belege wurden gesucht, um das Handeln zu rechtfertigen — das ist die zentrale
  Lehre dieser Reihe.
- Startkapital 10.000 € war hartcodiert, obwohl es real ~1.000 € sind.

## Das kannst du mitnehmen
- **Persönlichkeiten statt Prompts-Varianten:** Agenten mit klarem Charakter und
  Auftrag („muss widersprechen") erzeugen echte Debatte.
- **Advocatus Diaboli *nach* dem Urteil**, nicht davor — er sucht den fatalen
  Fehler im fertigen Ergebnis.
- **Anti-Muster:** Baue nie einen Weg, der ein Ergebnis erzwingt. Jeder
  Pflicht-Trade ist ein Bug, der als Feature verkleidet ist.
- Kosten senken durch **gestaffelte Zeitpläne** (teure Checks selten, billige oft)
  und **begrenzte Snapshot-Abfragen**.

## Verwandt
[Operation NEMI](operation-nemi.md) (Nachfolger der Forschung),
[Polymarket Bot](polymarket-bot.md) (gleiches Agenten-Muster).
