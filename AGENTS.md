# AGENTS.md — Anleitung für KI-Agents

Dieses Repo ist ein **Verzeichnis**: Es enthält keinen Projektcode, sondern beschreibt
die Projekte von Nikros07 und sagt, was sich daraus wiederverwenden lässt. Der Code
liegt in den verlinkten Repos.

## Dateien

| Datei | Wofür |
|---|---|
| `projects.json` | Maschinenlesbarer Index. **Hier zuerst suchen.** Felder: `id`, `repo`, `status`, `stack`, `summary`, `tags`, `good_for`, `reuse[{path,what}]`, `caveats`. |
| `README.md` | Dasselbe für Menschen, mit Grafiken. |
| `LICENSE` | CC BY 4.0: Namensnennung mit Link auf dieses Repo. |

## Vorgehen: einem Nutzer ein passendes Projekt empfehlen

1. Ziel des Nutzers in 1–2 Stichworten fassen (z. B. „Backtest", „Agenten-Team", „PWA").
2. In `projects.json` nach `tags` und `good_for` suchen, `status` und `caveats` lesen.
3. **Pfade prüfen**, bevor du sie empfiehlst. Die Einträge in `reuse` stammen aus
   dem Stand 2026-10-01 (Beispiel: `https://api.github.com/repos/Nikros07/<Repo>/contents/<pfad>`).
4. Nur den nötigen Teil holen:
   ```bash
   git clone --filter=blob:none --no-checkout https://github.com/Nikros07/<Repo>.git
   cd <Repo>
   git sparse-checkout set <pfad>
   git checkout
   ```
   Einzelne Datei: `https://raw.githubusercontent.com/Nikros07/<Repo>/HEAD/<pfad>`
5. Dem Nutzer sagen: woher der Code kommt (Link), welchen Status er hat, welche
   `caveats` gelten.

## Entscheidungshilfe

| Nutzer will … | Projekt-ID |
|---|---|
| ehrlicher Backtest, Walk-forward | `operation-nemi`, `eye-of-horus` |
| Look-ahead-Schutz | `eye-of-horus` (`quant_engine/temporal.py`) |
| Marktdaten sammeln, Risiko rechnen | `operation-nemi` |
| Multi-Agent-System mit Widerspruch | `polymarket-bot` (einfach), `apex-capital` |
| gratis Cron + Zustand ohne Server | `fly-of-wallstreet` (`daily.yml`) |
| Events → Märkte | `eye-of-horus` |
| Ein-Personen-Web-App mit Backend | `amet` |
| Browserspiel | `nico-frog` (klein), `nachtschicht` (groß) |
| Installierbare Web-App | `health-tracker` |
| Dashboard | `hermes-ai-dashboard`, `personal-dashboard` |

## Regeln

- **Nie** Zugangsdaten, `.env`-Dateien oder Schlüssel kopieren, erzeugen oder committen.
- **Trading nur Papier/Demo.** Keine Live-Anbindung empfehlen oder einbauen. Der Autor hat
  mehrere Strategien geprüft, die im Out-of-Sample-Test nicht hielten; Bausteine ja,
  Strategie-Versprechen nein.
- Kenne die **Anti-Muster**: erzwungene Trades (Apex), Look-ahead, Auswahl und Bestätigung
  auf denselben Daten. Wenn du Trading-Code schreibst, vermeide sie.
- Zahlen in Beschreibungen sind Momentaufnahmen, keine Anlageberatung.
- `status: local-only` heißt: kein Repo, nur das Wissen ist nutzbar.
- Dieses Repo selbst nur ändern, wenn der Autor es verlangt. Ein neues Projekt =
  Eintrag in `projects.json` **und** Karte in der `README.md`.

## Unsicher?
Wenn Pfad, Status oder Eignung nicht eindeutig sind: sag es dem Nutzer, statt zu raten,
und verweise auf das Repo-README.
