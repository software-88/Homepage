# Bestandsaufnahme schmidt-solutions.de
Stand: 23.09.2026 · erstellt von Freddy · Grundlage: öffentliche Prüfung der Live-Website (kein Admin-/IONOS-Zugriff)

## 1. Status: Zielarchitektur (beschlossen)
- CMS: Strapi Cloud (managed)
- Frontend: Astro, gehostet auf Cloudflare Pages
- Code/Versionierung: GitHub (vorhanden)
- Agentenzugriff: Strapi MCP mit eingeschränktem Admin-Token (kein Löschen, keine eigenständige Veröffentlichung)
- Domain/E-Mail: vorerst weiter bei IONOS
- Ethan: wird erst bei konkretem Entwurf einbezogen

## 2. Bestehende URLs (Crawl-Basis)
| Aktuelle URL | Inhalt | Status/Auffälligkeit |
|---|---|---|
| `/` | Startseite, Leistungsübersicht, EAVISION J100 | ok, aber Baukasten-Struktur |
| `/leistungen` | Leistungsübersicht | Slide-Platzhalter „Slide title / Write your caption here / Button“ sichtbar |
| `/leistungen/landwirtschaft` | Landwirtschaftliche Leistungen im Detail | viele leere „Button“-Elemente ohne Text/Ziel, Platzhalter „Button“ mehrfach wiederholt |
| `/leistungen#Inspektionen` | Ankerlink zu Inspektionen (kein eigenständiger Content geprüft) | Ankerstruktur, kein sauberer eigener Slug |
| `/schulung-und-vertireb` | Schulung, Vertrieb, Wartung | **Tippfehler im Slug** ("vertireb" statt "vertrieb") |
| `/produkte` | Drohnenmodelle (EAVISION J100, DJI Mavic 3M) inkl. technischer Daten und Kontaktformular | viele Platzhalter „Bildtitel / Untertitel hier einfügen / Button“; Kontaktformular ohne sichtbare Feldbeschriftung/Struktur |
| `/lenksysteme` | Lenksysteme (Produktkategorie) | **liefert aktuell einen Serverfehler (504 Gateway Timeout) statt Inhalt** – dringend prüfen |
| `/über-uns` | Team (Jan & Rebecca Schmidt), Kontaktdaten | Umlaut-URL, Slide-Platzhalter vorhanden |
| `/kontakt` | Kontaktdaten + vollständige Datenschutzerklärung auf derselben Seite | inhaltlich umfangreich, aber Struktur vermischt Kontakt und Datenschutzrecht auf einer URL |
| `/impressum7fff571f` | Impressum (inhaltlich vollständig, USt-ID vorhanden) | **technisch unschöne URL**, sollte zu `/impressum` werden |

## 3. Kontaktdaten – Inkonsistenzen (vor Übernahme klären)
- Telefonnummern: `0172 / 164 49 44` und `0162 / 239 11 73` werden angezeigt, das zweite `tel:`-Linkziel verweist technisch aber ebenfalls auf `+491721644944` (Weiterleitung auf dieselbe Nummer, nicht auf die zweite Nummer).
- E-Mail: Sichtbar überall `drohne@schmidt-solutions.de`. Im Linkziel (`mailto:`) sowie im Impressum/Datenschutztext steht teils `Jan@jrschmidt-home.de` als Verantwortlicher-Adresse.
- Adresse einheitlich: Grauhöfle 7/1, 74429 Sulzbach-Laufen, Baden-Württemberg.
- **Bitte von Jan bestätigen:** Welche Telefonnummer(n) und welche E-Mail-Adresse(n) sind aktuell tatsächlich gültig und sollen künftig einheitlich auf der ganzen Website erscheinen?

## 4. Sichtbare Baukasten-Platzhalter (müssen ersetzt werden)
Gefunden auf: `/leistungen`, `/leistungen/landwirtschaft`, `/produkte`, `/über-uns`
- „Slide title“ / „Bildtitel“
- „Write your caption here“ / „Untertitel hier einfügen“
- Leere „Button“-Elemente ohne Linkziel oder Beschriftung (mehrfach wiederholt, teils 4–8 Stück pro Abschnitt)

Empfehlung: Im neuen Content-Modell gibt es keine generischen Slide-/Button-Komponenten ohne Pflichtfelder mehr – jedes Element bekommt Titel, Text und Ziel als Pflichtfeld, damit sowas nicht mehr live gehen kann.

## 5. Technische Befunde
- `robots.txt` verweist auf Sitemap unter `https://www.schmidt-solutions.de/sitemap.xml` (www-Variante) – Canonical-Domain (mit/ohne www) muss beim Relaunch einmal eindeutig festgelegt werden.
- `/lenksysteme` liefert einen 504-Fehler – **Priorität: prüfen, ob das dauerhaft oder nur temporär ist.**
- Kein eigenständiges, klar strukturiertes Kontaktformular auf `/kontakt` erkennbar; Formulare tauchen (mit Fehlermeldungstext für Sendefehler) auf den Produktseiten auf.

