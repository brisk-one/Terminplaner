# Treffpunkt

Terminplaner für den Freundeskreis: Runde anlegen, Link verschicken, jeder tippt seine freien Abende an, der beste Abend wird automatisch ermittelt.

Stand: 04.11.2026, 01:45

Live: https://brisk-one.github.io/Terminplaner/

Entscheidungen und offene Punkte: [HUB.md](HUB.md) · Retrospektiven: [v1.0](RETROSPEKTIVE_2026-11-04_v1.0.md), [v1.1](RETROSPEKTIVE_2026-11-04_v1.1.md), [v1.2](RETROSPEKTIVE_2026-11-05_v1.2.md)

Hinweis 04.11.2026, 14:55: Umzug auf privates Repo plus Firebase Hosting ist entschieden, aber pausiert, bis die Domain der geplanten App-Plattform feststeht (Details im Hub). Bis dahin bleibt die Adresse oben gültig.

## Status

- [x] App gebaut und auf Handy-Breite getestet (Testmodus, drei Teilnehmer)
- [x] GitHub Pages aktiv (Branch `main`, Root)
- [x] Firebase-Projekt `terminplaner-809c6`: anonyme Anmeldung an (ohne automatische Bereinigung), Firestore `europe-west3`, Regeln veröffentlicht, Domain `brisk-one.github.io` freigegeben
- [x] Live-Test 04.11.2026: Runde anlegen, beitreten, Tage speichern, Reload, Live-Sync mit zweiter Identität
- [x] Regeltest live: ohne Anmeldung alles 403; fremde Identität darf Runde lesen und eigenen Eintrag schreiben, aber nicht Runden auflisten, Schlüssel lesen, fremde Einträge ändern, Runde bearbeiten oder Organisator werden
- [x] 04.11.2026, 02:10: Zwei Arten von Runden: „Termin finden“ (Kalender) und „Fester Termin“ (Zusage: Bin dabei / Vielleicht / Nicht dabei mit Kommentar). Nach dem Festlegen startet bei der Terminsuche automatisch die Zusagerunde. Keine Begleitpersonen (+1).
- [x] 04.11.2026, 02:10: Gastgeber-Option nur ohne festen Ort, eigene Farben für Kann/Vielleicht/Nein, kleine Avatare im Kalendertag, Lichterkette mit einer Birne pro Person (in Personenfarbe, ab 16 Personen mehrreihig), Titelschrift Fraunces, Panel-Einblendung nur einmal
- [x] 04.11.2026, 02:15: Eigener Avatar erscheint im Kalendertag, Farbwahl entfernt (Farbe folgt dem Avatar), Name und Avatar über Zahnrad-Knopf änderbar, vergebene Avatare blass und gesperrt, 48 Avatare nur Tiere und Fabelwesen, ausstehende Änderungen werden beim Verlassen der Seite sofort gespeichert
- [x] 04.11.2026, 02:30: Avatare um Gans, Qualle und Fabelwesen erweitert (59), ähnliche Drachen/Dinos umgefärbt, nicht darstellbare Emojis werden pro Gerät ausgeblendet. Neue Übersicht „Meine Veranstaltungen“ (Startseite) mit Live-Infos je Runde: Art, Termin oder bester Abend bisher, Ort, Teilnehmende, eigener Status, Antwortfrist; vergangene Runden separat; Runden lokal aus der Liste entfernbar. In jeder Runde führt „Meine Veranstaltungen“ oben links zurück. Hinweis: Die Liste ist gerätebezogen (Runden, die auf diesem Gerät geöffnet wurden).
- [x] 04.11.2026, 02:35: Leuchtrand repariert (lief vorher wegen ungültiger CSS-Einheit nie), bester Abend zusätzlich mit pulsierendem gelbem Rahmen und Leiste über dem Kalender (Tippen öffnet den Tag), Übersicht heißt „Meine Veranstaltungen“
- [x] 04.11.2026, 02:40: Leuchten dezenter und auf ca. 12 Personen skaliert, Katze und Haken nicht mehr abgeschnitten (Klassen-Kollision behoben), Leiste „Bester Abend“ zeigt Anzahl und wer kann
- [x] 04.11.2026, 02:45: In der App überall „Veranstaltung“ statt „Runde“. Terminsuche ohne „kann nicht“ (Tippen: kann, vielleicht, leer). Vielleicht einfarbig orange statt gestreift. Fester Termin: „Nicht dabei“ rosarot. „Meine Veranstaltungen“-Knopf auch beim Erstellen.
- [x] 04.11.2026, 02:50: Bester Tag: Rahmen liegt direkt am Tag an und pulsiert nur im Leuchten (keine Ausdehnung mehr). Schlafende Katze animiert (atmet, drei z steigen auf), z wird nicht mehr abgeschnitten.
- [x] 04.11.2026, 02:55: Kein mengenabhängiges Leuchten mehr. Nur der beste Abend leuchtet golden (weicher Glow, pulsiert), der zweitbeste hat einen kühlen Schimmer und ✨, auch in der Leiste genannt.
- [x] 04.11.2026, 03:00: Standardzeitraum Terminsuche 3 Wochen, Legenden im Eintragemodus entfernt, zweitbester Abend nur mit kühlem Schimmer (ohne Sternchen)
- [x] 04.11.2026, 03:10: Kein Tagesfenster beim Zurückstellen auf offen. Schnell-Eintragen: Einstellungen eines Tages (Gastgeber, Uhrzeiten, Notiz) als Standard pro Veranstaltung speicherbar, danach trägt ein Tipp direkt ein (abschaltbar, gespeichert pro Gerät). Kopfzeile bleibt beim Scrollen sichtbar.
- [x] 04.11.2026, 03:20: Speicheranzeige (Tasse) entfernt. Katze im Kalender weiter rechts, Ohren sitzen sauber am Kopf. Leiste „Bester Abend“ steht unter dem Kalender.
- [x] 04.11.2026, 03:35: Bester/zweitbester Abend nach Zusagen, dann Vielleicht. Gleichstand: alle gleich guten Abende werden gemeinsam gezeigt (Kalender, Leiste, Auswertung, Übersicht). Umrandung und Katze erst ab 3 Zusagen.
- [x] 04.11.2026, 03:40: Bei gleicher Zahl an Zusagen und Vielleicht gewinnt der Abend mit angebotenem Gastgeber; Gastgeber wird in der Leiste angezeigt.
- [x] 04.11.2026, 03:45: Katze erscheint erst ab 5 Zusagen (Kalender, Leiste, Auswertung); Umrandungen weiterhin ab 3.
- [x] 04.11.2026, 03:50: Katze entwickelt sich mit den Zusagen: ab 7 rosige Bäckchen, ab 9 Partyhütchen, ab 11 Herzchen statt z, ab 13 Schleife, ab 15 Krone und Funkeln (Accessoires sammeln sich an).
- [x] 04.11.2026, 03:55: Katzenstufen neu: ab 7 Herzchen statt z, ab 9 Partyhütchen, ab 11 schläft ein rotgetigertes Kätzchen auf ihrem Rücken, ab 13 Krone und Funkeln.
- [x] 04.11.2026, 03:50: Katzenstufen final: ab 5 schläft, ab 7 Herzchen, ab 9 Kätzchen auf dem Rücken, ab 11 Partyhütchen, ab 13 zusätzlich Sternchen und kleine Diskokugel (keine Krone).
- [x] 04.11.2026, 03:55: Katzenstufe ab 15: Katze wacht auf (fröhliche Augen, Lächeln), Herzchen und zusätzlich Musiknoten, bunte Disko-Lichtpunkte, wippt im Takt.
- [x] 04.11.2026, 04:00: Leiste „Bester Abend“ kompakt (Datum in einer Zeile, „1 Person“ / „4 Personen“).
- [ ] Erste echte Veranstaltung mit Freunden

