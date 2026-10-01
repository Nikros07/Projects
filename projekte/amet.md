# Amet — Private Finance

> Privates Finance-Command-Center: trackt reale Geldbereiche, rechnet daraus
> Gesamtvermögen und „direkt verfügbares" Geld gegen einen Zielbereich.

| | |
|---|---|
| **Repo** | https://github.com/Nikros07/Amet |
| **Stack** | Vanilla-JS (ES-Module, kein Build), Supabase (Postgres + Auth + Row-Level-Security + Edge Function), GitHub Pages |
| **Stand** | Phasen A–D fertig (Datenmodell, Schnelleingabe, Redesign, Analytics/Ziele/Budgets/Forecast); KI-Assistent clientseitig fertig, Edge Function noch einmalig zu deployen |

## Idee
Kein Bankzugriff, kein Open Banking, keine automatische Synchronisierung — alle
Buchungen werden bewusst von Hand erfasst. Wallets (Konto, Bargeld, Reserve,
Krypto, Geldbeutel) sind Konten im Ledger-Sinn, kein Wallet kann ins Minus
rutschen. Anfangssalden pro Wallet möglich.

## Funktionen
Schnelleingabe · Navigation · Sparziele & Budgets · Analytics · Forecast ·
KI-Assistent „AMET AI" (über Supabase Edge Function).

## Das kannst du mitnehmen
- **Eine App ohne Build:** Vanilla-ES-Module + `python -m http.server` genügen;
  ideal für GitHub Pages.
- **Supabase als komplettes Backend** (Schema, Migrationen 002–005 in Reihenfolge,
  RLS als eigentlicher Schutz — der anon key darf öffentlich sein).
- **Signups abschalten, genau einen Nutzer anlegen:** bewusst kein
  „Registrieren"-Knopf für Ein-Personen-Apps.
- **Ownership-Checks in Migrationen** statt nur im Client.
- Kein Wallet ins Minus: Constraint in der Datenbank, nicht in der Oberfläche.
- Der Setup-Teil des README ist ein gutes Muster: nummerierte, vollständige Schritte.

## Offen
Edge Function deployen · nach `.nojekyll`-Fix (2026-09-30) Pages-Auslieferung prüfen.
