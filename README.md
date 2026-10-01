<div align="center">

<img src="assets/banner.svg" alt="Meine Projekte" width="100%">

<br>

![Projekte](https://img.shields.io/badge/Projekte-13-6366f1?style=for-the-badge)
![Repos](https://img.shields.io/badge/GitHub_Repos-11-22d3ee?style=for-the-badge)
![Live](https://img.shields.io/badge/live-3-22c55e?style=for-the-badge)
![Trading](https://img.shields.io/badge/Trading-nur_Papier-f59e0b?style=for-the-badge)
![Agents](https://img.shields.io/badge/f%C3%BCr_Agents-AGENTS.md-a78bfa?style=for-the-badge)

**Du willst etwas Ähnliches bauen? Such dein Ziel unten aus und nimm dir nur den Teil, den du brauchst.**

[Finde dein Projekt](#-finde-dein-projekt) ·
[Alle Projekte](#-alle-projekte-auf-einen-blick) ·
[Details](#-die-projekte-im-detail) ·
[Gelerntes](#-was-ich-gelernt-habe) ·
[Für Agents](#-für-ai-agents)

</div>

---

## 🧭 Finde dein Projekt

```mermaid
flowchart TD
    Q{{"Was willst du bauen?"}}
    Q --> T["📈 Trading / Finanzen"]
    Q --> A["🤖 KI-Agenten"]
    Q --> G["🎮 Spiel"]
    Q --> W["🧰 App / Werkzeug"]
    Q --> N["🧠 Neuro / Spielerei"]

    T --> T1["Ehrlicher Backtest<br/>→ Eye of Horus, NEMI"]
    T --> T2["Marktdaten + Risiko<br/>→ NEMI"]
    T --> T3["Gratis-Job täglich<br/>→ Fly of Wallstreet"]
    T --> T4["Events → Märkte<br/>→ Eye of Horus"]
    T --> T5["Private Finanz-App<br/>→ Amet"]

    A --> A1["Einfache Pipeline<br/>→ Polymarket Bot"]
    A --> A2["Team mit Rollen<br/>→ Apex Capital"]

    G --> G1["Winzig, eine Datei<br/>→ Nico Frog"]
    G --> G2["Große Engine, 8 Level<br/>→ Nachtschicht"]

    W --> W1["Installierbare PWA<br/>→ Health Tracker"]
    W --> W2["Dashboard<br/>→ Hermes / Personal Dashboard"]

    N --> N1["Echtes Fliegenhirn<br/>→ Fuck the Fly"]
    N --> N2["Evolution + Lernen<br/>→ Fly of Wallstreet"]
```

---

## 🗺️ Alle Projekte auf einen Blick

```mermaid
mindmap
  root((Nikros07))
    Trading
      Apex Capital
      Operation NEMI
      Fly of Wallstreet
      Eye of Horus
      Polymarket Bot
      MT5 Master Strategy
    Finanzen
      Amet
    Spiele
      Nachtschicht
      Nico Frog
    Neuro
      Fuck the Fly
    Werkzeuge
      Personal Dashboard
      Hermes AI Dashboard
      Health Tracker
```

### Wie die Projekte zusammenhängen

```mermaid
graph LR
    APEX["Apex Capital<br/>10 Agenten"] -->|Lehren| NEMI["Operation NEMI<br/>Forschung"]
    APEX -->|Agenten-Muster| POLY["Polymarket Bot"]
    FTF["Fuck the Fly"] -.->|gleiches Gehirn-Modell| FLY["Fly of Wallstreet"]
    NEMI -.->|bewusst getrennt| FLY
    EOH["Eye of Horus<br/>Look-ahead-Sperre"] -.->|gleiche Ehrlichkeitsregeln| NEMI
    PD["Personal Dashboard"] -->|zweiter Anlauf| HERMES["Hermes AI Dashboard"]
    FROG["Nico Frog<br/>1 Datei"] -->|größerer Bruder| NACHT["Nachtschicht<br/>8 Level"]

    classDef trade fill:#312e81,stroke:#6366f1,color:#fff
    classDef game fill:#14532d,stroke:#22c55e,color:#fff
    classDef tool fill:#164e63,stroke:#22d3ee,color:#fff
    classDef neuro fill:#581c87,stroke:#a78bfa,color:#fff
    class APEX,NEMI,POLY,EOH,FLY trade
    class FROG,NACHT game
    class PD,HERMES tool
    class FTF neuro
```

### Die Tabelle

| | Projekt | Worum geht's | Stand | Repo |
|:-:|---|---|:-:|:-:|
| 📈 | **Apex Capital** | 10 KI-Agenten debattieren und handeln (Papier) | 🟢 live | [↗](https://github.com/Nikros07/Apex-Capital) |
| 📈 | **Operation NEMI** | Quant-Forschung, „NO TRADE" als Standard | 🔴 Backtest negativ | [↗](https://github.com/Nikros07/Operation-NEMI) |
| 📈 | **Fly of Wallstreet** | Fliegengehirn lernt Trading, Wochen-Evolution | 🟡 live, kein Vorsprung | [↗](https://github.com/Nikros07/Fly-of-Wallstreet) |
| 📈 | **Eye of Horus** | Ereignis → Markt, mit Look-ahead-Sperre | 🟢 Demo komplett | [↗](https://github.com/Nikros07/Eye-of-Horus) |
| 📈 | **Polymarket Bot** | Entscheider für Prognosemärkte | ⚪ ruht | [↗](https://github.com/Nikros07/Polymarket-Bot) |
| 📈 | **MT5 Master Strategy** | Forex-Robot + ETF-Portfolio | 🟡 v7 ungetestet | lokal |
| 💶 | **Amet** | Private Finanz-App (Supabase) | 🟢 nutzbar | [↗](https://github.com/Nikros07/Amet) |
| 🎮 | **Nachtschicht** | Pixel-Partyspiel, 8 Level | 🟢 [▶ spielbar](https://nikros07.github.io/Nachtschicht/) | [↗](https://github.com/Nikros07/Nachtschicht) |
| 🎮 | **Nico Frog** | Mini-Spiel in einer Datei | 🟢 fertig | [↗](https://github.com/Nikros07/Nico-Frog) |
| 🧠 | **Fuck the Fly** | Echtes Fliegenhirn swiped Bilder | 🟢 fertig | [↗](https://github.com/Nikros07/Fuck-the-Fly) |
| 🧰 | **Personal Dashboard** | Obsidian + Aufgaben + Suche | 🟡 Prototyp | [↗](https://github.com/Nikros07/Personal-Dashboard) |
| 🧰 | **Hermes AI Dashboard** | Widget-Kommandozentrale | 🟡 lokal | lokal |
| 🧰 | **Health Tracker** | Installierbare Tracker-PWA | 🟢 fertig | [↗](https://github.com/Nikros07/Health-Tracker) |

🟢 läuft/fertig · 🟡 Prototyp oder ohne Beleg · 🔴 Ergebnis negativ · ⚪ ruht

---

## 🔍 Die Projekte im Detail

Aufklappen, was dich interessiert. **„Nimm"** nennt Ordner/Dateien, die du direkt mitnehmen kannst.

### 📈 Trading & Finanzen

<details>
<summary><b>Apex Capital</b> — 10 KI-Agenten debattieren Aktien · 🟢 live</summary>

<br>

Python, FastAPI, Docker, Railway · nur Papiergeld · [Repo](https://github.com/Nikros07/Apex-Capital)

```mermaid
flowchart LR
    R["Recherche<br/>Elena · Kai · Sophie · Alex · Jordan"] --> D["Debatte<br/>Leo 🐂 vs Nina 🐻"]
    D --> RK["Risiko<br/>Viktor"]
    RK --> C["Urteil<br/>Marcus: INVEST / PASS / WAIT"]
    C --> DA["Teufelsanwalt<br/>Dante"]
    DA --> X["Ausführung<br/>Papierkonto"]
```

**Nimm:** `agents/` (Rollen-Agenten), `core/scheduler.py`.
**Vorsicht:** Enthielt erzwungene Trade-Pfade. Das ist ein Anti-Muster, nicht übernehmen.
</details>

<details>
<summary><b>Operation NEMI</b> — Forschung mit „NO TRADE" als Standard · 🔴 Backtest negativ</summary>

<br>

Python 3.11 · Railway-Cron · [Repo](https://github.com/Nikros07/Operation-NEMI)

Erster Echtdaten-Backtest (7,7 Jahre, 161 Symbole): **nicht profitabel**. Der Gewinn kam allein aus 2020, Walk-forward hat auch das beste Setup widerlegt. Das ist dokumentiert statt versteckt.

**Nimm:** `nemi/backtest/` (Walk-forward, Monte Carlo) · `nemi/data/` (Yahoo-Sammler) · `nemi/risk/` (Positionsgröße, Stops) · `nemi/engine/regime.py`.
</details>

<details>
<summary><b>Fly of Wallstreet</b> — Fliegengehirn lernt Trading · 🟡 live, kein Vorsprung</summary>

<br>

Python, NumPy, GitHub Actions · [Repo](https://github.com/Nikros07/Fly-of-Wallstreet)

```mermaid
flowchart LR
    M["Markt<br/>15 Merkmale"] --> S["30 Sinneskanäle"]
    S --> K["2000 Kenyon-Zellen<br/>nur 5 % feuern"]
    K --> O["GO / NOGO<br/>Long · Short"]
    O --> E["Entscheidung<br/>oder NO TRADE"]
    E --> DOP["Dopamin<br/>Ergebnis nach h Tagen"]
    DOP -.->|lernt nur hier| O
```

50 Fliegen, jede Woche sterben 10 % und 10 % werden geklont. Ergebnis 2000–2024: Sharpe **0,44** (Kolonie) vs. 0,41 (Kontrolle) vs. 0,48 (SPY): kein belastbarer Vorsprung.

**Nimm:** `.github/workflows/daily.yml` (kostenloser Tagesjob mit Zustand auf eigenem Branch) · `fly/evolution.py` · `fly/broker.py` (nur Papierkonto).
</details>

<details>
<summary><b>Eye of Horus</b> — Ereignis → Markt · 🟢 Demo komplett</summary>

<br>

FastAPI, Next.js 16, 3D-Globus · [Repo](https://github.com/Nikros07/Eye-of-Horus)

```mermaid
flowchart LR
    EV["Ereignis"] --> V["Verifikation"] --> I["Impact-Graph"] --> SG["Signal"] --> BT["Backtest<br/>mit Zeit-Sperre"] --> PT["Papierhandel"] --> OUT["Ergebnis"]
```

**Nimm:** `backend/app/services/quant_engine/` (Backtester, der Zukunftsdaten verweigert) · `event_engine/` (NASA EONET, Open-Meteo) · `impact_engine/`.
**Vorsicht:** Demo-Daten sind mit `is_demo` markiert und enthalten künstlichen Drift.
</details>

<details>
<summary><b>Polymarket Bot</b> — Entscheider für Wetten und Prognosemärkte · ⚪ ruht</summary>

<br>

Python, Streamlit, FastAPI · [Repo](https://github.com/Nikros07/Polymarket-Bot)

Sieben Stufen mit zehn Agenten (Scanner → Recherche → Predictor/Analyst/Skeptiker → Szenarien → Validierung → Synthese → Scoring). Läuft kostenlos mit OpenRouter oder ganz ohne Schlüssel im Demo-Modus.

**Nimm:** `backend/agents/` (inkl. `skeptic_agent.py`), `backend/core/orchestrator.py`.
</details>

<details>
<summary><b>MT5 Master Strategy</b> — Forex-Robot + ETF-Portfolio · 🟡 lokal</summary>

<br>

MQL5, Python · kein Repo

Der Forex-Robot v6 hatte vor Kosten exakt null Vorteil, deshalb v7 mit 13 Märkten auf Tagesbasis. Das ETF-Portfolio schlägt den DAX nach Steuer, aber **nicht** S&P-Buy-and-Hold (10,02 % vs. 10,56 % p. a.). Der echte Vorteil ist weniger Drawdown (−19 % statt −25 %).

**Lehre:** Kosten zuerst messen, immer gegen den dümmsten Konkurrenten vergleichen.
</details>

<details>
<summary><b>Amet</b> — private Finanz-App · 🟢 nutzbar</summary>

<br>

Vanilla-JS, Supabase, GitHub Pages · [Repo](https://github.com/Nikros07/Amet)

Wallets, Budgets, Sparziele, Forecast, KI-Assistent. Kein Bankzugriff, alles manuell, kein Wallet kann ins Minus.

**Nimm:** `supabase/` (Schema, Migrationen, Row-Level-Security) · `js/` (Wallets, Budgets, Ziele, Schnelleingabe).
</details>

### 🎮 Spiele

<details>
<summary><b>Nachtschicht</b> — Pixel-Partyspiel · 🟢 <a href="https://nikros07.github.io/Nachtschicht/">spielbar</a></summary>

<br>

Vanilla-JS, Canvas, 8 Level, Touch-Steuerung · [Repo](https://github.com/Nikros07/Nachtschicht)

Schule → Bei Moritz → Nachtbus → Schlange → Club → Afterhour → Späti → Heimweg.

**Nimm:** `nacht/` (Engine: Welt, Kampf, Dialoge, Ton, Eingabe, Mobil) · `ARCHITEKTUR.md` (Karte des Codes).
</details>

<details>
<summary><b>Nico Frog</b> — Mini-Spiel in einer Datei · 🟢</summary>

<br>

[Repo](https://github.com/Nikros07/Nico-Frog) · **Nimm:** `index.html`, das ist das ganze Spiel.
</details>

### 🧠 Neuro-Spielerei

<details>
<summary><b>Fuck the Fly</b> — echtes Fliegenhirn swiped Bilder · 🟢</summary>

<br>

Python, `pip install flybrain` · [Repo](https://github.com/Nikros07/Fuck-the-Fly)

166.700 echte Neuronen entscheiden per Balz- oder Fluchtreflex-Schaltkreis, ob ein Bild links oder rechts landet. Lädt beim ersten Start ca. 260 MB.

**Nimm:** `fly_tinder.py` als Einstieg in Konnektom-Daten.
</details>

### 🧰 Werkzeuge

<details>
<summary><b>Personal Dashboard</b> · 🟡 Prototyp</summary>

<br>

React/Vite/Tailwind + Fastify + SQLite · [Repo](https://github.com/Nikros07/Personal-Dashboard)

Obsidian-Sync, Aufgaben, Volltextsuche (SQLite FTS5), System-Monitoring. **Nimm:** `backend/` und `frontend/` als Gerüst.
</details>

<details>
<summary><b>Hermes AI Dashboard</b> · 🟡 lokal, noch ohne Repo</summary>

<br>

Next.js, Tailwind, Framer Motion · Widget-Board mit Drag-and-Drop, Strg+K-Suche, Demo-Daten ohne Schlüssel.
</details>

<details>
<summary><b>Health Tracker</b> — installierbare PWA · 🟢</summary>

<br>

HTML/JS · [Repo](https://github.com/Nikros07/Health-Tracker)

**Nimm:** `manifest.json` + `sw.js` als Minimal-Vorlage für „App aufs Handy installieren".
**Vorsicht:** `js/github-storage.js` speichert Daten im öffentlichen Repo, für private Daten nicht übernehmen.
</details>

---

## 🎓 Was ich gelernt habe

```mermaid
flowchart LR
    S["Tolles Backtest-Ergebnis"] --> C1{"Blick in die Zukunft?"}
    C1 -->|ja| X["❌ Messfehler"]
    C1 -->|nein| C2{"Nur ein gutes Jahr?"}
    C2 -->|ja| X
    C2 -->|nein| C3{"Kosten und Steuern drin?"}
    C3 -->|nein| X
    C3 -->|ja| C4{"Schlägt den dümmsten Konkurrenten<br/>auf frischen Daten?"}
    C4 -->|nein| X
    C4 -->|ja| OK["✅ Erst dann Papierhandel"]
```

1. **Nichts tun ist ein gültiges Ergebnis.** Kein Pfad darf einen Trade erzwingen.
2. **Der Code rechnet, die KI redet.** Alles, was Geld berührt, ist normaler, testbarer Code.
3. **Widerspruch einbauen.** Ein Skeptiker, der widersprechen *muss*, schlägt freundliche Agenten.
4. **Ehrlich messen:** Walk-forward statt Auswahldaten, frische Seeds, Kosten zuerst.
5. **Billig betreiben:** Cron statt Dauerbetrieb, GitHub Actions statt Server, Zustand auf eigenem Branch.

---

## 🤖 Für AI-Agents

Dieses Repo ist auch für Agents gebaut:

- [`projects.json`](projects.json): strukturierter Index (Tags, Status, wiederverwendbare Pfade, Vorsichtshinweise)
- [`AGENTS.md`](AGENTS.md): Vorgehen, Entscheidungstabelle und Regeln (keine Schlüssel, nur Papierhandel, Pfade vor dem Empfehlen prüfen)

---

<div align="center">

Wenn du etwas verwendest, verlinke kurz dieses Repo: **https://github.com/Nikros07/Projects** · [CC BY 4.0](LICENSE)

<sub>Stand 2026-10-01 · Keine Anlageberatung · Vieles ist Prototyp</sub>

</div>
