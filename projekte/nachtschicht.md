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
Zwei Cloud-Routinen (Prompts liegen im Repo unter `routinen/`) sollen jede Nacht
arbeiten — **auf einem eigenen Branch `claude/nacht`, nie auf `main`** (sonst würde
die Live-Seite überschrieben):

| Zeit | Routine | Aufgabe |
|---|---|---|
| 4:00 | `nacht-4-testen` | testet alles, schreibt `NACHT-BERICHT.md`, trägt Funde in die Warteschlange ein; ändert **keinen** Spielcode |
| 5:00 | `nacht-5-weiterbauen` | arbeitet `NACHT-TODO.md` von oben ab, testet jede Änderung, ein Commit je Punkt |

Morgens: `NACHT-LOG.md` lesen, `git log main..origin/claude/nacht` ansehen, mergen oder verwerfen.

**Stand:** Prompts und Warteschlange stehen; das Anlegen der Cloud-Routinen wartet
noch auf eine `environment_id`. Cron läuft in UTC — am 25.10.2026 (Winterzeit)
auf `0 3` / `0 4` umstellen.

## Das kannst du mitnehmen
- **Warteschlange als Gedächtnis:** Die Nacht-Sitzung hat keine Erinnerung an den
  Tag. Alles Offene muss in `NACHT-TODO.md` stehen, mit **P1/P2/P3**-Priorität und
  einem **messbaren „Fertig wenn"** — ohne das wird nichts abgehakt.
- **Skill `todo-notieren`:** am Ende jeder Aufgabe automatisch Offenes eintragen
  (steht als Pflicht in `CLAUDE.md`).
- **Trennung Tester / Bauer:** Die 4-Uhr-Routine darf nichts ändern, die 5-Uhr
  darf bauen — so prüft niemand seine eigene Arbeit.
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
