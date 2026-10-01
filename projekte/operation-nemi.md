# Operation NEMI

> Quantitative Anlage-Forschung, bei der **NO TRADE** das Standardergebnis ist —
> der bewusste Gegenentwurf zu [Apex Capital](apex-capital.md).

| | |
|---|---|
| **Repo** | https://github.com/Nikros07/Operation-NEMI |
| **Stack** | Python 3.11 (eigenes venv), Backtester, Paper-Modul, Railway-Cron |
| **Start** | 2026-08-28 |
| **Stand** | Erster Echtdaten-Backtest 2026-08-31: **nicht profitabel**, kein Setup validiert |

## Worum es geht
NEMI übernimmt von Apex, was gut war (Datenzugriff, Indikator-Mathematik,
deterministische Risikoformeln, AI-Routing, Dashboard-Transport) und ersetzt die
Entscheidungsarchitektur. Feste Regeln:

- **Kein Forced-Trade-Pfad — niemals.** NO TRADE ist ein normales Ergebnis.
- **Deterministisches Python besitzt jede Zahl, die Kapital berührt.** KI ist Beiwerk.
- Startkapital ~1.000 €; Einzahlungen müssen von Performance trennbar bleiben
  (zeitgewichtete Rendite).
- **Nichts erreicht echtes Kapital ohne Out-of-Sample-Validierung.**

## Ergebnis des ersten Backtests (7,7 Jahre, 161 Symbole, Benchmark SPY +227 %)
- Balanced −5,7 %, Aggressive −28,7 %.
- Walk-forward widerlegte auch das beste Setup (`trend_breakout_long`): 0 von 3
  auswertbaren Testfenstern hielten — der Vorteil existierte nur in den
  Auswahldaten.
- Die gesamte positive Performance stammte aus **2020** (Corona-Crash); jedes
  Jahr danach negativ.
- Empfehlung: kein Kapital, kein Paper-Trading; stattdessen Regimeabhängigkeit
  vorab erkennbar machen oder **neue Hypothesen** statt Feinschliff an den
  bestehenden sechs.

## Betrieb
Railway (5-€-Starter) als **Cron-Job**, nicht Dauerbetrieb: werktags 22:30 UTC,
Volume auf `/data`. Gesammelt werden 1d/1h/15m/5m (~430 MB/Jahr), **kein 1m**:
nur 1m hat Yahoos 30-Tage-Grenze und würde Dauerbetrieb erzwingen. Deployt ist
bewusst nur ein **Datensammler** — kein Kapital, keine Ausführung.

## Das kannst du mitnehmen
- Ein **Negativ-Ergebnis sauber zu dokumentieren** ist ein Ergebnis
  (`docs/RESULTS.md`, `docs/AUDIT.md`, `docs/ARCHITECTURE.md` im Repo).
- **Sammle Daten zuerst, handle später.** Ein Datensammler im Cron kostet
  Centbeträge und macht jeden späteren Backtest besser.
- Datenfrequenz nach **Datenquellen-Limit** wählen, nicht nach Wunsch.
- Prüfe jeden Gewinn auf **ein einzelnes Jahr/Regime**: Wenn alles aus einem
  Ereignis stammt, ist es keine Strategie.

## Verwandt
[Apex Capital](apex-capital.md), [Fly of Wallstreet](fly-of-wallstreet.md)
(bewusst eigenes Repo, nicht Teil von NEMI), [LERNEN.md](../LERNEN.md).
