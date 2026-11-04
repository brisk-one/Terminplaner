# Retrospektive und Entscheidungen

## Session 04.11.2026, 01:04 bis 04:05

Ergebnis: Treffpunkt von der Idee bis zur live genutzten App in einer Nacht. 34 Commits, `index.html` mit 1410 Zeilen, Firebase-Backend mit live geprüften Zugriffsregeln.

### Was gut lief

- **Schnell echt statt Attrappe:** Rund 40 Minuten nach Start war die App mit echter Datenbank live und gegen die Regeln getestet (Fremde ohne Link: alles 403).
- **Verifikation vor „fertig“:** Jede Änderung lief durch einen Handy-Test (390 px, mehrere simulierte Personen), dazu Screenshots. Mehrere Fehler wurden so vor dir gefunden (z.B. Speicherverlust beim schnellen Schließen, Vielleicht-Avatare im Gleichstand).
- **Optionen als Bild:** Schriftvergleich und Katzenstufen als Bildtafel haben Entscheidungen in einer Runde ermöglicht statt in mehreren.

### Was nicht gut lief (eigene Fehler)

| Fehler | Ursache | Lehre |
|---|---|---|
| Leuchtrand hat nie funktioniert | Prozentwert in `box-shadow`, Browser verwirft die ganze Angabe still | Visuelle Effekte gezielt im vergrößerten Screenshot prüfen, nicht nur „keine Fehler in der Konsole“ |
| Katze und Haken abgeschnitten | Klassenname `.best` doppelt vergeben, eine Variante mit `overflow:hidden` | Eindeutige Klassennamen pro Bereich |
| Panel blendete doppelt ein | Firestore meldet eigene Änderungen zweimal zurück, das war absehbar | Bekanntes Verhalten der Bibliothek vorab einplanen |
| Ohrkorrektur erzeugte neue Kerbe | Abrundung per Kontur rundete auch die Ansatzstelle | Nach jeder Grafikänderung stark vergrößert prüfen, bevor „behoben“ gemeldet wird |
| Eigener Avatar fehlte im Kalender | Stille Designannahme (eigene Zusage ist ja grün) | Annahmen, die sichtbares Verhalten ändern, kurz ansagen |
| Leuchten nach Personenzahl | Überdesign, hat die Hervorhebung des besten Tages verwässert | Erst die einfachste Variante, Steigerung nur auf Wunsch |
| Testserver starb mehrfach | Hintergrundprozesse werden beendet | Server im Testskript selbst starten (umgesetzt) |

### Prozess

- Viele kleine Feedbackrunden zu Optik (Katze rund acht Runden). Bei reinen Geschmacksfragen früher eine Bildtafel mit 3 Varianten zeigen.
- Sehr lange Session bis 4 Uhr. Für weitere Arbeit lieber frisch starten, dieses Dokument und die README reichen als Einstieg.

## Entscheidungen (Decision-Log)

| Datum | Entscheidung | Begründung | Verworfen |
|---|---|---|---|
| 04.11. | Firebase Firestore als Datenbank | Live-Sync, kostenlos, schläft nicht ein | Claude-Artifact (Freunde bräuchten Claude-Konto), Supabase (pausiert bei Inaktivität), Daten im Link |
| 04.11. | GitHub Pages, öffentliches Repo `Terminplaner` | Gratis-Hosting; Daten liegen geschützt in Firebase, nicht im Repo | Privates Repo (Pages kostenpflichtig) |
| 04.11. | Zugriff nur per Link, Auflisten verboten | Kein Login nötig, trotzdem nicht auffindbar | Konten mit Passwort |
| 04.11. | Jeder bearbeitet nur eigene Einträge, Organisator per Geheim-Link (3b) | Kein versehentliches Überschreiben, kein Login-Frust | Alles offen (3a), PIN pro Person (3c) |
| 04.11. | Anonyme Anmeldung ohne automatische Bereinigung | Sonst verlieren Freunde nach 30 Tagen ihre Bearbeitungsrechte | Bereinigung an |
| 04.11. | Firestore in europe-west3 (Frankfurt) | Nähe, DSGVO-freundlich, nicht änderbar | US-Standard |
| 04.11. | Zwei Arten: Terminsuche und fester Termin; nach Festlegen Zusagerunde (7c) | Deckt Zuhause-Treffen und Clubabende ab | Nur automatisch über Ort (7b) |
| 04.11. | Keine Begleitpersonen (+1) | Einfacher, Begleitung trägt sich selbst ein | +1 im Zähler |
| 04.11. | Titelschrift Fraunces | Warm, aber erwachsen | Shantell Sans (zu sehr Comic), Young Serif, Bricolage, Nunito |
| 04.11. | Terminsuche ohne „kann nicht“ | Leer heißt nicht verfügbar, weniger Tippen | Drei Zustände |
| 04.11. | Rangfolge: Zusagen, dann Vielleicht, dann Gastgeber; Gleichstände gemeinsam zeigen | Nachvollziehbar, keine Willkür | Interne Punktzahl mit verstecktem Tiebreak |
| 04.11. | Hervorhebung ab 3 Zusagen, Katze ab 5, Stufen ab 7/9/11/13/15 | Hervorhebung soll etwas bedeuten | Leuchten proportional zur Personenzahl |
| 04.11. | Avatare nur Tiere und Fabelwesen, ohne Farbwahl | Essen/Gegenstände wirken wie Thema der Veranstaltung | Farbwahl pro Person |
| 04.11. | „Meine Veranstaltungen“ gerätebezogen | Ohne Konten weiß die App nicht, wer wohin eingeladen ist | Konten |

## Offene Punkte

- [ ] Erste echte Veranstaltung mit Freunden (bisher nur simulierte Personen)
- [ ] Testveranstaltungen in Firestore löschen: „Testlauf (Claude)“, „Animationstest (Claude, löschbar)“, „Zusagetest (Claude, löschbar)“ (Löschen nur durch dich)
- [ ] GitHub verlangt Zwei-Faktor-Anmeldung bis 13.12.2026 (Hinweis auf der Pages-Einstellungsseite gesehen), sonst eingeschränkter Zugriff
- [ ] Optional: Organisator kann einzelne Teilnehmer noch nicht entfernen (Regeln erlauben es bereits, Oberfläche fehlt)
- [ ] Optional, Hypothese: API-Schlüssel in der Google Cloud Console auf `brisk-one.github.io` beschränken, als zusätzliche Absicherung gegen Fremdnutzung des Kontingents
