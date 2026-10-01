# Fly of Wallstreet

> Eine Zucht künstlicher Fruchtfliegen, deren Gehirn dem Pilzkörper nachgebaut
> ist. Sie „riechen" den Markt, lernen per Dopamin und entscheiden: Long, Short
> oder nichts.

| | |
|---|---|
| **Repo** | https://github.com/Nikros07/Fly-of-Wallstreet |
| **Stack** | Python, NumPy, GitHub Actions, optional Alpaca-Papierkonto |
| **Start** | 2026-09-19 |
| **Stand** | v4 (2026-09-21): **läuft live** (Wochenzucht), **kein belegter Vorsprung** |

## Die Idee
Vorbild ist das Lern- und Belohnungszentrum der Fliege, wie es das
FlyWire-Konnektom zeigt. Jede Fliege hat 30 Sinneskanäle (15 Marktmerkmale, je
AN/AUS) → 2.000 Kenyon-Zellen mit zufälliger Verdrahtung → APL-Hemmung (nur 5 %
feuern) → GO/NOGO-Ausgang je Aktion. **Nur die Ausgangssynapsen lernen**; Dopamin
kommt aus dem Ergebnis nach *h* Tagen. Belohnung schwächt NOGO, Strafe schwächt
GO, alles erholt sich langsam.

## Die Zucht
50 Fliegen. **Jede Woche** sterben 10 %, 10 % werden geklont. Gekreuzt wird die
DNA (`fly/evolution.py`).

## Ergebnis (ehrlich)
2000–2024, 8 Seeds, Ausführung zur Eröffnung:
Kolonie Sharpe **0,44** · Kontrolle **0,41** · SPY **0,48**.
**Kein belastbarer Lernvorsprung.** Der Friedhof 2025+ ist verbraucht.

**Warum die früheren Erfolge verschwanden:** Zwei unabhängige Prüf-Agenten fanden,
dass die Kontrolle Zukunftswissen hatte und Schlusskurs-Ausführung unerreichbar
war. Alle Vorsprünge aus v1–v3 sind damit nicht belastbar. Das ist im README
vollständig dokumentiert (inklusive des Verlaufs vor der Fehlerbehebung).

## Betrieb: kostenlos auf GitHub
`.github/workflows/daily.yml` läuft werktags 21:17 und 23:47 UTC (zwei Termine,
weil GitHub-Cron sich verspäten kann; der zweite ist idempotent). Der **Zustand**
liegt auf dem verwaisten Branch `fly-state` (jedes Mal ein einzelner Commit,
force-gepusht), Signale in `signals.csv` auf `main`. Optional: Alpaca-Papierkonto
über Secrets (fest *Paper*).

## Das kannst du mitnehmen
- **Zustand auf einem Orphan-Branch** statt in `main`: das Repo wächst nicht um
  täglich 1,5 MB. Rezept in [BAUSTEINE.md](../BAUSTEINE.md).
- **Doppelter Cron + Idempotenz + `concurrency`-Gruppe** macht GitHub-Cron
  zuverlässig genug.
- **Prüf-Agenten, die nur suchen, was falsch ist** — sie haben hier jeden
  Scheinerfolg gekippt.
- **Messregel:** Neue Ideen nur mit frischen Seeds gegen eine gemischte
  Dopamin-Kontrolle (`shuffled-dopamine`) messen. Nie Varianten auf denselben
  Seeds wählen *und* bestätigen.
- Nicht erneut probieren (schon widerlegt): mehr Sinne (v3), Mehrmarkt,
  Schädel-Bauweise, Vol-Overlay.

## Offene Ideen (Recherche, ungetestet)
Vorhersagefehler-Dopamin, Kompartimente, Teil-Vererbung, ALPS.

## Verwandt
[Fuck the Fly](fuck-the-fly.md), [Operation NEMI](operation-nemi.md).
