# Hub: Entscheidungen, Plattform und offene Punkte

Zentrale Datei für offene Punkte und Entscheidungen. Retrospektiven liegen als eigene Dateien daneben.

Stand: 06.11.2026, 13:24

## Retrospektiven

- [v1.0: Treffpunkt live (Spanne 01:04 bis 04:05)](RETROSPEKTIVE_2026-11-04_v1.0.md)
- [v1.1: Von der App zur Plattform (Spanne 04:05 bis 14:50)](RETROSPEKTIVE_2026-11-04_v1.1.md)
- [v1.2: Der Name, Nine Embers / 9MBRS (Spanne 04.11. 14:50 bis 05.11. 04:36)](RETROSPEKTIVE_2026-11-05_v1.2.md)

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
| 05.11., 04:18 | Plattform-Name **Nine Embers**, Kurzform **9MBRS** (Dennis); beide Namen als Domains sichern. **Status ab 05.11.2026, 14:06: vorläufig**, bis das Markenrisiko durch „EMBERS“ (Microsoft u. a.) geklärt ist; Dennis gibt das Tempo vor, kein Zeitdruck. **Ersetzt durch Eintrag 05.11., 16:49** | Gefiel Dennis von Anfang an; Kurzform löst die Länge als Subdomain-Suffix. Als einziges geprüftes Paar sind Kurz- und Langform auf .com, .de, .app und .dev frei, ohne Firma, Marke „Nine Embers“ ohne Treffer (Runde 4). Markenprüfung für 9MBRS noch offen (TMview gesperrt). Details [NAMENSPRUEFUNG.md](NAMENSPRUEFUNG.md) | OMGForge (Bestandteile OMG und FORGE stark belegt), Nightyard (aktive UK-Firma im selben Feld), NightSeven und Night7 (.com vergeben bzw. 3.999 US-Dollar), OwlSeven und NoxSeven (Dennis bevorzugt Nine Embers), 9FRG/Nine Forge (nineforge.com vergeben), erfundene Fantasy-Namen (Schreibweise beim Hören unklar), 2 bis 3 Zeichen (alle Domains vergeben) |
| 05.11., 16:49 | Plattform-Name **9MBRS**, mit Dennis' Logo-Entwurf (neun glühende Rauten im Ring); Langform „Nine Embers“ wird öffentlich nicht ausgeschrieben (Dennis' Frage 16:41, als Arbeitsannahme verbucht). Markenrisiko bewusst akzeptiert; Neubewertung, sobald monetarisiert oder eine Marke angemeldet wird; bei einer Beanstandung, etwa durch Amazon, Namenswechsel | Hobby ohne Monetarisierung, freie gute Namen sind kaum noch zu finden. 9MBRS ist auf .com, .de, .app und .dev frei, keine Marke und keine Firma 9MBRS; im Zeichen weit weg von EMBER. Restrisiko: Logo stellt begrifflich den Bezug zu „Embers“ her (Amazon EMBER, EU, eingetragen 10.10.2026), Schriftbild nahe „Nmbrs“ (EU, Lohnsoftware). Details [NAMENSPRUEFUNG.md](NAMENSPRUEFUNG.md) | „Nine Embers“ ausgeschrieben (direkte Nähe zu Amazon EMBER und Microsoft EMBERS), Weitersuchen (kaum freie Namen), Markenanmeldung jetzt (macht sichtbar, verfrüht ohne Monetarisierung) |

## Plattform (Stand 04.11.2026, 12:20)

