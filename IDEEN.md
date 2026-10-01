# Ideen & Brainstorm

Was als Nächstes sinnvoll wäre — sortiert nach Aufwand und Wirkung. Alles hier ist
**Vorschlag**, keine Zusage. Einträge mit ✅ sind eine direkte Folge der Lektionen
in [LERNEN.md](LERNEN.md).

---

## 1. Aufräumen (kleiner Aufwand, sofort wirksam)

- [ ] ✅ **Health Tracker auf privat stellen** oder Daten auslagern — er schreibt in
  ein öffentliches Repo ([Details](projekte/health-tracker.md)).
- [ ] **Hermes AI Dashboard** als eigenes Repo anlegen und pushen (aktuell nur lokal).
- [ ] **READMEs** für Health-Tracker und Nico-Frog (je zwei Sätze).
- [ ] Beschreibungen für Apex-Capital, Fuck-the-Fly, Health-Tracker, Nico-Frog im
  GitHub-Profil nachtragen — sie sind leer.
- [ ] **Vault-`origin`** korrigieren (zeigt fälschlich auf Personal-Dashboard).
- [ ] **Pinned Repos** auf GitHub: Apex, Fly, Nachtschicht, Eye of Horus, diese Übersicht.
- [ ] Polymarket-Bot: Namen und Titel vereinheitlichen, Branch nach `main` mergen.
- [ ] Amet: Supabase-Edge-Function einmalig deployen, Pages-Auslieferung prüfen.
- [ ] **Nachtschicht pushen:** 7 lokale Commits (Nachtroutine, `NACHT-TODO.md`,
  `CLAUDE.md`, Skill, `nachttest.js`) liegen nicht auf GitHub — Freunde sehen sie nicht.
- [ ] Nachtschicht: Cloud-Routine anlegen (wartet auf `environment_id`); am
  **25.10.2026** (Winterzeit) den Cron um eine Stunde anpassen.

---

## 2. Trading-Forschung (mittlerer Aufwand)

- **Regime zuerst erkennen:** NEMIs Gewinn stammte aus 2020. Ein Regime-Detektor
  (Volatilität, Trend, Korrelation) als *Vorfilter* — „heute ist NO TRADE-Wetter".
- **Eine gemeinsame Test-Bibliothek** für Apex, NEMI, Fly, MT5: dieselbe
  Walk-forward-, Kosten- und Look-ahead-Prüfung. Jetzt ist sie viermal gebaut.
- **Eye of Horus mit echten Daten** (`DATA_MODE=live`) und die Forschungsfrage
  wirklich beantworten: Ereignis-Erkennung früh genug? Mit der naiven Basislinie als Maßstab.
- **Fly: Vorhersagefehler-Dopamin** (aus den offenen Ideen) auf frischen Seeds testen.
- **MT5 v7: erster Testlauf** — zuerst zählen, wie viele der 13 Märkte melden.
- **UCITS-Backtest** mit real handelbaren Tickern (Strang B).
- **Der ehrliche Dauertest:** NEMI-Datensammler läuft ohnehin — in drei Monaten
  gibt es einen echten Out-of-Sample-Block.
- **Ensemble aus Verlierern?** Vier Strategien, die jede nichts können, aber
  unterschiedlich irren — lohnt eine Korrelationsanalyse, nicht ein Live-Test.

---

## 3. Werkzeuge für andere (größerer Hebel)

- **`no-lookahead`** — eine kleine Python-Bibliothek, aus Eye of Horus extrahiert:
  `as_of`-Datenzugriff plus ein Test-Helfer, der Look-ahead provoziert.
- **`nacht-queue`** — das Nachtschicht-System als Vorlage-Repo (`NACHT-TODO.md`,
  Prompts, Skill `todo-notieren`, `claude/`-Branch-Regeln). Wer ein Projekt hat,
  kopiert drei Dateien.
- **`orphan-state-action`** — das Zustand-auf-Branch-Rezept als wiederverwendbare
  GitHub Action.
- **„Ehrliche Backtests" — eine Checkliste** (aus LERNEN.md, Teil B) als
  druckbare Seite.
- **Konnektom-Spielplatz:** Fuck-the-Fly + Fly-Gehirn als Einstieg „Neuro trifft
  Daten" mit Notebook.
- **Vorlage „Ein-Personen-App":** Amet-Muster (Supabase + Vanilla-JS + Pages) als
  Template-Repo.

---

## 4. Spiele

- **Nachtschicht:** Software-Canvas für Pixelmessung in der Cloud (steht schon in
  `NACHT-TODO.md`), Highscores, Speicherstände, ein neues Level „Brunch am Morgen".
- **Nico Frog:** auf Nachtschicht-Engine portieren oder als Mini-Spiel im Menü.
- **Hub-Seite** für alle Browserspiele (GitHub Pages).

---

## 5. Persönliche Werkzeuge

- **Dashboards zusammenführen:** Personal Dashboard und Hermes AI Dashboard haben
  überlappende Ziele. Entweder ein Backend (Fastify/SQLite) hinter dem Next.js-Frontend
  oder eines von beiden einfrieren.
- **Amet ↔ Dashboard:** Amet-Daten als Widget im Hermes-Dashboard.
- **Obsidian als Langzeitgedächtnis für alle Agenten:** ein Vault-Ordner pro Projekt
  mit `STATUS.md`, das die Agenten selbst pflegen — so wie diese Übersicht.
- **Automatische Übersicht:** ein Skript, das alle Repos einmal pro Woche abfragt
  (Stand, letzter Commit, offene TODOs) und diese Seite aktualisiert.

---

## 6. Wilde Ideen

- **Fly-Parlament:** Statt einer Kolonie viele Fliegen-Typen, die sich gegenseitig
  überstimmen (jeder mit anderem Sinn) — mit dem Skeptiker-Muster aus Polymarket.
- **Trade-Tagebuch der NO-TRADE-Tage:** Das System schreibt jeden Tag auf, *warum* es
  nichts getan hat — daraus entsteht ein Datensatz über „Nichts-Tage".
- **Nacht-Zeitung:** Die Nachtroutinen erzeugen morgens eine einseitige HTML-Zusammenfassung
  (was geändert, was getestet, was offen).
- **Projekt-Autopsie als Format:** Jedes beendete Projekt bekommt einen Abschnitt „Was wir
  geglaubt haben / was stimmte" (NEMI und Fly haben ihn schon).
- **Öffentlicher Misserfolgs-Katalog:** Alle widerlegten Vermutungen gesammelt —
  wertvoller als Erfolge, weil sie niemand veröffentlicht.

---

## Wie du Ideen hier einträgst
Als Zeile unter dem passenden Kapitel; wenn sie größer ist, als Steckbrief mit der
[Vorlage](projekte/_VORLAGE.md). Ideen, die umgesetzt sind, wandern in
[LERNEN.md](LERNEN.md) oder [BAUSTEINE.md](BAUSTEINE.md).
