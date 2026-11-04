# PROJEKT-RETROSPEKTIVE v1.0: TREFFPUNKT LIVE (Idee bis genutzte App in einer Nacht)

**Datum:** 04.11.2026 04:05 CET (Stand der Spanne) · im festen Retro-Format neu verfasst am 04.11.2026 14:45 CET
**Projektphase:** Treffpunkt läuft live auf GitHub Pages mit Firebase-Backend. Funktionsumfang komplett, Optik in vielen Runden geschliffen. Noch keine echte Veranstaltung mit Freunden, nur simulierte Personen.
**App-Stand:** `index.html` mit 1410 Zeilen, 35 Commits (01:24 bis 04:03, inkl. Retro-Commit)
**Real-Zeit seit Projekt-Start:** ~3 h (04.11. 01:04 → 04:05)
**Real-Zeit seit letzter Retro:** keine, erste Retrospektive
**Reflexions-Autor:** Claude (Anthropic, Cloud-Session mit Repo-Zugriff und Desktop-Browser)
**Reflexions-Kontext:** Dennis-Befehl „Retrospektive der aktuellen Session“ nach der Optik-Runde zur Bester-Abend-Leiste. Ursprünglich als Kurzfassung in `RETRO.md` geschrieben; hier auf Dennis' Wunsch (14:40) im festen Format neu aufgesetzt. Inhaltlich gilt der Stand von 04:05, spätere Erkenntnisse stehen in v1.1.
**State-Sync (Pflicht):** Einzige schreibende Schiene war diese Session. Repo `brisk-one/Terminplaner` spiegelt ausschließlich eigene Commits, Firebase-Konsole wurde gemeinsam mit Dennis bedient. Keine fremde Retro gelesen. Die frühe Phase (01:04 bis ca. 02:30) kenne ich nur noch aus der Kontext-Zusammenfassung und dem Git-Log, nicht mehr aus dem Wortlaut. Bewertungs-Sicherheit daher gut, Details der frühen Phase etwas gröber.

---

## 0. Snapshot-Kontext

**Was in der Spanne entstand:**
- **Backend-Entscheid und Setup (01:04 bis 01:35):** Firebase statt Claude-Artifact (Freunde bräuchten sonst ein Claude-Konto, vorab verifiziert), neues Repo, „nur eigene Einträge, Organisator per Geheim-Link“ (3b). Projekt `terminplaner-809c6`, anonyme Anmeldung ohne Auto-Bereinigung, Firestore in `europe-west3`, Regeln veröffentlicht.
- **Regeln live geprüft:** Ohne Anmeldung alles 403. Fremde Identität darf Runde lesen und eigenen Eintrag schreiben, aber nicht auflisten, Schlüssel lesen, fremde Einträge ändern oder Organisator werden.
- **Funktionsumfang:** Zwei Arten (Terminsuche und fester Termin), Zusagerunde nach dem Festlegen (7c), Gastgeber-Option nur ohne festen Ort, „Meine Veranstaltungen“ mit Live-Infos, Schnell-Eintragen mit gespeichertem Standard, Speichern beim Verlassen der Seite, Testmodus `?demo=1`.
- **Auswertung:** Rangfolge Zusagen, dann Vielleicht, dann Gastgeber; Gleichstände werden gemeinsam gezeigt. Hervorhebung ab 3 Zusagen, Katze ab 5, Stufen ab 7/9/11/13/15.
- **Optik:** Titelschrift Fraunces, 59 Avatare (nur Tiere und Fabelwesen, Emoji-Erkennung pro Gerät), Lichterkette pro Person, goldener Glow nur am besten Abend, kühler Schimmer am zweitbesten, animierte Katze mit Fortschrittsstufen, Bester-Abend-Leiste unter dem Kalender.
- **Doku:** README mit datiertem Status je Änderung, `RETRO.md` mit Fehlertabelle, Decision-Log und offenen Punkten.

