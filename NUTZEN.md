# Wofür nimmst du welchen Code?

Für Freunde: Du hast ein Projekt und suchst, was du von mir klauen kannst. Such dir
unten dein Ziel aus. Dort steht, **welches Repo**, **welche Dateien** und **was du
dafür tun musst**. Frag mich, wenn was unklar ist.

> Alle Repos: https://github.com/Nikros07 · Ehrlichkeits-Hinweis: Vieles ist
> Prototyp. Was getestet ist und was nicht, steht in den
> [Steckbriefen](projekte/).

---

## So holst du dir nur einen Teil eines Repos

Du brauchst selten das ganze Projekt. Mit Sparse-Checkout holst du nur einen Ordner:

```bash
git clone --filter=blob:none --no-checkout https://github.com/Nikros07/Eye-of-Horus.git
cd Eye-of-Horus
git sparse-checkout set backend/app/services/quant_engine
git checkout
```

Oder du lädst auf GitHub eine einzelne Datei mit dem Knopf **Raw** herunter.
Danach: Datei in dein Projekt legen und Importe anpassen.

---

## Ich will …

### … einen Trading-Backtest bauen, der nicht lügt
| Du brauchst | Nimm |
|---|---|
| Backtester, der Zukunftsdaten *verweigert* | [Eye-of-Horus](https://github.com/Nikros07/Eye-of-Horus) → `backend/app/services/quant_engine/` (`temporal.py`, `backtester.py`, `metrics.py`) |
| Walk-forward, Monte Carlo, Validierung | [Operation-NEMI](https://github.com/Nikros07/Operation-NEMI) → `nemi/backtest/` (`engine.py`, `metrics.py`, `montecarlo.py`, `validation.py`) |
| Checkliste, welche Fehler typisch sind | [LERNEN.md](LERNEN.md), Teil B |

**Tipp:** Fang mit `temporal.py` an und lies danach `LERNEN.md` Nr. 4–8. Das spart dir
Wochen Selbsttäuschung.

### … Marktdaten sammeln (Yahoo) und speichern
[Operation-NEMI](https://github.com/Nikros07/Operation-NEMI) → `nemi/data/`
(`yahoo.py`, `store.py`, `validation.py`). Merke: 1-Minuten-Daten gibt Yahoo nur
30 Tage zurück — [Begründung](projekte/operation-nemi.md).

### … Risiko-Rechnung (Positionsgröße, Stop-Loss)
[Operation-NEMI](https://github.com/Nikros07/Operation-NEMI) → `nemi/risk/`
(`sizing.py`, `stops.py`). Reiner deterministischer Code, gut testbar.

### … Marktregime erkennen
[Operation-NEMI](https://github.com/Nikros07/Operation-NEMI) → `nemi/engine/regime.py`,
`technical.py`, `setups.py`. Ehrlich: Die Setups haben im Test nicht gewonnen. Nimm
die Bausteine, nicht die Versprechen.

### … ein Team aus KI-Agenten bauen, die sich widersprechen
| Muster | Repo | Dateien |
|---|---|---|
| Rollen mit Persönlichkeit, CIO-Urteil, Teufelsanwalt | [Apex-Capital](https://github.com/Nikros07/Apex-Capital) | `agents/` (`base.py`, `committee.py`, `cio.py`, `devil.py`, `risk.py`) |
| Agenten-Pipeline mit Pflicht-Skeptiker und Orchestrator | [Polymarket-Bot](https://github.com/Nikros07/Polymarket-Bot) | `backend/agents/` (`base_agent.py`, `skeptic_agent.py`, `debate_agent.py`), `backend/core/orchestrator.py` |

**Tipp:** `base.py` bzw. `base_agent.py` zuerst lesen: Daran siehst du, wie ein
Agent aufgebaut ist. Dann eigene Rollen ergänzen.

### … etwas nachts automatisch laufen lassen, ohne Server
[Fly-of-Wallstreet](https://github.com/Nikros07/Fly-of-Wallstreet) →
`.github/workflows/daily.yml`. Fertiges Rezept in [BAUSTEINE.md](BAUSTEINE.md), Nr. 1
und 2. Kostet nichts, braucht nur ein GitHub-Konto.

### … eine KI nachts an meinem Projekt weiterarbeiten lassen
Das Muster (Warteschlange `NACHT-TODO.md`, Anleitung `routinen/nacht.md`, Skill
`todo-notieren`, Branch `claude/nacht`) ist in [BAUSTEINE.md](BAUSTEINE.md), Nr. 3,
komplett beschrieben. ⚠️ Die Dateien selbst liegen bei mir noch lokal und nicht auf
[GitHub](https://github.com/Nikros07/Nachtschicht) — frag mich, dann pushe ich sie.

### … ein Browserspiel ohne Framework bauen
| Größe | Repo |
|---|---|
| Mini, eine einzige Datei | [Nico-Frog](https://github.com/Nikros07/Nico-Frog) |
| Groß: Engine mit Kampf, Dialogen, Ton, Touch | [Nachtschicht](https://github.com/Nikros07/Nachtschicht) → `nacht/` (`kern.js`, `welt.js`, `kampf.js`, `dialog.js`, `ton.js`, `mobil.js`) |

Läuft auf GitHub Pages ohne Build. Alle Regeln der Engine stehen in `ARCHITEKTUR.md`.

### … eine private Finanz-App bauen
[Amet](https://github.com/Nikros07/Amet) → `supabase/` (Schema, Migrationen) und
`js/` (Wallets, Budgets, Ziele, Schnelleingabe). Setup in fünf Schritten im README
des Repos. Du brauchst ein kostenloses Supabase-Konto.

### … eine App, die man aufs Handy „installiert" (PWA)
[Health-Tracker](https://github.com/Nikros07/Health-Tracker) → `manifest.json`,
`sw.js`, `index.html`. ⚠️ Nimm den Code, **nicht** die Datenablage in ein
öffentliches Repo (`js/github-storage.js`) für private Daten.

### … ein schickes Dashboard mit Widgets und Strg+K
[Hermes AI Dashboard](projekte/hermes-ai-dashboard.md) (Next.js; Repo folgt) oder
[Personal-Dashboard](https://github.com/Nikros07/Personal-Dashboard) (React/Vite +
Fastify + SQLite).

### … Ereignisse (Wetter, Katastrophen) mit Märkten verknüpfen
[Eye-of-Horus](https://github.com/Nikros07/Eye-of-Horus) → `backend/app/services/`:
`event_engine/` (Quellen NASA EONET, Open-Meteo, Verifikation), `impact_engine/`
(Graph Ereignis → Rohstoff), `signal_engine/`. Läuft ohne Schlüssel im Demo-Modus.

### … mit einem echten Fliegengehirn spielen
[Fuck-the-Fly](https://github.com/Nikros07/Fuck-the-Fly) (`fly_tinder.py`, ein
`pip install` reicht) oder [Fly-of-Wallstreet](https://github.com/Nikros07/Fly-of-Wallstreet)
→ `fly/` (`senses.py`, `dopamine.py`, `population.py`, `evolution.py`) für ein
Pilzkörper-Netz mit Evolution.

### … evolutionäre Algorithmen / Populationen verstehen
[Fly-of-Wallstreet](https://github.com/Nikros07/Fly-of-Wallstreet) → `fly/evolution.py`,
`population.py`, `colony.py`: Auslese (10 % Tod, 10 % Klone), Kreuzung, Seeds.

### … Papierhandel mit Alpaca anbinden
[Fly-of-Wallstreet](https://github.com/Nikros07/Fly-of-Wallstreet) → `fly/broker.py`
oder [Eye-of-Horus](https://github.com/Nikros07/Eye-of-Horus) (Broker hinter einem
Adapter). Immer **Paper**, nie live.

---

## Wenn du unsicher bist

| Dein Typ | Starte hier |
|---|---|
| „Ich will lernen, wie man Trading-Ideen ehrlich testet" | [LERNEN.md](LERNEN.md) → NEMI → Eye of Horus |
| „Ich will KI-Agenten bauen" | Polymarket-Bot (einfacher) → Apex Capital |
| „Ich will ein Spiel machen" | Nico Frog → Nachtschicht |
| „Ich will eine eigene App für mich" | Amet-Muster → Health-Tracker (PWA) |
| „Ich will einfach was Cooles sehen" | Fuck-the-Fly, Eye of Horus (3D-Globus), Nachtschicht spielen |

## Regeln fürs Weiterverwenden (unter Freunden)
1. **Schlüssel gehören nie in Git.** Nutze `.env` (steht in jeder `.gitignore`).
2. **Trading nur auf Papier**, bis du Out-of-Sample-Beweise hast
   ([LERNEN.md](LERNEN.md) Nr. 5–7).
3. **Sag, woher es kommt** — ein Link auf das Repo in deinem README reicht.
4. **Fehler melden:** Wenn du was gefunden hast, schreib mir oder öffne ein Issue.
