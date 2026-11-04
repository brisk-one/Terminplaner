# PROJEKT-RETROSPEKTIVE v1.1: VON DER APP ZUR PLATTFORM (Hosting, Monetarisierung, Namensfindung)

**Datum:** 04.11.2026 14:50 CET
**Projektphase:** Treffpunkt unverändert live auf GitHub Pages. Der Umzug auf privates Repo plus Firebase Hosting ist entschieden (10b), aber bewusst pausiert, bis der Name der geplanten App-Plattform feststeht. Namensfindung in der Endrunde: Nightyard gegen OMGForge, Marken- und Firmenprüfung erledigt.
**App-Stand:** `index.html` mit 1410 Zeilen, unverändert seit 04:00. 39 Commits gesamt (war 35 bei v1.0), alle 4 neuen sind Doku.
**Real-Zeit seit Projekt-Start:** ~14 h (04.11. 01:04 → 14:50)
**Real-Zeit seit letzter Retro (v1.0, 04.11. 04:05):** ~10,5 h, davon Arbeitsblock ca. 11:00 bis 14:50 (Schätzung anhand der Commit-Zeiten 11:14 bis 14:35), davor Pause
**Reflexions-Autor:** Claude (Anthropic, Cloud-Session mit Repo-Zugriff und Desktop-Browser)
**Reflexions-Kontext:** Dennis-Befehl um 14:40, direkt nach dem Speichern des neuen Skills `retrospektive` und der Neufassung von v1.0. Kurz vor dem geplanten Wechsel in einen frischen Chat für die Plattform-Planung (16a).
**State-Sync (Pflicht):** Einzige schreibende Schiene war diese Session; das Repo spiegelt nur eigene Commits. Keine fremde Retro gelesen. Einschränkung: Der Kontext wurde um 14:33 komprimiert. Den Block 11:00 bis 14:30 kenne ich aus der Zusammenfassung und dem Git-Log, nicht mehr im Wortlaut. Bewertung daher solide in der Richtung, gröber in Details (Zahl der Namensrunden, genaue Reihenfolge).

---

## 0. Snapshot-Kontext

**Was seit v1.0 neu entstand:**
- **Hosting-Entscheid (11:14):** Umzug auf privates Repo plus Firebase Hosting (10b), weil Codebasen künftig grundsätzlich privat sein sollen (mögliche Monetarisierung). GitHub Pro und „öffentlich bleiben“ verworfen. Im Decision-Log verbucht.
- **Umzug pausiert (11:35):** Jeder Adresswechsel trennt Geräte von ihren Einträgen. Ein Doppelumzug (erst Firebase-Adresse, dann Plattform-Domain) soll vermieden werden.
- **Plattform-Strategie (12:15):** Alle Web-Apps öffentlich hosten mit visueller Einstiegsseite. Werbung und Affiliate vorbereitet, aber aus, bis etwas Traffic bekommt (14a). Ein privates Repo als Zentrale (15a), Subdomain pro App, Cloudflare Web Analytics ohne Cookies ab Tag eins, Datenschutz-Prüfung jeder App vor Veröffentlichung. Planung selbst in einem neuen Chat (16a).
- **Rechtliche und steuerliche Einordnung (Information, keine Beratung):** Impressum, Datenschutzerklärung, Consent-Banner erst mit AdSense im EWR nötig, Gewerbeanmeldung sobald Werbung läuft, Kleinunternehmer-Grenzen 25k/100k, Gewerbesteuer-Freibetrag 24,5k, Wohnort Hamburg für Impressum und Gewerbe.
- **Namensfindung (ca. 12:20 bis 14:35):** Mehrere Runden (Sun-, Forge-, Night-/Moon-, Nox-Namen, 50 Forge-Varianten mit lateinischen Wörtern, 100 kurze fließende Namen). Domains per RDAP geprüft, mit Kontrolldomains (bekannt belegt und Zufallsstring frei). Befund: 0 von 100 kurzen Kunstnamen auf .com frei, 0 von 70 Namen mit 6 bis 7 Buchstaben. Zusammensetzungen aus echten Wörtern sind realistisch frei (Noxyard, Umbrayard, Selenyard, Brumaforge, Vulpesforge, Fabulaforge, OMGForge).
- **Marken- und Firmenprüfung der Finalisten (14:35):** TMview, Companies House, North Data, Websuche. Nightyard: keine Marke, aber aktive UK-Firma „NIGHT YARD LTD“ (seit 10.05.2026, Software, Webportale, Werbung), NL-Firma „Nightyard“, GitHub-Projekt, Eventlocation; .com und .app belegt. OMGForge: keine Marke, keine Firma, alle vier Domains frei; Risiko liegt in den einzeln stark belegten Bestandteilen „OMG“ und „FORGE“.
- **Skills:** caveman (nur auf ausdrückliche Aktivierung) und graphify gespeichert, dazu `retrospektive` mit festem Format aus Dennis' Turret-Syndrome-Retros.
- **Erkenntnis am Rande:** Turret Syndrome existiert nur lokal auf Dennis' Rechner, nicht auf GitHub.