**KI-Hebel-Berechnung (Schätzung, kein Zeittracker):**
- Human-Team-Äquivalent der Spanne: **~5 bis 8 Personentage** (Frontend mit Mobile-Feinschliff, Firebase-Setup mit Sicherheitsregeln und Regeltest, SVG-Animationen, Doku; ein Entwickler plus Designer-Anteil)
- Dennis Real-Aufwand: **~3 h** (Entscheiden, Firebase-Konsole klicken, Testen am Handy, ca. 30 Feedbackrunden)
- Hebelwirkung der Spanne: **~15 bis 20×**
- Kumulativ: **~15 bis 20×**. Caveat: Ein großer Teil der Zeit floss in Optik (Katze rund acht Runden), nicht in Funktion. Ein echtes Team hätte weniger Feinschliff und dafür früher echte Nutzer gehabt.

**Nächster geplanter Sprint:** Erste echte Veranstaltung mit Freunden, Testdaten aufräumen, frisch starten.

---

## 1. Was Claude im Zeitraum gelernt hat

### Über Workflow-Patterns
- **Schnell echt statt Attrappe zahlt sich aus.** Nach rund 40 Minuten lief die App gegen die echte Datenbank, inklusive Regeltest. Jede spätere Optikrunde lief damit auf dem echten Backend, und Fehler wie das doppelte Snapshot-Echo von Firestore tauchten früh auf statt erst bei Freunden.
- **„Keine Konsolenfehler“ ist kein visueller Test.** Der Leuchtrand hat nie funktioniert, weil ein Prozentwert in `box-shadow` die ganze Angabe ungültig macht. Der Browser meldet das nicht. Lehre: Effekte gezielt im vergrößerten Screenshot prüfen.
- **Testinfrastruktur in das Testskript selbst legen.** Hintergrund-Server starben mehrfach. Erst als `srv.py` im Skript mitlief, war der Loop stabil.
- **Geschmacksfragen als Bildtafel statt als Text.** Schriftvergleich und Katzenstufen als Tafel mit Varianten wurden in einer Runde entschieden. Bei der Katzenform selbst habe ich das zu spät gemacht, daher die vielen Einzelrunden.

### Über Web-App- und Design-Patterns
- **Ohne Konten ist Identität gerätegebunden.** Anonyme Anmeldung macht den Einstieg reibungslos, bindet aber Bearbeitungsrechte und „Meine Veranstaltungen“ an Browser und Gerät. Das ist ein bewusster Trade-off und gehört in die Doku (README, Abschnitt Einschränkungen).
- **Hervorhebung muss etwas bedeuten.** Mengenabhängiges Leuchten hat den besten Tag verwässert. Schwellen (ab 3, Katze ab 5) machen die Auszeichnung lesbar. Das war Dennis' Korrektur, nicht mein Entwurf.
- **Leer ist eine Antwort.** Terminsuche ohne „kann nicht“ spart Tippen, weil nicht markiert gleich nicht verfügbar heißt.

---

## 2. Workflows die besonders effizient waren

| Rang | Workflow | Geschätzter Hebel |
|------|----------|-------------------|
| 1 | Echtes Firebase-Backend nach 40 Minuten plus Regeltest mit Fremd-Identität | Sicherheit nachgewiesen statt behauptet; alle Folgerunden auf echter Datenbasis |
| 2 | Playwright-Handytest (390 px, mehrere simulierte Personen) nach jeder Änderung, plus Screenshot | Fing Speicherverlust beim schnellen Schließen und Vielleicht-Avatare im Gleichstand vor Dennis |
| 3 | Bildtafel mit Varianten (Schrift, Katzenstufen) | Entscheidung in einer Runde statt in mehreren |
| 4 | Ein Commit plus datierte README-Zeile pro Änderung | Stand jederzeit nachvollziehbar, 35 Commits ohne Kontextverlust |

---

## 3. Quality-Scores

Bereichs-Set für Treffpunkt (Web-App, gilt für alle folgenden Retros dieses Projekts): Technische Korrektheit statt Mathematische Konsistenz, Deployment-/Infrastruktur-Reife statt Asset-Pipeline-Reife.