- Ziel: alle Web-Apps öffentlich hosten, visuelle Einstiegsseite, Werbung/Affiliate vorbereitet aber ausgeschaltet, bis etwas Traffic bekommt (14a). Laufende Kosten minimal.
- Entschieden: ein privates Repo als Zentrale (Hub-Datei darin), Subdomain pro App, Cloudflare Web Analytics ohne Cookies ab Tag eins, jede App vor Veröffentlichung auf private Daten prüfen.
- Nächster Schritt: neuer Chat (16a) mit Namensprüfung, Inventur aller Apps (Rechner und Chatverlauf), Plan mit Akzeptanzkriterien und Pre-Mortem.
- Name: Richtung „Werkstatt/Schmiede“ gefällt (Sunforge wäre Favorit, aber Forge-Namen sind stark belegt). Shortlist steht noch aus.
  - 05.11.2026, 16:49: Revidiert: Name **9MBRS** mit Logo, Langform „Nine Embers“ öffentlich nicht ausgeschrieben; Domains 9mbrs.com und 9mbrs.de seit 05.11.2026 registriert (siehe Entscheidungen).
  - 05.11.2026, 04:18: Entschieden (überholt): **Nine Embers**, Kurzform **9MBRS** (siehe Entscheidungen).
  - 04.11.2026, 14:35: Finale Kandidaten Nightyard und OMGForge geprüft (TMview, Companies House, North Data, Websuche). Nightyard: keine Marke, aber aktive UK-Firma „NIGHT YARD LTD“ (seit 10.05.2026, Software/Webportale/Werbung), NL-Firma „Nightyard“ (Graffiti), GitHub-Projekt „nightyard“ (KI-Coding-IDE), Eventlocation „The Night Yard“ (UK); .com/.app belegt. OMGForge: keine Marke, keine Firma, nur ein Minecraft-Dateiname; .com/.de/.app/.dev frei. Risiko OMGForge: viele ältere Marken „OMG“ und „FORGE“ einzeln (u.a. Object Management Group, Autodesk Forge, Forge of Empires). Keine anwaltliche Prüfung.
- Wohnort für Gewerbe/Impressum: Hamburg.

## Offene Punkte

Nächste Schritte laut Retro v1.2 (05.11.2026, 04:36), in dieser Reihenfolge (vorher laut v1.1):

