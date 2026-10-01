# Personal Dashboard

> Lokales, persönliches Dashboard mit Obsidian-Memory, KI-Agenten (Hermes),
> Aufgaben, Dateiautomatisierung und System-Monitoring.

| | |
|---|---|
| **Repo** | https://github.com/Nikros07/Personal-Dashboard |
| **Stack** | React 18 + TypeScript + Vite + Tailwind + shadcn/ui · Node + Fastify · SQLite (FTS5) |
| **Stand** | Prototyp/Gerüst (letzter Push 2026-07-01, mit GitHub-Pages-Workflow) |

## Funktionen (geplant/gerüstet)
Obsidian-Sync über das Local-REST-API-Plugin · Hermes-Agenten (Chat,
Memory-Review, PDF-Zusammenfassung, Task-Generator) · Kanban/Listen-Aufgaben ·
File-Watcher mit Automatisierung · globale Volltextsuche · Projekt-Dashboards mit
Git-Status · CPU/GPU/RAM-Widgets · Quick Actions · Analytics · Dark/Light mit
Glassmorphism.

## Struktur
`frontend/` (React) · `backend/` (Fastify) · `scripts/` (Watcher, Summarizer) ·
`skills/` (Hermes-Skills) · `docs/`.

## Das kannst du mitnehmen
- **SQLite + FTS5** reicht für lokale Volltextsuche über Notizen — kein Elasticsearch nötig.
- **Obsidian als Gedächtnis** einer KI: Notizen lesen/schreiben über das
  REST-Plugin, damit der Agent dort lernt, wo du ohnehin arbeitest.
- Lokale Modelle (Ollama/GPT4All) als Fallback ohne Cloud-Kosten.
- Ein `start.bat` für Ein-Klick-Start unter Windows.

## Verwandt
[Hermes AI Dashboard](hermes-ai-dashboard.md) (zweiter Anlauf, anderes Gerüst).

> **Hinweis zur Ordnung:** Der Obsidian-Vault, in dem dieses Projekt liegt, zeigt
> mit seinem `origin` noch fälschlich auf dieses Repo — nicht aus dem Vault pushen.