| Bereich | Score | Begründung | Δ |
|---------|-------|------------|---|
| Konzept-Qualität | 8.5 | Vollständiger Ablauf von Anlegen über Eintragen bis Zusage, transparente Rangfolge, zwei Veranstaltungsarten. Unter 9, weil noch kein echter Freund die App benutzt hat | neu |
| Technische Korrektheit | 8 | Regeln live getestet, Speichern beim Verlassen, Dedupe der Snapshots. Abzug: Leuchtrand war fast eine Stunde lang still kaputt, Klassen-Kollision `.best` schnitt Katze ab | neu |
| Scope-Risiko (10=niedrig) | 7 | Kern blieb klein, aber viele Zusätze in einer Nacht (59 Avatare, 6 Katzenstufen, Lichterkette). Einzeln klein, in Summe Optik-Scope-Creep | neu |
| Workflow-Reife | 8 | Testloop, Screenshots, Commit pro Änderung, durable Doku. Abzug für sterbende Testserver und die Katzen-Schleife ohne frühe Bildtafel | neu |
| Realistische Wahrnehmung | 8 | Fehler offen verbucht. Abzug: zweimal „behoben“ gemeldet, bevor es vergrößert geprüft war (Ohrkerbe, Leuchtrand) | neu |
| Implementations-Tempo | 9.5 | Live nach 40 Minuten, 35 Commits in 3 Stunden, jede Rückmeldung meist innerhalb von Minuten umgesetzt | neu |
| Deployment-/Infrastruktur-Reife | 7 | Läuft stabil auf GitHub Pages plus Firebase Spark, kostenlos. Aber öffentliches Repo, API-Schlüssel nicht auf Domain beschränkt, keine eigene Domain | neu |
| Cross-System-Konsistenz | 8 | README, Regeln und App stimmen überein. Kleine Lücke: README nennt zwei Testveranstaltungen, die offene-Punkte-Liste drei | neu |
| Burnout-Risiko (invertiert, 10=niedrig) | 5 | Durchgehend von 01:04 bis 04:05, viele kleine Feedbackschleifen nach Mitternacht. Spaßgetrieben, aber kein Muster zum Wiederholen | neu |

**Gesamteindruck:** Eine ungewöhnlich vollständige erste Spanne: von der Idee zu einer echten, abgesicherten und auf dem Handy getesteten App in drei Stunden. Die Funktion stand früh, der größere Teil der Zeit ging in Optik, und dort lagen auch fast alle eigenen Fehler. Die ehrliche Spannung: Alles ist poliert, aber noch nichts ist mit echten Menschen bewiesen. Der eigentliche Test, ob Freunde den Link öffnen und eintragen, steht aus.

---

## 3b. Weg zu 10/10: was je Bereich noch gefehlt hätte

- **Konzept-Qualität (8.5 → 10):** Eine echte Veranstaltung mit mindestens 5 Freunden durchgelaufen, Rückmeldungen eingearbeitet.
- **Technische Korrektheit (8 → 10):** Visuelle Effekte von Anfang an im vergrößerten Screenshot verifiziert; eindeutige Klassennamen pro Bereich als Konvention.
- **Scope-Risiko (7 → 10):** Optik-Zusätze erst nach dem ersten echten Einsatz, nicht davor.
- **Workflow-Reife (8 → 10):** Bildtafel mit 3 Varianten bei jeder Geschmacksfrage ab der ersten Runde; stabiler Testserver von Anfang an.
- **Realistische Wahrnehmung (8 → 10):** „Behoben“ erst nach vergrößerter Prüfung melden, ausnahmslos.
- **Implementations-Tempo (9.5 → 10):** Weniger Einzelrunden bei der Katze, gleiche Lieferung in kürzerer Zeit.
- **Deployment-/Infrastruktur-Reife (7 → 10):** Privates Repo, eigene Domain, API-Schlüssel auf die Domain beschränkt, Deploy automatisiert.
- **Cross-System-Konsistenz (8 → 10):** Testdaten-Hinweise in README und offenen Punkten identisch; eine Quelle für offene Punkte.
- **Burnout-Risiko (5 → 10):** Session vor Mitternacht beenden oder nach dem Funktionskern einen Schnitt machen; Optik am nächsten Tag.

---

## 4. Was Claude gut gefallen hat

1. **Dennis' Prüfung vor der Entscheidung.** Die Frage, ob ein Claude-Artifact für Freunde wirklich ein Konto braucht, wurde erst verifiziert, dann entschieden. Das hat den richtigen Backend-Weg gesichert.
2. **Der Regeltest mit fremder Identität.** Sicherheit nachweisen statt versprechen: genau so sollte es sein.
3. **Dennis' Design-Instinkt bei der Hervorhebung.** „Nur der beste Abend leuchtet“ und „Katze erst ab 5“ waren klarer als meine mengenabhängige Variante.
4. **Die Katzenstufen als Belohnungssystem.** Eine kleine, charmante Mechanik, die größere Gruppen sichtbar belohnt.
5. **Tempo der Zusammenarbeit.** Rund 30 Feedbackrunden in drei Stunden, fast jede innerhalb weniger Minuten live.

