# Nachtschicht

> Pixel-Art-Partyspiel im Browser über eine Nacht, die aus dem Ruder läuft.
> Kein Download, keine Installation, kein Konto.

| | |
|---|---|
| **Repo** | https://github.com/Nikros07/Nachtschicht |
| **Spielen** | ▶ https://nikros07.github.io/Nachtschicht/ |
| **Stack** | Vanilla-JS, klassische `<script>`-Tags (läuft von `file://`), Canvas mit Bitmap-Font, GitHub Pages |
| **Stand** | spielbar (8 Level); Nachtroutinen vorbereitet |

## Die Level
1 Schule · 2 Bei Moritz · 3 Der Nachtbus · 4 Die Schlange · 5 Club · 6 Afterhour ·
7 Späti · 8 Heimweg. Jedes Level ist eine Stufe des Abends. Schleichen, Werfen,
Taschenlampe, Handy stumm schalten, Kämpfe, Pegel — Steuerung auch für Touch
(Querformat).

## Besonderheit: das Projekt baut sich nachts selbst weiter
**Eine** Cloud-Routine arbeitet jede Nacht — **auf einem eigenen Branch
`claude/nacht`, nie auf `main`** (sonst würde die Live-Seite überschrieben). Der
Prompt in der Oberfläche hat nur ~12 Zeilen: Branch holen, Anleitung lesen, dazu die
harten Grenzen. Die ganze Anleitung steht in `routinen/nacht.md` und wird von der
Cloud-Sitzung selbst aus dem Repo geholt — versioniert, und eine Änderung braucht
keinen Eingriff in die Oberfläche.

*Warum eine statt zwei (frühere Fassung: Testen um 4, Bauen um 5):* Das Nutzungslimit
ist ein Fünf-Stunden-Fenster am Konto. Zwei Läufe im Abstand einer Stunde teilen sich
dasselbe Fenster und bringen nicht mehr Arbeit, nur doppelten Aufwand — der zweite
liest alles noch einmal. Die zwei alten Prompts bleiben als Vorlage.

Morgens: `NACHT-LOG.md` lesen, `git log main..origin/claude/nacht` ansehen, mergen oder verwerfen.

**Stand (2026-10-01):** Anleitung und Warteschlange stehen lokal; das Anlegen der
Cloud-Routine wartet noch auf eine `environment_id`. Cron läuft in UTC — am
25.10.2026 (Winterzeit) um eine Stunde anpassen.

> ⚠️ **Auf GitHub fehlen diese Dateien noch** (`NACHT-TODO.md`, `routinen/`,
> `CLAUDE.md`, Skill `todo-notieren`, `tools/nachttest.js`): Sie liegen in
> lokalen, noch ungepushten Commits. Wer sie nachbauen will: Beschreibung in
> [BAUSTEINE.md](../BAUSTEINE.md), Nr. 3, oder bei mir nachfragen.

## Das kannst du mitnehmen
- **Warteschlange als Gedächtnis:** Die Nacht-Sitzung hat keine Erinnerung an den
  Tag. Alles Offene muss in `NACHT-TODO.md` stehen, mit **P1/P2/P3**-Priorität und
  einem **messbaren „Fertig wenn"** — ohne das wird nichts abgehakt.
- **Skill `todo-notieren`:** am Ende jeder Aufgabe automatisch Offenes eintragen
  (steht als Pflicht in `CLAUDE.md`).
- **Erst testen, dann bauen — im selben Lauf:** Erst misst die Routine den Ist-Zustand
  und trägt Funde in die Warteschlange ein, dann arbeitet sie diese ab. Wer lieber
  strikt trennt (Tester ändert nichts, Bauer baut), nimmt die zwei alten Prompts —
  zwei Läufe teilen sich aber das Nutzungslimit.
- **Sicherheit durch Branch-Präfix `claude/`**, zusätzlich im Prompt verboten:
  `main`, `--force`, Löschen. „Entscheidung nötig" fassen Routinen nicht an.
- **Test ohne Browser:** `tools/nachttest.js` setzt Engine und Level headless
  zusammen und spielt jede Seite in ~2 s durch (Ausnahmen, NaN, tote
  Gesprächsverweise). Grenzen sind ehrlich benannt: keine Pixel, kein Ton.
- **Messen statt raten:** `update(1/60)` in einer Schleife, Werte auslesen.
- Alle Stellschrauben stehen im `TUNE`-Block des Levels, nicht in der Logik.
- Bitmap-Font ohne Umlaute → im Canvas ae/oe/ue/ss, im HTML dürfen sie stehen.

## Verwandt
[BAUSTEINE.md](../BAUSTEINE.md) → „Nacht-Warteschlange".
