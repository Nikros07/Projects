# Polymarket Bot ("AI Decision System")

> Ein 10-Agenten-„OASIS"-Entscheider für Sportwetten, Prognosemärkte und andere
> probabilistische Ereignisse.

| | |
|---|---|
| **Repo** | https://github.com/Nikros07/Polymarket-Bot |
| **Stack** | Python, Streamlit-UI, FastAPI-Backend, OpenRouter/Tavily |
| **Stand** | ruht seit April 2026 (letzter Commit 2026-04-13, Branch `claude/ai-decision-system-…`) |

## Architektur
Sieben Stufen: Scan & Parse → Recherche → Vorhersage + Analyse (parallel) →
Szenarien → Validierung → Synthese → Scoring.

| Agent | Aufgabe |
|---|---|
| Scanner, InputParser | Entitäten erkennen, Anfrage normalisieren |
| Research | Informationen sammeln (Tavily/Serper) |
| Predictor | erste Wahrscheinlichkeit |
| Analyst / Skeptic | Pro-Argument / **muss widersprechen** |
| Scenario, Validator | Alternativen durchspielen, Logik prüfen |
| Synthesizer, Scoring | zusammenführen, gewichtet bewerten |

Dazu: Debate Agent, Sports Predictions, „Wisdom of Crowd".

## Betrieb ohne Kosten
Drei Wege: **A** OpenRouter (kostenlose Modelle, keine Karte), **B**
Anthropic/OpenAI, **C** Demo-Modus komplett ohne Schlüssel.

## Das kannst du mitnehmen
- **Skeptiker, der widersprechen *muss*:** erzwungene Gegenposition verhindert
  Bestätigungsfehler im Agenten-Team.
- **Drei Betriebsmodi** (gratis / bezahlt / Demo) machen ein Projekt für andere
  sofort startbar.
- Neue Domäne oder neuer Agent sind im README als Erweiterungspunkte beschrieben —
  ein gutes Muster für Plugin-artige Agentensysteme.
- **Hinweis:** Repo-Name und README-Titel unterscheiden sich (Bot vs. Decision
  System) — beim Wiederaufnehmen vereinheitlichen.

## Verwandt
[Apex Capital](apex-capital.md) (gleiches Debattenmuster).
