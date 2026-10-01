# Bausteine — Rezepte zum Abschreiben

Alles hier ist aus laufenden Projekten extrahiert. Jeder Baustein nennt, woher er
kommt, und wie du ihn anpasst.

---

## 1. Cron auf GitHub Actions — kostenlos und robust
*Aus [Fly of Wallstreet](projekte/fly-of-wallstreet.md) (`.github/workflows/daily.yml`).*

```yaml
name: Täglich
on:
  schedule:
    - cron: "17 21 * * 1-5"   # nie zur vollen Stunde: GitHub verspätet dort am meisten
    - cron: "47 23 * * 1-5"   # zweiter Termin als Netz — Lauf muss idempotent sein
  workflow_dispatch:           # Knopf zum Selbststarten

permissions:
  contents: write

concurrency:
  group: mein-job             # nie zwei Läufe gleichzeitig am selben Zustand
  cancel-in-progress: false

jobs:
  lauf:
    runs-on: ubuntu-latest
    timeout-minutes: 30
    steps:
      - uses: actions/checkout@v4
        with: { ref: main }    # aktueller Stand, nicht der SHA beim Auslösen
      - uses: actions/setup-python@v5
        with: { python-version: "3.11", cache: pip }
      - run: pip install -r requirements.txt && python -m pytest -q
      - run: python -m meinprojekt.step
```

**Anpassen:** Zeiten in UTC (Sommer/Winter beachten), Tests *vor* dem Lauf, damit ein
kaputter Stand nichts schreibt.

---

## 2. Zustand auf einem verwaisten Branch
*Aus Fly. Wann: Dein Job hat ein Gedächtnis (Modell, Datenbank), das täglich wächst,
aber nicht die Historie von `main` aufblähen soll.*

```bash
git worktree add -q --detach "$RUNNER_TEMP/zustand"
cd "$RUNNER_TEMP/zustand"
git checkout -q --orphan zustand
git rm -r -q --cached . && git clean -fdxq
cp -r "$GITHUB_WORKSPACE/state" .
git add -f state/
git commit -q -m "Zustand $(date -u +%F)"
git push -f -q origin zustand:fly-state     # jedes Mal ein einziger Commit, ersetzt
```

Zum Laden am Anfang des nächsten Laufs:

```bash
if git fetch -q origin fly-state; then
  git restore --source=FETCH_HEAD --worktree -- state/   # nur Arbeitsbaum, nie in den Index
fi
```

**Warum:** Das Repo wächst nicht um täglich 1,5 MB. `main` bleibt sauber, Signale
(`signals.csv`) können trotzdem dort landen — mit `pull --rebase` und drei Wiederholungen.

---

## 3. Nacht-Warteschlange für KI-Routinen
*Aus [Nachtschicht](projekte/nachtschicht.md).* Drei Dateien genügen:

**`NACHT-TODO.md`** — die Warteschlange:
```
- [ ] **P1 · Kurztitel** — was falsch ist oder fehlt, und warum es nervt.
  Wo: datei.html (Funktion) · Fertig wenn: messbares Kriterium
```
`P1` Fehler/großer Mangel · `P2` spürbar · `P3` Feinschliff. Eine eigene Rubrik
**„Entscheidung nötig"** für alles, was nur der Mensch klären kann.

**`NACHT-LOG.md`** — Protokoll, was passiert ist (morgens zuerst lesen).
**`NACHT-BERICHT.md`** — Testbericht der Tester-Routine.

Dazu **eine** Anleitung `routinen/nacht.md` (erst testen und Funde eintragen, dann
von oben abarbeiten, ein Commit pro Punkt). In der Oberfläche steht nur ein kurzer
Prompt: Branch holen, Anleitung lesen, harte Grenzen. Eine Routine reicht, weil das
Nutzungslimit ein Fünf-Stunden-Fenster am Konto ist — zwei Läufe hintereinander bringen
nicht mehr Arbeit. Und in `CLAUDE.md` die
Pflicht, am Ende jeder Aufgabe einen Skill `todo-notieren` aufzurufen, der Offenes,
Aufgeschobenes und Ungeprüftes einträgt.

**Sicherheit:** Arbeit nur auf `claude/nacht`; Prompts verbieten `main`, `--force`,
Löschen. Morgens: `git log main..origin/claude/nacht --oneline`, dann mergen oder
verwerfen. Cron ist UTC — im Herbst/Frühling umstellen.

---

## 4. Test ohne Browser
*Aus Nachtschicht (`tools/nachttest.js`).* Setze Engine und Seiten headless zusammen,
rufe `update(1/60)` in einer Schleife auf, lies Werte aus und suche nach Ausnahmen,
`NaN`, toten Verweisen. ~2 Sekunden für zehn Seiten. Schreibe ausdrücklich dazu, was
es **nicht** messen kann (Pixel, Ton).

---

## 5. Look-ahead-Sperre
*Aus [Eye of Horus](projekte/eye-of-horus.md).* Idee: Der Backtester bekommt Daten
nur durch eine Schicht, die `as_of`-Zeit kennt und alles dahinter verweigert (Fehler,
nicht leer). Dazu ein Test, der gezielt versucht, Zukunft zu lesen — er muss
scheitern. Sonst verlässt du dich auf Disziplin.

---

## 6. Broker hinter einem Adapter
*Aus Eye of Horus und Fly.* `RiskEngine → BrokerAdapter → PaperBroker | AlpacaBroker`.
Die Live-Variante bleibt ein bewusster **Stub**, bis jemand sie absichtlich
verdrahtet. Papierkonto fest einkodiert, nicht per Schalter.

---

## 7. Provenienz-Tags für KI-Texte
*Aus Eye of Horus.* Jede Aussage trägt `OBSERVED` / `DERIVED` / `HYPOTHESIS` /
`UNCERTAIN`. Ohne API-Schlüssel springt ein deterministischer Ersatz ein — nichts wird
erfunden.

---

## 8. Drei Betriebsmodi
*Aus [Polymarket Bot](projekte/polymarket-bot.md).* A) kostenloser Anbieter, B)
bezahlter Anbieter, C) Demo ohne Schlüssel. Jeder, der das Repo klont, kommt in fünf
Minuten zu einem laufenden Ergebnis.

---

## 9. Ein-Personen-App mit Supabase
*Aus [Amet](projekte/amet.md).* Schema + nummerierte Migrationen, Row-Level-Security
als eigentlicher Schutz, Signups abgeschaltet, ein einziger Nutzer von Hand angelegt,
Constraints in der Datenbank (nichts ins Minus) statt in der Oberfläche. Frontend:
Vanilla-ES-Module, `python -m http.server`, GitHub Pages.

---

## 10. Minimal-PWA
*Aus [Health Tracker](projekte/health-tracker.md).* `index.html` + `manifest.json`
(Name, Farben, Icons 192/512) + `sw.js` (Cache-Liste der Dateien). Mehr braucht
„auf dem Handy installieren" nicht.

---

## 11. Projekt-Gesundheitscheck
Ein rein lesender Scan über alle Projekt-Ordner (Git vorhanden? Ungepushtes?
Secrets in Dateien? `.gitignore`/`.env.example`?) plus ein Slash-Command, der
Reparaturen vorschlägt. Politik: Additives (`.gitignore`, `.env.example`, README,
Lockfiles) ohne Rückfrage; Löschen, Committen, Pushen nur nach Bestätigung.