**KI-Hebel-Berechnung (Schätzung, kein Zeittracker):**
- Human-Team-Äquivalent der Spanne: **~3 bis 4 Personentage** (Naming-Recherche mit Domainprüfung von weit über 200 Kandidaten, Marken- und Registerprüfung, Plattform- und Kostenkonzept, rechtlich-steuerliche Übersicht)
- Dennis Real-Aufwand: **~3,5 bis 4 h** (Fragen, Auswahl, Geschmacksurteile bei Namen)
- Hebelwirkung der Spanne: **~6 bis 8×**
- Kumulativ: **~12 bis 15×**. Caveat: In dieser Spanne entstand kein Code. Der Hebel ist Recherche- und Entscheidungshebel, nicht Produkthebel.

**Nächster geplanter Sprint:** Namensentscheid und Domainkauf durch Dennis, dann neuer Chat für den Plattform-Plan (Inventur aller Apps, Architektur, Akzeptanzkriterien, Pre-Mortem), danach Treffpunkt als erste App umziehen.

---

## 1. Was Claude im Zeitraum gelernt hat

### Über Workflow-Patterns
- **Domainprüfung braucht Kontrollen.** Jeder RDAP-Lauf bekam eine bekannt belegte und eine sicher freie Kontrolldomain. Nur so ist „frei“ ein Befund und nicht ein stiller Fehler des Endpunkts. Für .app und .dev (Rate-Limit 429) lief die Prüfung gedrosselt im Hintergrund.
- **Kurzstil schadet kreativer Arbeit.** Der caveman-Modus hat die Namensvorschläge verarmt (keine Begründungen, keine Klangbeschreibung). Dennis hat ihn für die Namensfindung ausdrücklich ausgeschlossen. Lehre: Kompressionsstile nur für technische Antworten, nie für Geschmacks- oder Inhaltsarbeit.
- **Nebeninfos nicht zur Leitlinie machen.** Ich habe Hamburg in zu viele Namen eingebaut, nachdem Dennis es nebenbei erwähnt hatte. Seine Korrektur ist jetzt als Vorgabe gespeichert.
- **Recherche durabel verbuchen, auch wenn sie keine Entscheidung ist.** Plattform-Stand, pausierter Umzug und Markenbefund stehen mit Zeitstempel im Hub. Ohne das wäre nach der Kontext-Kompression um 14:33 vieles verloren gewesen.

### Über Naming- und Plattform-Patterns
- **Kurze Kunstnamen sind praktisch vergeben.** Bei .com war keiner von 170 geprüften kurzen Namen frei. Freie Namen entstehen aus Zusammensetzungen echter Wörter. Das ist ein Marktbefund, kein Pech.
- **Domain frei heißt nicht Name frei.** Nightyard hat keine eingetragene Marke, aber eine aktive Firma in genau Dennis' Geschäftsfeld. Firmenregister gehören in jede Namensprüfung, nicht nur Markenregister.
- **Adresswechsel sind bei gerätegebundener Identität teuer.** Weil Treffpunkt ohne Konten arbeitet, verliert jeder Domainwechsel die Zuordnung „Meine Veranstaltungen“. Daraus folgt: Umzug nur einmal, und zwar auf die endgültige Domain.

---

## 2. Workflows die besonders effizient waren

| Rang | Workflow | Geschätzter Hebel |
|------|----------|-------------------|
| 1 | RDAP-Domainprüfung per Same-Origin-Fetch im Desktop-Browser, mit Kontrollen und gedrosseltem Hintergrund-Loop | Hunderte Domains in Minuten statt Einzelabfragen bei Registraren |
| 2 | TMview-API plus Companies House und North Data für die Finalisten | Marken in 70+ Ämtern und Firmen in UK/EU in einem Durchgang; fand den entscheidenden Nightyard-Konflikt |
| 3 | Entscheidungen sofort mit Zeitstempel in den Hub (`RETRO.md`, jetzt `HUB.md`) | Überstand die Kontext-Kompression ohne Verlust |