Hinweis: In der Datenbank liegen Test-Runden „Testlauf (Claude)“, „Animationstest (Claude, löschbar)“ und „Zusagetest (Claude, löschbar)“. Nur per Link erreichbar, kann in der Firebase Console unter Firestore gelöscht werden.

## Dateien

| Datei | Zweck |
|---|---|
| `index.html` | Die komplette App |
| `firebase-config.js` | Verbindung zur Datenbank (einmalig ausfüllen) |
| `firestore.rules` | Zugriffsregeln, kommen in die Firebase Console |

## Einrichtung Firebase (einmalig, ca. 10 Minuten)

1. **Projekt anlegen:** [console.firebase.google.com](https://console.firebase.google.com) öffnen, "Projekt hinzufügen", Name z.B. `terminplaner`. Google Analytics kann aus bleiben.
2. **Anonyme Anmeldung aktivieren:** Linkes Menü "Authentication", "Jetzt starten", Reiter "Sign-in method", Anbieter "Anonym" aktivieren, speichern.
   Damit bekommt jedes Gerät still eine Kennung. So darf jeder nur seine eigenen Einträge ändern, ohne Passwort.
3. **Datenbank anlegen:** Linkes Menü "Firestore Database", "Datenbank erstellen", Standort `europe-west3 (Frankfurt)`, im **Produktionsmodus** starten.
4. **Regeln eintragen:** In Firestore den Reiter "Regeln" öffnen, den Inhalt komplett durch `firestore.rules` ersetzen, "Veröffentlichen".
5. **Web-App registrieren:** Zahnrad oben links, "Projekteinstellungen", unten bei "Meine Apps" das Symbol `</>` wählen, Name `terminplaner`, Hosting nicht ankreuzen. Die angezeigten Werte (`apiKey`, `authDomain`, `projectId`, ...) in `firebase-config.js` eintragen.
6. **Domain freigeben:** "Authentication", Reiter "Einstellungen", "Autorisierte Domains", `brisk-one.github.io` hinzufügen.

Die Werte in `firebase-config.js` sind nicht geheim, sie stehen ohnehin im Browser. Geschützt wird alles über die Regeln aus Schritt 4.

## GitHub Pages

Repo: [brisk-one/Terminplaner](https://github.com/brisk-one/Terminplaner). Einschalten: "Settings", "Pages", Source "Deploy from a branch", Branch `main`, Ordner `/ (root)`. Nach ca. 1 Minute erreichbar unter `https://brisk-one.github.io/Terminplaner/`.

## Wie der Zugriff geschützt ist

- Jede Runde hat eine zufällige ID mit 20 Zeichen im Link. Raten ist praktisch ausgeschlossen.
- Die Regeln verbieten das Auflisten aller Runden. Ohne Link kommt niemand an eine Runde.
- Jeder Teilnehmer kann nur seinen eigenen Eintrag schreiben (gebunden an sein Gerät).
- Der Organisator-Link enthält einen zweiten geheimen Schlüssel. Wer ihn öffnet, darf die Runde bearbeiten und den Termin festlegen.
- Die Seite ist für Suchmaschinen gesperrt (`noindex`).

Grenze: Wer den Link hat, kann mitmachen. Wird er weitergeleitet, kommen auch Dritte rein.

## Bekannte Einschränkungen

- Die Identität hängt am Gerät und Browser. Wer auf Handy und Laptop abstimmt, erscheint zweimal. Einfach ein Gerät nutzen.
- Wer die Browserdaten löscht, kann seinen alten Eintrag nicht mehr ändern. Der Organisator kann neu anfangen lassen (Eintrag bleibt aber stehen, Löschen ist in der Oberfläche noch nicht eingebaut).

## Testmodus

`index.html?demo=1` läuft ohne Firebase, alle Daten bleiben im Browser. Nur zum Ausprobieren.

## Kosten

Firebase-Gratistarif (Spark). Für einen Freundeskreis reichen die Tageslimits um Größenordnungen.
