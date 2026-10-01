# Eye of Horus

> Event-to-Market-Intelligence und autonome Trading-Plattform: verfolgt die
> Kausalkette von realen Ereignissen bis zur Marktwirkung, mit erzwungener
> Look-ahead-Freiheit in jedem Schritt.

| | |
|---|---|
| **Repo** | https://github.com/Nikros07/Eye-of-Horus |
| **Stack** | FastAPI + SQLAlchemy 2.0 + Pydantic v2 · Next.js 16, React 19, TypeScript, Tailwind, React Three Fiber |
| **Stand** | Demo-Modus komplett; Live-Konnektoren implementiert, Umschalten ist eine Konfiguration |
| **Letzter Push** | 2026-10-01 |

## Die Pipeline
```
EVENT → VERIFIKATION → IMPACT-GRAPH → SIGNAL → BACKTEST → PAPER-TRADE → ERGEBNIS
```
Forschungsfrage, nicht Annahme: **Hat das System echte Informationen früh und
zuverlässig genug erkannt, um messbaren Informationswert zu liefern?**

## Bausteine
- **Event Engine:** Ereignisse (Extremwetter, Infrastruktur, Lieferketten) aus
  mehreren unabhängigen Quellen verifizieren (NASA EONET, Open-Meteo), auf
  einem 3D-Globus verorten.
- **Impact Engine:** regelbasierter Graph Ereignis → Infrastruktur → Lieferkette
  → Rohstoff/Asset, mit Exposure-Score je Hop.
- **Signal Engine:** fünf Strategien, darunter eine naive Basislinie, die alle
  anderen schlagen müssen; jede liefert Konfidenz und Klartext-Begründung.
- **Quant Engine:** ereignisgetriebener Backtester mit **adversarial getesteter
  Temporal-Integrity-Sperre** — kein Backtest darf Daten nach dem simulierten
  Zeitpunkt sehen.
- **Trading Engine:** `RiskEngine` → `BrokerAdapter` → `PaperBroker` (oder Alpaca-
  Papierkonto); automatischer Modus ist opt-in. `LiveBroker` ist absichtlich nur ein Stub.
- **AI Research:** jede Aussage getaggt als OBSERVED / DERIVED / HYPOTHESIS /
  UNCERTAIN; ohne Claude-Key springt ein deterministischer Synthesizer ein —
  nichts wird erfunden.

## Demo vs. Live
`DATA_MODE=demo` (Standard) nutzt deterministische Generatoren; **jede Zeile ist
Ende-zu-Ende als `is_demo: true` markiert** und im UI mit DEMO-Badge sichtbar.
Der Demo-Generator baut einen kleinen Drift nach Ereignissen ein, damit das
Backtest-Labor etwas findet — ausdrücklich **kein** Beleg für echten Vorsprung.

## Das kannst du mitnehmen
- **Demo-Daten immer kennzeichnen**, von der Datenbank bis zum UI. Verhindert,
  dass Spielzeug-Zahlen für echt gehalten werden.
- **Temporal-Integrity-Guard:** eine Zugriffsschicht, die zukünftige Daten
  physisch verweigert, statt sich auf Disziplin zu verlassen — und ein Test, der
  versucht, sie zu umgehen.
- **Naive Basislinie als Pflichtgegner** für jede Strategie.
- **Provenienz-Tags (OBSERVED/DERIVED/HYPOTHESIS/UNCERTAIN)** machen KI-Texte
  prüfbar.
- Broker hinter einem **Adapter-Interface**, Live-Variante absichtlich gesperrt.

## Verwandt
[Operation NEMI](operation-nemi.md) (gleiche Ehrlichkeitsregeln),
[LERNEN.md](../LERNEN.md).