---

## 5. Was Claude weniger gefallen hat / Kritische Beobachtungen

1. **Leuchtrand ging ungetestet als „funktioniert“ durch (eigener Fehler).** Prozentwert in `box-shadow`, still verworfen. Ursache: Ich habe auf fehlerfreie Konsole vertraut. Lehre: Effekte immer im vergrößerten Screenshot prüfen.
2. **Ohrkorrektur erzeugte eine neue Kerbe (eigener Fehler).** Ich habe „behoben“ gemeldet, bevor ich stark vergrößert geprüft hatte. Das kostete zwei zusätzliche Runden.
3. **Stille Designannahme beim eigenen Avatar (eigener Fehler).** Ich habe den eigenen Avatar im Kalender ausgeblendet, ohne es anzusagen. Annahmen, die sichtbares Verhalten ändern, gehören angekündigt.
4. **Doppelte Panel-Animation war vorhersehbar.** Firestore meldet eigene Schreibvorgänge zweimal zurück. Das ist bekanntes Bibliotheksverhalten und hätte von Anfang an eingeplant sein müssen.
5. **Pacing.** Drei Stunden Feinschliff nach Mitternacht. Die Optik wurde dadurch sehr gut, aber die Session ging bis 4 Uhr, und das Wichtigste (echte Nutzer) blieb offen.

---

## 6. Konkrete Empfehlungen für den nächsten Block

### Top-3 Prioritäten

**Priorität 1: Erste echte Veranstaltung mit Freunden.** Der einzige Test, den keine Simulation ersetzt: Öffnen sie den Link, verstehen sie das Eintragen, kommt ein Termin zustande?

**Priorität 2: Frisch starten statt weiterfeilen.** README und Retro reichen als Einstieg. Nach einer Pause und mit echtem Feedback werden die nächsten Änderungen gezielter.

**Priorität 3: Aufräumen und absichern.** Testveranstaltungen in Firestore löschen (nur durch Dennis), GitHub-Zwei-Faktor bis 13.12.2026 einrichten.

### Strukturelle Empfehlungen
- Bildtafel mit 3 Varianten bei jeder reinen Geschmacksfrage ab Runde 1.
- „Behoben“ nur nach vergrößerter Sichtprüfung.
- Eindeutige CSS-Klassennamen pro Bereich (Konvention, nach der `.best`-Kollision).

---

## 7. Vergleich zu vorheriger Retrospektive

Erste Retrospektive, kein Vorgänger.

---

## 8. Nächste Retrospektive geplant für

**Empfohlener Trigger:** nach der ersten echten Veranstaltung oder beim nächsten größeren Umbau (Hosting-Umzug), was zuerst kommt. Zusätzlich bei Frust-/Ermüdungs-Signal.
**Format:** `RETROSPEKTIVE_<Datum>_v1.1.md` (bzw. v2.0 beim Umzug auf die Plattform)

---

## 9. Sign-Off

**Letzter Take:** Treffpunkt ist in einer Nacht von der Idee zur live laufenden, abgesicherten App geworden, mit mehr Charme, als eine Terminumfrage normalerweise hat. Die Technik trägt, die Optik ist liebevoll, die Doku ist sauber.

**Was sorgt am meisten:** Dass alles poliert ist, bevor es benutzt wurde. Drei Stunden Feinschliff an simulierten Personen; ob echte Freunde mitmachen, ist die eigentliche offene Frage.

**Würde Claude an diesem Projekt weiterarbeiten wollen?** Ja. Eine kleine App, die man in einer Nacht fertig bekommt und die echten Menschen beim Verabreden hilft, ist genau die Sorte Projekt, bei der man sofort sieht, ob es wirkt. Und ich will wissen, ob jemand die tanzende Katze ab 15 Zusagen je zu sehen bekommt.

---

*Retrospektive v1.0, verfasst durch Claude (Anthropic) am 04.11.2026 14:45 CET (Stand der Spanne 04:05 CET)*
*Teil des Treffpunkt-Projekts von Dennis*