- [x] P1 Domains für 9MBRS kaufen. Erledigt 06.11.2026, 13:18 geprüft (RDAP): **9mbrs.com** bei INWX, registriert 05.11.2026 21:55 CET, läuft bis 05.11.2027, Transfersperre aktiv, Nameserver INWX; **9mbrs.de** aktiv seit 05.11.2026 23:02 CET, Nameserver INWX. Inhaberdaten sind öffentlich nicht sichtbar, im INWX-Konto prüfen, dass Dennis Inhaber ist. Ursprünglich: 9mbrs.com, 9mbrs.de; optional .app und .dev. Keine nineembers-Domains (Dennis, 05.11.2026, 17:21). Registrar-Empfehlung (17:36): INWX für alles in einem Konto (.com, .de, .app, .dev; deutscher Anbieter, .de sehr günstig, .com ca. 13,50 $ im ersten Jahr und 18,50 $ Verlängerung laut domainoffer.net); Alternative Cloudflare für .com zum Selbstkostenpreis, kann aber kein .de. Kontoschutz mit Zwei-Faktor, automatische Verlängerung an, keine Zusatzpakete. Vorher beim Registrar prüfen, dass kein Premium-Preis gilt. Danach: .web-Vorrangphase für .com-Inhaber (ab Mitte Januar 2027) nutzen.
- [ ] Domain-Nachsorge (Dennis, bei INWX): automatische Verlängerung für beide Domains an, Zwei-Faktor-Anmeldung im Konto an, Inhaber prüfen
- [ ] .web: ab Mitte Januar 2027 Vorrangphase für Inhaber der .com nutzen und 9mbrs.web registrieren (bei INWX nachsehen, sobald angeboten)
- [ ] DNS für 9mbrs.com/.de erst im Plattform-Plan einrichten (Firebase Hosting, Subdomains), bis dahin ruhen lassen
- [ ] Projekt-Anweisungen des claude.ai-Projekts „9MBRS“ anpassen, sobald die Plattform ein eigenes Repo hat (Text vom 06.11.2026 nennt noch brisk-one/Terminplaner)
- [x] P1 Markenrisiko „EMBERS“ für Nine Embers / 9MBRS klären (05.11.2026, 16:49: Dennis entscheidet sich für 9MBRS mit Logo und akzeptiert das Restrisiko, siehe Entscheidungen)
  - Ursprünglicher Wortlaut des erledigten Punkts: Markenrisiko „EMBERS“ für Nine Embers / 9MBRS klären, bevor der Name endgültig ist (Dennis, 05.11.2026, 14:06: Der Name ist auch Markenname, das muss bis ins Detail geprüft sein; kein Zeitdruck). Stand und Fakten in [NAMENSPRUEFUNG.md](NAMENSPRUEFUNG.md), Abschnitt „Markenrisiko EMBERS“.
  - 05.11.2026, 16:28: Microsoft vermutlich kleines Risiko (keine Nutzung seit Mixer-Ende 2020, kein Widerspruch gegen Nexon). Größeres Risiko neu gefunden: Amazon „EMBER“, EU-Marke eingetragen 10.10.2026, Kl. 9, 35, 38, 41, 42, Amazons Smart-TV-Marke seit 2026. Außerdem verteidigt Bright Star („EMBER SWORD“) gegen Nexons „EMBERS OF THE UNCROWNED“ (Widerspruch offen). Entscheidung Dennis offen, kein Zeitdruck.
  - 05.11.2026, 16:38: Kosten einer eigenen Markenanmeldung (Amtsgebühren, ohne Anwalt): DPMA (nur Deutschland) 290 € elektronisch inkl. bis zu 3 Klassen, Verlängerung nach 10 Jahren 750 €; EUIPO (EU) 850 € für 1 Klasse, 900 € für 2, 1.050 € für 3. Für die Plattform naheliegend Kl. 9, 41, 42. EU-Förderung (SME Fund 2026) für Marken bereits ausgeschöpft. Zeitpunkt: erst nach endgültiger Namensklärung (Dennis' Entscheidung).
- [ ] Wiedervorlage Marke: Name und Markenlage neu prüfen, sobald Werbung oder andere Einnahmen eingeschaltet werden, die Nutzung deutlich wächst (Dennis, 17:21: lieber umbenennen, bevor es richtig viral geht, dann ist der Markenschaden klein) oder eine Markenanmeldung ansteht (Hypothese Claude: ohne geschäftlichen Verkehr greift das Markenrecht kaum; mit Werbung schon). Dann auch den Ausgang von „EMBER SWORD“ gegen „EMBERS OF THE UNCROWNED“ nachsehen
- [x] P1 Markenprüfung für „9MBRS“ und erneut „Nine Embers“ in TMview nachholen. Erledigt 05.11.2026, 13:31: keine Marke für 9MBRS, Nine Embers, NineEmbers oder 9embers. Bestandteil „EMBERS“ allein ist in Software-Klassen eingetragen (u. a. Microsoft, Embers SAS); vor einer eigenen Markenanmeldung fachlich prüfen lassen. Details [NAMENSPRUEFUNG.md](NAMENSPRUEFUNG.md). Ursprünglich: (TMview hat den Rechner am 05.11.2026 gegen 04:13 nach vielen automatischen Abfragen gesperrt; später langsam prüfen). Laut Retro v1.2: sequenziell, mit Kontrollabfrage (bekannter Treffer), bei mehr als 100 Treffern blättern; zusätzlich DPMAregister
- [x] P1 Namensentscheid (05.11.2026, 04:18: Nine Embers / 9MBRS, siehe Entscheidungen). Verlauf:
  - 05.11.2026, 02:34: Runde 3 nach Muster Wort plus Zahl (78 Namen geprüft, Bericht in [NAMENSPRUEFUNG.md](NAMENSPRUEFUNG.md)). Dennis' sieben Kandidaten haben alle keine freie .com; nur NightSeven ist sonst sauber. Engere Wahl mit allen vier Domains frei und ohne Marke oder Firma: NoxSeven, DuskSeven, NightEleven, SunTwelve. Empfehlung NoxSeven. .web ist erst ab Mitte Dezember 2026 registrierbar, Inhaber der .com haben danach Vorrang. Entscheidung offen.
  - 05.11.2026, 02:43: Dennis wählt weitere Runde (1d). Runde 4: 267 neue Namen, 81 mit freier .com, 21 voll geprüft und alle sauber (vier Domains frei, keine Marke, keine aktive Firma, keine App). Night360: .com bei Afternic für 9.850 US-Dollar, sonst sauber; Sun360 raus. Empfehlung OwlSeven, Alternativen AnvilSeven und RavenNine. Entscheidung offen.
  - 05.11.2026, 02:53: Runde 5 mit Ziffern. Night7 (.com 3.999 US-Dollar) und Tools5 (.com 2.999 US-Dollar) bei Afternic käuflich, sonst sauber; Tools4 raus. Bei Sun, Tools, Forge, Owl, Moon, Star, Ember und Flare ist die .com mit jeder Ziffer vergeben. 20 Ziffern-Namen voll frei (u. a. Night0, Nox0, Raven0). Aus Runde 4 sind 80 von 81 Namen auf allen vier Endungen frei (Liste im Bericht). Entscheidung offen.
  - 05.11.2026, 02:59: NoxOn und NoxOne geprüft, beide raus (eingetragene Marken in Software-Klassen: NOXON von Palotec AG und NOXON GmbH, NOX ONE von Nox Systems AG; Domains größtenteils vergeben).
  - 05.11.2026, 03:09: Runde 6, Ziffer vorne (Dennis: NineEmbers gefällt, Sorge wegen Länge als Subdomain-Suffix). 9forge (.com 1.995 US-Dollar), 9embers (.com in Benutzung), 5nights (Nähe zu „Five Nights at Freddy's“), 3tools und 5tools fallen raus oder kosten. Voll frei und sauber u. a. 9Forges, 8Embers, 9Anvils, 9Comets, 9Lanterns. Empfehlung: NineEmbers behalten, 9embers.de/.app als Kurzadresse dazunehmen. Entscheidung offen.
  - 05.11.2026, 03:25: Runde 7, erfundene Fantasy-Namen: 123 erzeugt, 43 auf allen vier Endungen frei und ohne Marke; engere Wahl von 12 auch ohne Firma und App. Favoriten Claude: Lumivael, Miravael, Nocturell. Entscheidung offen.
  - 05.11.2026, 03:38: Runde 8. Drei Buchstaben: .com, .de, .app praktisch alle vergeben, raus. Kurze Kunstnamen (5 bis 6 Buchstaben) voll frei und sauber: Cawyn, Lumwen, Nyvael, Syvael, Naewyn, Noxwyn, Embael, Vyriel, Iravyn, Ylaria. Entscheidung offen.
  - 05.11.2026, 03:43: Runde 9, gemütlich und seriös: 221 Namen, 23 voll frei und ohne Marke (u. a. Funkennest, Nachtstube, KilnNook, HoneyKiln, SlateKiln, FlintKiln, ClearKiln). Entscheidung offen.
  - 05.11.2026, 03:51: Runde 10, 2 bis 5 Zeichen: 2 und 3 Zeichen auf .com und .de komplett vergeben. Ziffer + 3 Konsonanten oft frei; voll frei u. a. 9FRG, 9KLN, 9GLW, 9WRK, 9PPS, 9KRX, 9NVX. Entscheidung offen.
  - 05.11.2026, 04:14: Runde 11, Kürzel plus ausgeschriebener Name. Am stärksten: 9MBRS / Nine Embers (alles frei, auch nineembers.com, Marke in Runde 4 ohne Treffer), 9FRG / Nine Forge (frei bis auf nineforge.com), 9KLN / Nine Kilns, 9NVL / Nine Anvils, 9CMT / Nine Comets. Seven-Varianten haben fast alle aktive Firmen. TMview hat den Rechner nach vielen Abfragen gesperrt; Markenprüfung dieser Runde offen, später nachholen. Entscheidung offen.
- [ ] P2 Plattform-Plan im frischen Chat, nach einer Pause (Retro v1.2): Inventur aller Apps, Architektur, Akzeptanzkriterien, Pre-Mortem; erster Schnitt Einstiegsseite plus Treffpunkt
  - 05.11.2026, 17:21: Anforderung „umzugsfähig“ in den Plan aufnehmen (Dennis und Claude): (1) Daten, die im Browser an der Adresse hängen (lokaler Speicher, anonyme Anmeldung), müssen auf eine neue Domain mitgenommen werden können, z. B. per Übergabeseite, die beim Umzug die Kennung im Link-Anker (#) an die neue Adresse übergibt; (2) Umleitung der alten Domain per 301, Pfade erhalten, alte Domain mindestens ein bis zwei Jahre behalten; (3) neue Domain vorab beim Anbieter freigeben (z. B. autorisierte Domains in Firebase). Erst die Übergabeseite, danach die reine Umleitung
- [ ] Entscheidung offen (04.11.2026, 14:58): Adress-Architektur der Plattform (Subdomains, Pfade oder eigene Domains pro App). Optionen und Empfehlung im Chat vom 04.11., Entscheidung im Plattform-Chat
- [ ] P3 Treffpunkt einmalig auf die endgültige Domain umziehen, direkt danach erste echte Veranstaltung. Laut Retro v1.2 mit festem Datum, damit der Praxistest nicht erneut rutscht
- [x] Turret Syndrome als privates GitHub-Repo sichern. 04.11.2026, 14:55 geprüft: lokales Git-Repo `D:\UnityProjects\TurretSyndrome` ohne Remote (kein `[remote]` in `.git/config`, keine `refs/remotes`), Commits 29.05. bis 01.07.2026 liegen nur lokal. Erledigt 05.11.2026, 00:12: privates Repo `brisk-one/turret-syndrome`, alle Zweige gepusht, `master` maßgeblich (Turret-Syndrome-Hub W11)
- [ ] Skill `naming-check` um die Lehren aus Retro v1.2 ergänzen (genannte Einschränkungen als feste Kriterien, Markenabfragen mit Kontrolle und Drosselung, Kürzel und Langform getrennt prüfen, Sprachfallen). Vorschlag an Dennis, Speichern durch ihn

Weitere offene Punkte:

- [ ] Umzug: eigenen Seitennamen anlegen, Deploy einrichten, testen, danach Repo auf privat stellen (Reihenfolge wichtig, sonst Ausfall)
  - 04.11.2026, 11:40: Pausiert, bis Domain und Struktur der geplanten App-Plattform (Einstiegsseite für alle Apps) feststehen. Grund: Jeder Adresswechsel trennt Geräte von ihren Einträgen, ein Doppelumzug soll vermieden werden.

- [ ] Testveranstaltungen in Firestore löschen: „Testlauf (Claude)“, „Animationstest (Claude, löschbar)“, „Zusagetest (Claude, löschbar)“ (Löschen nur durch dich)
- [ ] GitHub verlangt Zwei-Faktor-Anmeldung bis 13.12.2026 (Hinweis auf der Pages-Einstellungsseite gesehen), sonst eingeschränkter Zugriff
- [ ] Optional: Organisator kann einzelne Teilnehmer noch nicht entfernen (Regeln erlauben es bereits, Oberfläche fehlt)
- [ ] Optional, Hypothese: API-Schlüssel in der Google Cloud Console auf `brisk-one.github.io` beschränken, als zusätzliche Absicherung gegen Fremdnutzung des Kontingents