## 6. Rechtliches (nur Hinweis, keine Rechtsberatung)
- Datenschutzerklärung ist auf `/kontakt` integriert und inhaltlich umfangreich (Server-Logfiles, IONOS-Hosting, WhatsApp Business, YouTube, Google Maps, reCAPTCHA, Cookie-Consent-Tool).
- Verantwortlicher laut Datenschutztext: Jan Schmidt, mit abweichender E-Mail-Adresse zur sichtbaren Kontakt-Mail (siehe Punkt 3).
- Diese Inhalte sollten vor dem Relaunch von Jan (ggf. mit rechtlicher Prüfung) bestätigt und aktualisiert werden – Freddy übernimmt sie nur unverändert, ändert aber nichts eigenständig an rechtlichen Aussagen.
- **Freigabepflichtig / offen:** Morgan prüft die Datenschutzseite (DSGVO-Text auf `/kontakt`) inhaltlich, sobald die neue Seite dafür bereitsteht. Bis diese Prüfung erfolgt ist, wird der bestehende Datenschutztext unverändert übernommen und nicht eigenständig von Freddy inhaltlich angepasst.

## 7. Offene Fragen an Jan
1. ~~Ist `/lenksysteme` dauerhaft defekt oder nur ein temporärer Fehler?~~ → **Geklärt (24.09.2026):** Lenksysteme entfallen komplett als Angebot.
2. Welche Telefonnummer(n)/E-Mail(s) sind aktuell wirklich in Benutzung?
3. Gibt es weitere Unterseiten, die beim Crawl nicht auffindbar waren (z. B. nicht verlinkte Landingpages, Kampagnenseiten)?
4. Gibt es vorhandenes Bildmaterial (Drohnenfotos, Team, Einsätze) in guter Auflösung, das übernommen werden soll, oder muss neues Material beschafft werden?
5. Sollen die bestehenden Google Maps-/YouTube-/WhatsApp-Einbindungen 1:1 übernommen werden oder ist das eine gute Gelegenheit, das technisch/datenschutzrechtlich zu verschlanken?
6. ~~Wie sollen schmidt-solutions.de und agridrones-europe.com künftig zueinander stehen?~~ → **Geklärt (30.09.2026):** Beide Seiten bleiben getrennt. schmidt-solutions.de fokussiert auf Dienstleistung/Beratung/Training (Landwirtschaft, Weinbau, Forst), agridrones-europe.com bleibt der eigenständige Drohnen-Shop mit Produkten, Zubehör und Software. Beide Seiten werden künftig klar gegenseitig verlinkt, um Verwirrung bei Nutzern und Suchmaschinen zu vermeiden.

## 8. Nächste Schritte
1. Jan beantwortet die offenen Fragen aus Punkt 7.
2. Freddy entwirft die neue Informationsarchitektur (Seitenstruktur, URL-Konzept, Redirect-Tabelle alt → neu).
3. Freddy modelliert die Strapi-Content-Types (Leistungsseite, Produkt, Schulung, Team, Referenz, Fachbeitrag, FAQ, globale Einstellungen).
4. Aufbau Astro-Grundgerüst + Cloudflare Pages Preview-Deployment.
5. Freigaberunde mit Jan vor jeder inhaltlichen Veröffentlichung.

## 9. Zweite Domain: agridrones-europe.com (ergänzt 30.09.2026)

Auf Hinweis von Jan geprüft: **agridrones-europe.com** ist eine weitere, eigenständig betriebene Website von Schmidt Solutions – technisch auf WordPress, inhaltlich deutlich moderner und vollständiger gepflegt als schmidt-solutions.de in einigen Bereichen. Kein Admin-Zugriff, nur öffentliche Prüfung.

### Struktur der Seite
```
/                       Startseite ("Better drones. Bigger results")
/drones/                Drohnenübersicht
/eavision-j150/         EAVISION J150 (2026) – Flaggschiff, 70L/100L Tank
/eavision-j70/          EAVISION J70 (2026) – kompakte Allround-Drohne, 30L Tank
/eavision-j100/         EAVISION J100 (2025) – Allrounder, 40L Tank
/dji-mavic-3m/          DJI Mavic 3 Multispektral (Kamera-/Analysedrohne)
/pix4dfields/           Software-Seite (Auswertungssoftware)
/zubehoer/              Zubehörübersicht
/stromerzeuger/         Zubehör: Stromerzeuger
/stromspeicher/         Zubehör: Stromspeicher
/mischfaesser/          Zubehör: Mischfässer
/service-wartung/       Beratung, Schulung, Service, Genehmigungen/SORA-Prozess
/team/                  Team-Seite (Jan & Rebecca Schmidt, mit Fotos & Bios)
/contact/               Kontakt
/impressum/             Impressum (eigenständig, sauberer Slug)
/privacy-policy/        Datenschutzerklärung (eigenständig)
/en/...                 Komplette englische Übersetzung aller Seiten (Sprachumschalter vorhanden)
```

