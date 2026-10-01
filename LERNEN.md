# Lektionen aus allen Projekten

Das ist der Teil, der **auch ohne meine Projekte** nützt. Jede Lektion hat einen
Beleg (welches Projekt, welche Zahl) und eine Anwendung („So machst du es").
Kurz: Die meisten guten Ergebnisse waren Messfehler, bis jemand nachgesehen hat.

---

## A. Handeln und Entscheiden

### 1. „Nichts tun" muss ein gültiges Ergebnis sein
**Beleg:** [Apex Capital](projekte/apex-capital.md) hatte vier Wege, die mindestens
einen Trade pro Scan erzwangen, einer davon reichte ein `fake_result` mit
`verdict: INVEST` an den Kauf. **So machst du es:** Ein System darf nie so gebaut
sein, dass es handeln *muss*. `NO TRADE` / `PASS` / `WAIT` ist der Ruhezustand.
Suche in deinem Code nach Pfaden, die ein Ergebnis fabrizieren, wenn die Analyse
nichts findet.

### 2. Der Code besitzt die Zahlen, die KI redet
**Beleg:** [Operation NEMI](projekte/operation-nemi.md), Regel 2. **So machst du es:**
Alles, was Kapital berührt (Positionsgröße, Stop, Limit), rechnet deterministischer,
testbarer Code. Sprachmodelle dürfen zusammenfassen, erklären, widersprechen — nie
eine Zahl festlegen, die Geld bewegt.

### 3. Widerspruch muss eingebaut sein
**Beleg:** Skeptiker, der widersprechen *muss* ([Polymarket Bot](projekte/polymarket-bot.md));
Teufelsanwalt nach dem Urteil ([Apex](projekte/apex-capital.md)); Viktor sagt zuerst nein.
**So machst du es:** Gib Agenten gegensätzliche Aufträge, nicht verschiedene Tonlagen.

---

## B. Messen ohne sich zu belügen

### 4. Look-ahead ist der Standardfehler
**Beleg:** [Fly of Wallstreet](projekte/fly-of-wallstreet.md): Die Kontrolle hatte
Zukunftswissen, Ausführung zum Schlusskurs war nicht erreichbar → alle Vorsprünge aus
v1–v3 verschwanden. [Eye of Horus](projekte/eye-of-horus.md) löst es strukturell.
**So machst du es:**
- Eine Zugriffsschicht, die Zukunftsdaten *verweigert*, statt Disziplin vorauszusetzen.
- Ein Test, der versucht, sie zu umgehen.
- Ausführung zu einem Preis, den du *wirklich* hättest bekommen können.

### 5. Gewinne, die nur in den Auswahldaten leben, sind keine
**Beleg:** NEMI: bestes Setup 0 von 3 Walk-forward-Fenstern; die gesamte Rendite
stammte aus 2020. **So machst du es:** Walk-forward oder echte Out-of-Sample-Daten;
Gewinn **pro Jahr/Regime** aufschlüsseln. Kommt alles aus einem Ereignis, ist es
keine Strategie.

### 6. Nie auswählen *und* bestätigen auf denselben Daten
**Beleg:** Fly-Messregel — Varianten nie auf denselben Seeds wählen und bestätigen.
**So machst du es:** Trenne Auswahl-Daten und Bestätigungs-Daten, frische Seeds für
jede Bestätigung. Zähle, wie viele Varianten du probiert hast (NEMI: 23), und rechne
den Zufall heraus.

### 7. Vergleiche mit dem dümmsten Konkurrenten
**Beleg:** [MT5-Strategie](projekte/mt5-master-strategy.md): 10,02 % p. a. schlägt den
DAX, aber nicht S&P-Buy-and-Hold (10,56 %). Fly: Sharpe 0,44 vs. SPY 0,48.
**So machst du es:** Immer eine naive Basislinie mitlaufen lassen (Eye of Horus macht
sie zur Pflicht). Wer sie nicht schlägt, hat nichts.

### 8. Kosten zuerst
**Beleg:** MT5-EA v6: Profit Factor 0,88, vor Spreads exakt null Edge. Wechsel auf
Tagesbasis senkte den Spread von 6,3 % auf 0,9 % des Risikos. **So machst du es:**
Rechne Kosten und Steuern in den ersten Backtest, nicht in den letzten.

### 9. Kennzeichne Demo-Zahlen bis ins UI
**Beleg:** Eye of Horus: `is_demo: true` Ende-zu-Ende, sichtbares DEMO-Badge.
**So machst du es:** Ein Flag pro Zeile, im UI sichtbar. Sonst hält irgendwann jemand
Spielzeug für echt.

### 10. Lass unabhängige Prüfer nur nach Fehlern suchen
**Beleg:** Zwei Prüf-Agenten kippten bei Fly alle Scheinerfolge. **So machst du es:**
Ein Agent, der baut, prüft nicht selbst. Der Prüfer bekommt den Auftrag „finde, was
falsch ist", nicht „sieh drüber".

### 11. Dokumentiere widerlegte Vermutungen
**Beleg:** Quartals-Rebalancing (kostet statt spart), Abgeltungssteuer (killt den
Vorsprung nicht), mehr Sinne bei Fly (hilft nicht). **So machst du es:** Eine Liste
„nicht erneut probieren" mit Begründung. Spart Wochen.

---

## C. Betrieb und Kosten

### 12. Cron statt Dauerbetrieb
**Beleg:** NEMI auf Railway: ein Cron-Job werktags 22:30 UTC statt eines Servers, der
rund um die Uhr läuft. **So machst du es:** Frage, ob dein Dienst wirklich *laufen*
muss oder nur *ausgeführt* werden muss.

### 13. Wähle die Datenfrequenz nach dem Limit der Quelle
**Beleg:** Kein 1-Minuten-Datenstrom wegen Yahoos 30-Tage-Grenze — bei täglichem Lauf
geht mit 5m/15m/1h nichts verloren. **So machst du es:** Lies die Rückblick-Grenze
deiner Quelle, bevor du das Sammelintervall festlegst.

### 14. Sammle Daten zuerst, handle später
**Beleg:** NEMI deployt nur einen Datensammler. **So machst du es:** Ein billiger
Sammler macht jeden späteren Backtest besser, ohne Risiko.

### 15. Gestaffelte Zeitpläne
**Beleg:** Apex-Kostenoptimierung (Monitor gestaffelt, Abfrage begrenzt). **So machst du
es:** Teures selten, Billiges oft.

### 16. GitHub-Cron ist unzuverlässig — plane damit
**Beleg:** [Fly](projekte/fly-of-wallstreet.md) nutzt zwei Termine, nie zur vollen
Stunde, idempotente Läufe und eine `concurrency`-Gruppe. **So machst du es:** Gleiche
Aufgabe zweimal planen und so schreiben, dass der zweite Lauf nichts ändert.

---

## D. Zusammenarbeit mit KI über Nacht

### 17. Die Nachtsitzung hat kein Gedächtnis
**Beleg:** [Nachtschicht](projekte/nachtschicht.md). **So machst du es:** Eine
Warteschlange in einer Datei im Repo. Jeder Eintrag: Priorität, Ort, **messbares
„Fertig wenn"**. Ohne messbares Ende wird nichts abgehakt.

### 18. Trenne Tester und Bauer
**So machst du es:** Eine Routine testet und meldet, eine zweite baut. Der Tester ändert
keinen Code.

### 19. Sicherheitsleine: eigener Branch
**Beleg:** Arbeit nur auf `claude/nacht`, nie `main`, weil `main` die Live-Seite ist.
**So machst du es:** Doppelt sichern — durch Plattformregeln *und* im Prompt (kein
`main`, kein `--force`, kein Löschen).

### 20. Entscheidungen bleiben beim Menschen
**So machst du es:** Ein Abschnitt „Entscheidung nötig" in der Warteschlange, den die
Routinen nicht anfassen (z. B. Namen, Tonalität, Spielende).

### 21. Prüfe, was die Cloud *nicht* kann
**Beleg:** Kein Browser in der Cloud → `nachttest.js` ohne Pixel. **So machst du es:**
Schreibe die Grenzen hinein und lass die Routine Punkte überspringen, die sie nicht
messen kann.

---

## E. Ordnung

### 22. Fremder Code ist nicht dein Projekt
**Beleg:** [Umfeld](projekte/umfeld.md): `test 1` sah nach Wegwerf-Test aus, war eine
Kopie fremden Codes. **So machst du es:** Klone Fremdes, kopiere es nicht; führe eine
Liste, was Projekt und was Werkzeug ist.

### 23. Eine Wahrheit, Verweise statt Kopien
**Beleg:** Eine eingefrorene Dublette des Polymarket-Projekts im Vault wurde durch eine
Verweis-Notiz ersetzt. **So machst du es:** Ein Ort für den Code, überall sonst ein Link.

### 24. Repos im Vault ausklammern
**Beleg:** Der Obsidian-Vault enthält mehrere Repos und steht selbst unter Git; die
Unterprojekte stehen in der `.gitignore`. **So machst du es:** Sonst sammelt
`git add .` venv und Datenbanken ein.

### 25. Gesundheitscheck für alle Projekte
**So machst du es:** Ein wiederholbarer, rein lesender Scan (Versionierung, ungepushte
Arbeit, Secrets, `.gitignore`), dessen Reparaturen konservativ sind: Additives ohne
Rückfrage, Löschen/Committen/Pushen nur nach Bestätigung.

### 26. Daten, die privat sind, gehören nicht in öffentliche Repos
**Beleg:** [Health Tracker](projekte/health-tracker.md) schreibt Daten in sein eigenes
(öffentliches) Repo. **So machst du es:** Privates Repo oder separate Daten.