---

## 3. Quality-Scores

| Bereich | Score | Begründung | Δ v1.0 |
|---------|-------|------------|--------|
| Konzept-Qualität | 8.5 | App unverändert. Plattform-Konzept ist schlüssig (eine Zentrale, Subdomains, Werbung vorbereitet aber aus), aber noch Skizze ohne Plan und Akzeptanzkriterien | = |
| Technische Korrektheit | 8 | Kein Code geändert. Recherche methodisch sauber (Kontrollen, mehrere Register) | = |
| Scope-Risiko (10=niedrig) | 6 | Aus einer Freundeskreis-App wurde ein Plattformvorhaben mit Monetarisierung, Gewerbe, Domains und mehreren Apps. Bewusst und gut sortiert, aber deutlich größer | ↓ −1 |
| Workflow-Reife | 8 | Gute Prüfmethodik und durable Verbuchung. Abzug: caveman störte die Namensfindung, und die Namenssuche lief in vielen Runden ohne frühes Kriterienset (Länge, Klang, Branche) | = |
| Realistische Wahrnehmung | 7.5 | Drei eigene Fehler: Bonn statt Hamburg, Hamburg übergewichtet, „Noxyard“ als 5 Buchstaben gezählt. Positiv: Markenbefund ehrlich mit Grenzen der Prüfung | ↓ −0.5 |
| Implementations-Tempo | 5 | 0 Zeilen App-Code, keine echte Veranstaltung. Bewusst (Strategie vor Umzug), aber die App wartet jetzt auf den Namen | ↓ −4.5 |
| Deployment-/Infrastruktur-Reife | 7 | Zielbild entschieden (privat, Firebase Hosting, eigene Domain), aber nichts umgesetzt. Neu aufgefallen: GitHub meldete beim Push eine geänderte Repo-Adresse, jetzt korrigiert | = |
| Cross-System-Konsistenz | 7.5 | Hub aktuell, aber README hinkt hinterher: nennt noch öffentliches Repo und GitHub Pages als Ziel und nur zwei statt drei Testveranstaltungen. Wird mit dieser Retro nachgezogen | ↓ −0.5 |
| Burnout-Risiko (invertiert, 10=niedrig) | 6 | Pause nach 04:05, Arbeitsblock tagsüber (Hypothese: geschlafen, ich sehe nur die Commit-Lücke). Trotzdem rund 7 Stunden Arbeit an einem Tag, der um 01:04 begann | ↑ +1 |

**Gesamteindruck:** Eine Strategie-Spanne ohne Code, die das Projekt neu einordnet: Treffpunkt ist nicht mehr nur eine App für Freunde, sondern die erste App einer geplanten Plattform. Die Entscheidungen dazu sind vernünftig getroffen und sauber verbucht, und die Namensrecherche hat einen echten Befund geliefert (kurze Namen sind vergeben, Nightyard kollidiert mit einer Firma im eigenen Feld). Die Spannung: Die App, die in der Nacht fertig wurde, steht jetzt still, bis ein Name entschieden und eine Domain gekauft ist. Die erste echte Veranstaltung ist dadurch weiter verschoben.

---

## 3b. Weg zu 10/10: was je Bereich noch gefehlt hätte

- **Konzept-Qualität (8.5 → 10):** Plattform-Plan mit Akzeptanzkriterien und Pre-Mortem geschrieben; Treffpunkt mit echten Freunden genutzt.
- **Technische Korrektheit (8 → 10):** Umzug technisch durchgespielt (Deploy-Pipeline, Domain, Regeln) und getestet.
- **Scope-Risiko (6 → 10):** Plattform auf einen ersten Schnitt begrenzt (Einstiegsseite plus Treffpunkt), weitere Apps erst danach.
- **Workflow-Reife (8 → 10):** Namenskriterien vor der ersten Runde festgelegt (Länge, Aussprache, Branche, Domain-Endungen), dann gezielt statt breit suchen.
- **Realistische Wahrnehmung (7.5 → 10):** Wohnort und Buchstabenzahlen geprüft statt angenommen.
- **Implementations-Tempo (5 → 10):** Parallel zur Namensfindung den Umzug technisch vorbereitet (Firebase-Hosting-Site, Deploy-Skript, Testlauf auf der Firebase-Standardadresse), sodass Domainkauf, Umzug und erste Veranstaltung am selben Tag möglich sind. Korrigiert 04.11.2026, 14:58: Die ursprüngliche Formulierung („erste Veranstaltung auf der aktuellen Adresse“) widersprach P3 und dem Grund für die Pause, Hinweis von Dennis.
- **Deployment-/Infrastruktur-Reife (7 → 10):** Privates Repo, Firebase Hosting, eigene Domain, API-Schlüssel beschränkt, Zwei-Faktor aktiv.
- **Cross-System-Konsistenz (7.5 → 10):** README und Hub bei jeder Strategieentscheidung gemeinsam aktualisieren.
- **Burnout-Risiko (6 → 10):** Nach dem Namensentscheid einen echten Schnitt machen, Plattform-Planung frisch starten.