### Wichtige inhaltliche Funde
- **Produktdaten deutlich detaillierter** als auf schmidt-solutions.de: technische Eckdaten zu Tankgröße, LiDAR-Hinderniserkennung, patentierter CCMS-Sprühtechnologie, Batteriesystem (9-Minuten-Laden) etc.
- **Bereits zwei zusätzliche, neuere Drohnenmodelle** (EAVISION J150 und J70, beide "2026"), die auf schmidt-solutions.de bisher gar nicht auftauchen (dort nur J100 und Mavic 3M gelistet).
- **Zubehör-Kategorien** (Stromerzeuger, Stromspeicher, Mischfässer) und eine **Software-Seite (PIX4Dfields)** existieren nur hier, nicht auf schmidt-solutions.de.
- **Mehrsprachigkeit ist hier schon gelöst**: jede Seite hat eine funktionierende `/en/...`-Version. Das ist relevant für die im Root-Auftrag genannte künftige internationale Ausrichtung von Beratung/Training.
- **Service & Wartung-Seite** beschreibt Beratung, Vor-Ort-Schulung, Service und Genehmigungsunterstützung (inkl. SORA-Prozess-Grafik) – inhaltlich sehr nah an dem, was auf schmidt-solutions.de unter „Schulung & Vertrieb" grob behandelt wird, hier aber ausführlicher.
- **Team-Seite** zeigt Jan (Gründer/CEO) und Rebecca Schmidt (Mitgründerin/Management) mit Fotos und Kurzbios – deutlich hochwertiger umgesetzt als die Team-Sektion auf `/über-uns`.
- **Kontaktdaten** decken sich mit schmidt-solutions.de: Adresse Grauhöfle 7/1, 74429 Sulzbach-Laufen; Telefon `+49 172 164 49 44`; E-Mail `drohne@schmidt-solutions.de`.
- **Social-Media-Verlinkung ist markenübergreifend**: Instagram/Facebook/LinkedIn verlinken auf "schmidt_solutions"-Profile, YouTube auf einen "@Agridrones-Europe"-Kanal.
- Eigenes Impressum und eigene Datenschutzerklärung unter sauberen, sprechenden URLs (`/impressum/`, `/privacy-policy/`) – im Gegensatz zu den auf schmidt-solutions.de gefundenen Problemen (kryptische Impressum-URL, Datenschutz in Kontaktseite integriert).
- WhatsApp-Widget ("WhatsApp us") ist eingebunden, ebenso wie auf schmidt-solutions.de erwähnt.

### Einordnung für den Relaunch
Ein erheblicher Teil dessen, was für den Relaunch von schmidt-solutions.de ohnehin geplant war (ausführliche Produktseiten, Weinbau-/Forst-Bezug im Serviceangebot, englische Version, saubere URLs, Team-Darstellung), existiert auf agridrones-europe.com bereits – teils reifer als auf der Hauptseite.

**Entscheidung (30.09.2026):** Jan hat sich für **getrennte Marken/Seiten** entschieden. schmidt-solutions.de bleibt die Plattform für Dienstleistung, Beratung und Training (Landwirtschaft, Weinbau, Forst, Inspektionen), agridrones-europe.com bleibt der eigenständige Drohnen-Shop (Produkte, Zubehör, Software, technischer Service/Genehmigungen rund um die Drohnen selbst). Konsequenzen für die weitere Arbeit:
- schmidt-solutions.de behält die Produktseiten (`/produkte`) nur als schlanken Überblick mit Verweis/Link zu agridrones-europe.com für Kauf, technische Details und Zubehör – keine Duplizierung der ausführlichen Produktdaten.
- Auf beiden Seiten sollte eine klare, gegenseitige Verlinkung ergänzt werden (z. B. Footer-Link oder Hinweisbox „Drohnen kaufen? Zu Agridrones Europe" bzw. „Beratung & Schulung? Zu Schmidt Solutions"), damit Google und Nutzer die Abgrenzung verstehen und sich beide Seiten nicht gegenseitig kannibalisieren.
- Die für schmidt-solutions.de geplanten Themen Weinbau/Forst/Referenzen/Ratgeber bleiben unabhängig von dieser Entscheidung relevant, da sie sich auf Beratung/Dienstleistung beziehen, nicht auf den Produktverkauf.
- Agridrones Europe wird in dieser Runde nicht technisch migriert oder verändert – hier bleibt es bei WordPress, außer Jan äußert später einen expliziten Wunsch dazu.
