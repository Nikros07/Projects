# MT5 Master Strategy

> Zwei bewusst getrennte Stränge: ein MetaTrader-5-Expert-Advisor für Forex/CFD
> (Prop-Firm) und ein ETF-Momentum-Portfolio, gemessen gegen DAX und S&P 500.

| | |
|---|---|
| **Ort** | lokal im Obsidian-Vault (`1. Projects/MT5-Master-Strategy/`), **kein eigenes Repo** |
| **Stack** | MQL5, Python (pandas, numpy, yfinance) |
| **Stand** | EA **v7**, Python **v4** (2026-08-29) |

## Strang A — MT5-EA
- **v6** (Einzelpaar EURUSD H1, Turtle-Stop) wurde real gemessen: Profit Factor
  **0,88**, vor Spreadkosten bei exakt null.
- **v7:** kompletter Ansatzwechsel auf bis zu **13 Märkte gleichzeitig**,
  Tagesbasis statt H1 (Spread fällt von 6,3 % auf 0,9 % des Risikos),
  Währungs-Klumpenschutz, volatilitätsnormierte Größe.
- v7 kompiliert; **erster Testlauf steht aus.** Wichtigste Prüfung: wie viele der
  13 Märkte das MT5-Journal wirklich meldet (unter 8 ist der Test wertlos).

## Strang B — ETF-Portfolio (`adaptive_momentum_v4.py`)
Monatlich Top-2 aus SPY/QQQ/EWG/EFA/GLD nach 1/3/6-Monats-Momentum, defensiv
IEF/BIL, Vol-Target 15 %, Hebel max. 1,5×.

| Messgröße (nach deutscher Steuer) | Wert |
|---|---|
| Strategie | 10,02 % p. a. |
| DAX | 8,75 % |
| S&P-500-Buy-and-Hold | **10,56 %** (schlägt die Strategie) |
| Max-Drawdown | −19,3 % statt −24,6 % |
| Walk-Forward, 30 Fenster seit 2007 | DAX in 63 % geschlagen, Median +1,09 Pp. |

Der reale Vorteil ist das **Risiko**, nicht die Rendite.

## Zwei Vermutungen, die falsch waren
- Quartals- statt Monats-Rebalancing spart *keine* Rendite — es kostet welche
  (8,67 % statt 11,80 % netto): das Signal verfällt schneller als die Steuer.
- Die Abgeltungssteuer killt den DAX-Vorsprung *nicht* (~3,9 Pp. p. a., Vorsprung bleibt).

## Das kannst du mitnehmen
- **Miss Kosten, bevor du Signale verfeinerst.** v6 hatte vor Kosten null Edge — dann
  hilft kein Feintuning. Wechsel auf Tagesbasis hat das Kostenproblem gelöst.
- **Vergleiche immer mit dem dümmsten Konkurrenten** (hier: S&P kaufen und halten).
- **Prüfe Parametervarianten zufallsbereinigt** (hier 23 geprüft) und mit
  Walk-Forward über rollende Fenster.
- **Dokumentiere widerlegte Vermutungen**, damit niemand sie erneut vorschlägt.
- Headless kompilieren: `MetaEditor64.exe /compile:<pfad> /log:<pfad>` (Log ist UTF-16).
- Vor jedem „live schalten": Validierungs-Checkliste im Vault durchgehen.

## Offen
Erster v7-Testlauf · UCITS-Backtest mit real handelbaren Tickern · lohnt sich der
Aufwand bei nur 1,3 Pp. DAX-Vorsprung (und Rückstand zum S&P) überhaupt?