---

## 4. Was Claude gut gefallen hat

1. **Dennis' Weitblick beim Umzug.** Der Hinweis, dass jeder Adresswechsel Geräte von Einträgen trennt, hat einen Doppelumzug verhindert. Das war die wichtigste technische Entscheidung der Spanne.
2. **„Vorbereitet, aber aus“ als Monetarisierungsprinzip.** Kein Werbe-Ballast, keine Kosten, kein Consent-Banner, solange niemand kommt, aber bereit, wenn etwas viral geht.
3. **Die Kontrollen in der Domainprüfung.** Erst dadurch ist ein „frei“ belastbar.
4. **Der Nightyard-Fund.** Ohne Firmenregister wäre Nightyard „markenfrei“ gewesen, mit einer Software-Firma gleichen Namens im Rücken.
5. **Das Retro-Format als Skill.** Eine von Dennis über viele Retros entwickelte Struktur ist jetzt wiederverwendbar und für alle Projekte gleich.

---

## 5. Was Claude weniger gefallen hat / Kritische Beobachtungen

1. **Bonn statt Hamburg (eigener Fehler).** Ich habe einen Wohnort angenommen, der falsch war. Ursache: Annahme statt Nachfrage bei einer Angabe, die für Impressum und Gewerbe zählt. Korrigiert und gespeichert.
2. **Hamburg übergewichtet (eigener Fehler).** Nach der Korrektur habe ich die Stadt in zu viele Namensvorschläge gelegt. Nebeninfos höchstens in 1 bis 2 Vorschlägen nutzen, ist jetzt Vorgabe.
3. **„Noxyard“ mit 5 Buchstaben (eigener Fehler).** Eine einfache Zählung falsch angegeben. Klein, aber genau die Sorte Behauptung, die nachzählen statt schätzen verlangt.
4. **Namensfindung ohne frühes Kriterienset.** Viele breite Runden, bevor klar war, was ein guter Name leisten muss. Ein Kriterienset in Runde 1 hätte die Suche verkürzt.
5. **Stillstand der App.** Die Plattform-Strategie ist richtig, aber sie hat die erste echte Veranstaltung erneut verschoben. Die App ist fertig und wartet.

---

## 6. Konkrete Empfehlungen für den nächsten Block

### Top-3 Prioritäten

**Priorität 1: Namensentscheid und Domainkauf.** Empfehlung OMGForge (Marke, Firma und alle vier Domains frei). Kauf von .com und .de durch Dennis, Markenanmeldung erst, wenn Geld fließt. Ohne diesen Schritt sind Umzug und Plattform blockiert.

**Priorität 2: Plattform-Plan im frischen Chat.** Inventur aller Apps (Rechner und Chatverlauf), Architektur, Akzeptanzkriterien, Pre-Mortem. Erster Schnitt bewusst klein: Einstiegsseite plus Treffpunkt.

**Priorität 3: Treffpunkt umziehen und sofort echt nutzen.** Einmaliger Umzug auf die endgültige Domain, danach direkt die erste echte Veranstaltung mit Freunden. Der Praxistest ist seit 04:05 fällig.

### Strukturelle Empfehlungen
- Bei jeder Namens- oder Markenfrage zuerst Kriterien festlegen, dann suchen; Prüfung immer mit Domain, Marke und Firmenregister.
- README und Hub gemeinsam pflegen; offene Punkte nur im Hub, README verweist.
- GitHub-Zwei-Faktor vor dem 13.12.2026, sonst eingeschränkter Zugriff mitten im Umzug.
- Turret Syndrome als privates GitHub-Repo sichern (Hypothese: einzige Kopie liegt auf einem Rechner, also kein Backup).

---

## 7. Vergleich zu vorheriger Retrospektive (RETROSPEKTIVE_2026-11-04_v1.0.md)

