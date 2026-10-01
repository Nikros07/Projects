# Hermes AI Dashboard

> Apple-inspirierte persönliche KI-Kommandozentrale für Produktivität, Kalender,
> Notizen, Ziele, Finanzen, Krypto, Aktien, Fitness und Benachrichtigungen.

| | |
|---|---|
| **Repo** | **noch keins** — lokal (`Nick/1. Projects/Hermes-AI-Dashboard`, initialer Commit 2026-10-01, kein `origin`) |
| **Stack** | Next.js (App Router), React, TypeScript, Tailwind, Framer Motion, Docker, PWA |
| **Stand** | läuft vollständig mit Demo-Daten; echte Anbindungen vorbereitet |

## Funktionen
Hermes AI Center (Chat, Verlauf, Favoriten, Suche, vorbereitete Upload-/Sprach-Kontrollen) ·
`Strg+K`-Suche · Drag-and-Drop-Widget-Board mit gespeichertem Layout · Live-Uhr ·
Wetter · Aufgaben, Kalender, Ziele, Portfolio, Krypto, Aktien, Fitness · Themes
mit eigenen Akzentfarben · lokaler AES-GCM-Helfer für verschlüsselten Export/Import.

## Das kannst du mitnehmen
- **Läuft ohne Schlüssel:** Demo-Daten als Standard, echte Dienste per `.env.local`
  zuschaltbar (`HERMES_API_KEY`, `OPENWEATHER_API_KEY`, Kalender-/Inbox-IDs).
- **Command-Palette (`Strg+K`)** und **persistentes Widget-Layout** sind
  Wiederverwendbares für jedes Dashboard.
- Lokale **AES-GCM-Verschlüsselung** für Export/Import — Daten, die den Browser
  verlassen, bleiben verschlüsselt.
- Dockerfile + PWA-Manifest von Anfang an.

## Offen
Eigenes GitHub-Repo anlegen und pushen · echte Anbindungen (Wetter, Kalender, Hermes).

## Verwandt
[Personal Dashboard](personal-dashboard.md).
