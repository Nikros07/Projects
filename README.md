# Meine Projekte

Hier steht, was ich schon gebaut habe. Willst du etwas Ähnliches machen? Schau, was
dazu passt, und nimm dir den Teil, den du brauchst. Jedes Projekt hat sein eigenes
Repo (verlinkt), hier sind nur die Erklärungen.

Wenn du etwas verwendest, verlink bitte kurz dieses Repo: https://github.com/Nikros07/Projects

---

## Trading & Finanzen

### Apex Capital — 10 KI-Agenten, die Aktien debattieren
[Repo](https://github.com/Nikros07/Apex-Capital) · Python, FastAPI · läuft live (nur Papiergeld)
Agenten mit Rollen (Makro, Technik, Fundamental, Risiko, Bulle, Bär, CIO, Teufelsanwalt) recherchieren und streiten, bevor getradet wird.
**Das kannst du nutzen:** `agents/` als Vorlage für ein Agenten-Team mit Rollen und Widerspruch.

### Operation NEMI — Trading-Forschung mit „NO TRADE" als Standard
[Repo](https://github.com/Nikros07/Operation-NEMI) · Python
Backtester mit Walk-forward und Monte Carlo, Yahoo-Datensammler, Risiko-Rechnung. Ergebnis ehrlich: im Test nicht profitabel.
**Das kannst du nutzen:** `nemi/backtest/` (ehrlich testen), `nemi/data/` (Marktdaten sammeln), `nemi/risk/` (Positionsgröße, Stops).

### Fly of Wallstreet — Fliegengehirn lernt Trading
[Repo](https://github.com/Nikros07/Fly-of-Wallstreet) · Python · läuft gratis auf GitHub Actions
Künstliche Fruchtfliegen (Pilzkörper + Dopamin) lernen, wöchentlich Auslese. Ergebnis ehrlich: kein belegter Vorsprung vor dem Index.
**Das kannst du nutzen:** `.github/workflows/daily.yml` (kostenloser täglicher Job mit Zustand auf eigenem Branch), `fly/evolution.py` (evolutionäre Auslese), `fly/broker.py` (Alpaca-Papierkonto).

### Eye of Horus — von Ereignissen zu Marktwirkung
[Repo](https://github.com/Nikros07/Eye-of-Horus) · FastAPI, Next.js, 3D-Globus
Wetter-/Katastrophen-Ereignisse → Impact-Graph → Signale → Backtest → Papierhandel. Läuft im Demo-Modus ohne Schlüssel.
**Das kannst du nutzen:** `backend/app/services/quant_engine/` (Backtester, der Zukunftsdaten verweigert), `event_engine/` (NASA EONET, Open-Meteo).

### Polymarket Bot — Entscheidungs-Engine für Wetten und Prognosemärkte
[Repo](https://github.com/Nikros07/Polymarket-Bot) · Python, Streamlit · ruht seit April
10 Agenten in Stufen, mit einem Skeptiker, der widersprechen muss. Läuft auch gratis oder ganz ohne API-Schlüssel (Demo).
**Das kannst du nutzen:** `backend/agents/` und `backend/core/orchestrator.py` für eine Agenten-Pipeline.

### MT5 Master Strategy — Forex-Robot und ETF-Portfolio
Lokal, kein eigenes Repo · MQL5, Python
EA v7 (13 Märkte, Tagesbasis) und ein ETF-Momentum-Portfolio, gemessen gegen DAX und S&P 500. Erkenntnis: Der Vorteil liegt im geringeren Risiko, nicht in der Rendite; Kosten haben die erste Version zerstört.

### Amet — private Finanz-App
[Repo](https://github.com/Nikros07/Amet) · Vanilla-JS + Supabase
Wallets, Budgets, Sparziele, Forecast, KI-Assistent. Kein Bankzugriff, alles manuell.
**Das kannst du nutzen:** `supabase/` (Schema + Migrationen) und `js/` als Muster für eine Ein-Personen-App ohne Build.

---

## Spiele

### Nachtschicht — Pixel-Partyspiel im Browser
[Repo](https://github.com/Nikros07/Nachtschicht) · [▶ spielen](https://nikros07.github.io/Nachtschicht/) · Vanilla-JS, 8 Level
**Das kannst du nutzen:** `nacht/` als Spiel-Engine ohne Framework (Welt, Kampf, Dialoge, Ton, Touch-Steuerung).

### Nico Frog — Mini-Spiel in einer Datei
[Repo](https://github.com/Nikros07/Nico-Frog) · eine HTML-Datei
**Das kannst du nutzen:** als kleinste Vorlage für ein Browserspiel.

### Fuck the Fly — ein echtes Fliegenhirn swiped Bilder
[Repo](https://github.com/Nikros07/Fuck-the-Fly) · Python, `pip install flybrain`
**Das kannst du nutzen:** als Einstieg, um mit einem echten Gehirn-Modell (166.700 Neuronen) zu spielen.

---

## Persönliche Werkzeuge

### Personal Dashboard
[Repo](https://github.com/Nikros07/Personal-Dashboard) · React/Vite + Fastify + SQLite
Dashboard mit Obsidian-Anbindung, Aufgaben, Volltextsuche, System-Monitoring. Prototyp.

### Hermes AI Dashboard
Lokal, noch kein Repo · Next.js, Tailwind
Kommandozentrale mit Widget-Board, Strg+K-Suche, Demo-Daten. **Das kannst du nutzen:** Idee und Aufbau für ein eigenes Dashboard.

### Health Tracker
[Repo](https://github.com/Nikros07/Health-Tracker) · HTML/JS-PWA
Installierbare Tracker-App. **Das kannst du nutzen:** `manifest.json` + `sw.js` als Minimal-Vorlage für „App aufs Handy installieren".

---

## Was ich daraus gelernt habe (Kurzfassung)
- Wenn ein Backtest toll aussieht, ist es meistens ein Messfehler (Blick in die Zukunft, nur ein gutes Jahr, Kosten vergessen).
- „Nichts tun" muss ein gültiges Ergebnis sein, nie einen Trade erzwingen.
- Alles, was Geld berührt, rechnet normaler Code, nicht die KI.
- Trading nur auf Papier, bis es außerhalb der Testdaten bewiesen ist.

*Keine Anlageberatung. Vieles hier ist Prototyp.*
