# Hub: Entscheidungen, Plattform und offene Punkte

Zentrale Datei für offene Punkte und Entscheidungen. Retrospektiven liegen als eigene Dateien daneben.

Stand: 05.11.2026, 02:34

## Retrospektiven

- [v1.0: Treffpunkt live (Spanne 01:04 bis 04:05)](RETROSPEKTIVE_2026-11-04_v1.0.md)
- [v1.1: Von der App zur Plattform (Spanne 04:05 bis 14:50)](RETROSPEKTIVE_2026-11-04_v1.1.md)

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
| 04.11., 11:15 | Umzug auf privates Repo plus Firebase Hosting (10b), vor der ersten echten Veranstaltung | Codebasen künftig grundsätzlich privat (mögliche Monetarisierung); Firebase Hosting kostenlos und im bestehenden Projekt | GitHub Pro (kostet), öffentliches Repo behalten (10a) |
| 04.11. | „Meine Veranstaltungen“ gerätebezogen | Ohne Konten weiß die App nicht, wer wohin eingeladen ist | Konten |

## Plattform (Stand 04.11.2026, 12:20)

- Ziel: alle Web-Apps öffentlich hosten, visuelle Einstiegsseite, Werbung/Affiliate vorbereitet aber ausgeschaltet, bis etwas Traffic bekommt (14a). Laufende Kosten minimal.
- Entschieden: ein privates Repo als Zentrale (Hub-Datei darin), Subdomain pro App, Cloudflare Web Analytics ohne Cookies ab Tag eins, jede App vor Veröffentlichung auf private Daten prüfen.
- Nächster Schritt: neuer Chat (16a) mit Namensprüfung, Inventur aller Apps (Rechner und Chatverlauf), Plan mit Akzeptanzkriterien und Pre-Mortem.
- Name: Richtung „Werkstatt/Schmiede“ gefällt (Sunforge wäre Favorit, aber Forge-Namen sind stark belegt). Shortlist steht noch aus.
  - 04.11.2026, 14:35: Finale Kandidaten Nightyard und OMGForge geprüft (TMview, Companies House, North Data, Websuche). Nightyard: keine Marke, aber aktive UK-Firma „NIGHT YARD LTD“ (seit 10.05.2026, Software/Webportale/Werbung), NL-Firma „Nightyard“ (Graffiti), GitHub-Projekt „nightyard“ (KI-Coding-IDE), Eventlocation „The Night Yard“ (UK); .com/.app belegt. OMGForge: keine Marke, keine Firma, nur ein Minecraft-Dateiname; .com/.de/.app/.dev frei. Risiko OMGForge: viele ältere Marken „OMG“ und „FORGE“ einzeln (u.a. Object Management Group, Autodesk Forge, Forge of Empires). Keine anwaltliche Prüfung.
- Wohnort für Gewerbe/Impressum: Hamburg.

## Offene Punkte

Nächste Schritte laut Retro v1.1 (04.11.2026, 14:50), in dieser Reihenfolge:

- [ ] P1 Namensentscheid Nightyard / OMGForge (Empfehlung OMGForge), danach Domains .com und .de kaufen (Kauf nur durch dich)
  - 05.11.2026, 02:34: Runde 3 nach Muster Wort plus Zahl (78 Namen geprüft, Bericht in [NAMENSPRUEFUNG.md](NAMENSPRUEFUNG.md)). Dennis' sieben Kandidaten haben alle keine freie .com; nur NightSeven ist sonst sauber. Engere Wahl mit allen vier Domains frei und ohne Marke oder Firma: NoxSeven, DuskSeven, NightEleven, SunTwelve. Empfehlung NoxSeven. .web ist erst ab Mitte Dezember 2026 registrierbar, Inhaber der .com haben danach Vorrang. Entscheidung offen.
- [ ] P2 Plattform-Plan im frischen Chat: Inventur aller Apps, Architektur, Akzeptanzkriterien, Pre-Mortem; erster Schnitt Einstiegsseite plus Treffpunkt
- [ ] Entscheidung offen (04.11.2026, 14:58): Adress-Architektur der Plattform (Subdomains, Pfade oder eigene Domains pro App). Optionen und Empfehlung im Chat vom 04.11., Entscheidung im Plattform-Chat
- [ ] P3 Treffpunkt einmalig auf die endgültige Domain umziehen, direkt danach erste echte Veranstaltung
- [ ] Turret Syndrome als privates GitHub-Repo sichern. 04.11.2026, 14:55 geprüft: lokales Git-Repo `D:\UnityProjects\TurretSyndrome` ohne Remote (kein `[remote]` in `.git/config`, keine `refs/remotes`), Commits 29.05. bis 01.07.2026 liegen nur lokal

Weitere offene Punkte:

- [ ] Umzug: eigenen Seitennamen anlegen, Deploy einrichten, testen, danach Repo auf privat stellen (Reihenfolge wichtig, sonst Ausfall)
  - 04.11.2026, 11:40: Pausiert, bis Domain und Struktur der geplanten App-Plattform (Einstiegsseite für alle Apps) feststehen. Grund: Jeder Adresswechsel trennt Geräte von ihren Einträgen, ein Doppelumzug soll vermieden werden.

- [ ] Testveranstaltungen in Firestore löschen: „Testlauf (Claude)“, „Animationstest (Claude, löschbar)“, „Zusagetest (Claude, löschbar)“ (Löschen nur durch dich)
- [ ] GitHub verlangt Zwei-Faktor-Anmeldung bis 13.12.2026 (Hinweis auf der Pages-Einstellungsseite gesehen), sonst eingeschränkter Zugriff
- [ ] Optional: Organisator kann einzelne Teilnehmer noch nicht entfernen (Regeln erlauben es bereits, Oberfläche fehlt)
- [ ] Optional, Hypothese: API-Schlüssel in der Google Cloud Console auf `brisk-one.github.io` beschränken, als zusätzliche Absicherung gegen Fremdnutzung des Kontingents