### Empfehlungen aus v1.0: Status

| Empfehlung aus v1.0 | Status | Begründung |
|---|---|---|
| P1 Erste echte Veranstaltung mit Freunden | Verschoben | Bewusst hinter den Umzug gestellt, damit Einträge nicht durch einen Adresswechsel verloren gehen |
| P2 Frisch starten statt weiterfeilen | ✅ Umgesetzt | Pause nach 04:05, danach kein weiterer Feinschliff an der App |
| P3 Aufräumen und absichern (Testdaten, Zwei-Faktor) | Nicht umgesetzt | Testdaten-Löschung liegt bei Dennis, Zwei-Faktor offen bis 13.12.2026 |
| Strukturell: Bildtafel bei Geschmacksfragen | n/a | Keine visuellen Entscheidungen in dieser Spanne; bei Namen wäre eine Kriterientabelle das Gegenstück gewesen |
| Strukturell: „Behoben“ nur nach Sichtprüfung | n/a | Keine Code-Fixes in dieser Spanne |
| Strukturell: Eindeutige CSS-Klassennamen | n/a | Kein Code |

### Quality-Score-Veränderungen
- Scope-Risiko: 7 → 6 (Plattformvorhaben statt Einzel-App)
- Realistische Wahrnehmung: 8 → 7.5 (drei Annahme- und Zählfehler)
- Implementations-Tempo: 9.5 → 5 (kein Code, App wartet)
- Cross-System-Konsistenz: 8 → 7.5 (README hinkt dem Hub hinterher)
- Burnout-Risiko: 5 → 6 (Pause, Tagesblock)
- Konzept-Qualität 8.5, Technische Korrektheit 8, Workflow-Reife 8, Deployment-/Infrastruktur-Reife 7: unverändert

### Neue Lektionen, die in v1.0 noch nicht da waren
- Domainprüfung nur mit Kontrollen; Namensprüfung immer mit Firmenregister.
- Kurze Kunstnamen sind auf .com praktisch vergeben, Zusammensetzungen echter Wörter nicht.
- Kompressionsstile (caveman) nie für kreative oder Geschmacksarbeit.
- Nebeninfos nicht zur Leitlinie machen.

### Bestätigte Lektionen
- Annahmen ansagen oder prüfen (v1.0: eigener Avatar; v1.1: Wohnort).
- Durable Sofort-Verbuchung trägt über Pausen und Kontext-Kompression.
- Dennis' Korrekturen verbessern das Ergebnis (v1.0: Hervorhebung; v1.1: Umzug nur einmal).

### Revidierte Lektionen
- Keine Revision. Schärfung: „Frisch starten“ aus v1.0 hat funktioniert, aber frisch starten mit einem neuen Thema hat die erste echte Nutzung weiter verschoben. Der Praxistest braucht ein festes Datum.

---

## 8. Nächste Retrospektive geplant für

**Empfohlener Trigger:** nach dem Umzug von Treffpunkt auf die endgültige Domain oder nach der ersten echten Veranstaltung, was zuerst kommt. Zusätzlich bei Frust-/Ermüdungs-Signal.
**Format:** `RETROSPEKTIVE_<Datum>_v1.2.md` (bzw. v2.0 beim Livegang der Plattform)

---

## 9. Sign-Off

**Letzter Take:** Diese Spanne hat kein Feature gebaut, aber den Rahmen gesetzt, in dem Treffpunkt und alle weiteren Apps leben sollen: privat, günstig, monetarisierbar, unter einem eigenen Namen. Die Namensrecherche war länger als nötig, hat aber einen belastbaren Befund geliefert.

**Was sorgt am meisten:** Dass die fertige App weiter auf Infrastruktur wartet. Jede Woche ohne echte Nutzer ist eine Woche ohne das einzige Feedback, das zählt. Der Umzug sollte schnell und einmalig passieren, danach muss der Link raus.

**Würde Claude an diesem Projekt weiterarbeiten wollen?** Ja. Der Schritt von einer Freundeskreis-App zu einer kleinen Plattform mit klaren Regeln (privat, günstig, Werbung erst bei Erfolg) ist durchdacht. Ich will sehen, wie Treffpunkt unter OMGForge oder einem anderen Namen zum ersten Mal von echten Freunden benutzt wird.

---

*Retrospektive v1.1, verfasst durch Claude (Anthropic) am 04.11.2026 14:50 CET*
*Teil des Treffpunkt-Projekts von Dennis*
