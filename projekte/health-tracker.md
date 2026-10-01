# Health Tracker

> Installierbare Web-App („PWA"), um den eigenen Konsum von Alkohol und Nikotin
> mitzuzählen.

| | |
|---|---|
| **Repo** | https://github.com/Nikros07/Health-Tracker |
| **Stack** | HTML, CSS, ES-Module (JavaScript), Web-App-Manifest, Service Worker, GitHub-Contents-API als Speicher |
| **Stand** | klein, fertig (April 2026) |

Dunkles Design, Hochformat, Modal „Eintrag hinzufügen", Kategorien mit Tageslimit
und Unterkategorien, Diagramme. Der Service Worker cached die App-Dateien, sie lässt
sich auf dem Handy wie eine App installieren.

## Wie die Daten gespeichert werden
`js/github-storage.js` liest und schreibt `data/tracker-data.json` **im Repo selbst**
über die GitHub-API; das Token liegt nur im `localStorage` des Geräts. Praktisch:
kein eigener Server, Sync zwischen Geräten gratis, Versionsverlauf inklusive.

> ⚠️ **Datenschutz:** Das Repo ist öffentlich. Ein Tracker für Alkohol-/Nikotinkonsum
> sollte seine Daten **nicht** in einem öffentlichen Repo ablegen. Entweder das Repo
> auf *privat* stellen oder die Daten in ein separates privates Repo auslagern.
> (Beim Erstellen dieser Übersicht enthielt die Datei nur die Kategorien-Vorlage;
> sobald echte Einträge synchronisiert werden, wären sie öffentlich lesbar.)

## Das kannst du mitnehmen
- **Minimal-PWA als Vorlage:** `manifest.json` + `sw.js` + `index.html`.
- **„GitHub als Datenbank"** für Ein-Personen-Apps: Datei im Repo, API zum
  Lesen/Schreiben, SHA zur Konflikterkennung. Funktioniert — aber nur mit **privatem**
  Repo, wenn die Daten privat sind.
- Das Repo hat noch **keinen README** — ein kurzer Absatz würde es nutzbar machen.
