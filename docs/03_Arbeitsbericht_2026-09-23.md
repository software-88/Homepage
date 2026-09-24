# Arbeitsbericht – Website-Relaunch schmidt-solutions.de
Stand: 23.09.2026, Ende Arbeitstag · erstellt von Freddy

## Erledigt heute

1. Öffentliche Prüfung der bestehenden Live-Website (alle Hauptseiten, robots.txt) durchgeführt.
2. Bestandsaufnahme erstellt und abgelegt (GitHub `docs/bestandsaufnahme.md`, Google Drive-Ordner "Homepage").
3. Zielarchitektur mit Jan abgestimmt und festgelegt: Astro (Frontend) + Strapi Cloud (CMS) + Cloudflare Pages (Hosting) + GitHub (Code/Versionierung) + eingeschränktes Strapi-MCP-Token für Freddys Agentenzugriff.
4. GitHub-Repository "Homepage" und Google-Drive-Ordner "Homepage" als feste Ablageorte bestätigt und mit Grundgerüst befüllt (README, Bestandsaufnahme, Sitemap-Entwurf, Content-Modell-Entwurf).
5. Sitemap- und URL-Konzept mit vollständiger Redirect-Tabelle (alt → neu) entworfen, inklusive Behebung des Tippfehlers `/schulung-und-vertireb`, der kryptischen Impressum-URL und der defekten Lenksysteme-Seite.
6. Strapi-Content-Modell entworfen: 10 Content-Types (u. a. Leistung, Produkt, Schulung, Team, Referenz, Fachbeitrag, FAQ, Kontaktanfrage) mit Pflichtfeldern, die sichtbare Baukasten-Platzhalter wie auf der aktuellen Seite technisch ausschließen.
7. Rollen-/Rechte-Tabelle für das MCP-Admin-Token entworfen: Freddy kann künftig Inhalte lesen und als Entwurf anlegen/bearbeiten, aber nicht löschen oder eigenständig veröffentlichen.
8. Notiz ergänzt: Morgan prüft die Datenschutz-/DSGVO-Seite inhaltlich, sobald sie fertig vorliegt – bis dahin bleibt der bestehende Rechtstext unverändert.

## Offen / wartet auf Jan

1. Ist `/lenksysteme` dauerhaft defekt (504-Fehler) oder nur ein temporäres Problem?
2. Welche Telefonnummer(n) und E-Mail-Adresse(n) sind aktuell tatsächlich gültig? (Aktuell widersprüchliche Angaben zwischen sichtbarem Text, `tel:`/`mailto:`-Linkzielen und Impressum/Datenschutztext.)
3. Gibt es weitere, aktuell nicht verlinkte Unterseiten oder Landingpages?
4. Ist vorhandenes Bildmaterial (Drohnen, Team, Einsätze) in guter Qualität vorhanden, oder muss neues Material beschafft werden?
5. Sollen bestehende Google Maps-/YouTube-/WhatsApp-Business-Einbindungen 1:1 übernommen oder datenschutzfreundlicher ersetzt werden?
6. Grundsätzliche Freigabe/Rückmeldung zu den drei neu vorgeschlagenen Seiten `/leistungen/weinbau`, `/leistungen/forst`, `/referenzen`, `/ratgeber` – sind das sinnvolle Ergänzungen oder eher nicht leistbar?

## Blockiert

- Keine technische Blockade aktuell. Der Fortschritt bei Punkt "Astro-Grundgerüst aufsetzen" wartet bewusst auf die Antworten oben, damit nicht mit falschen Kontaktdaten oder einer unklaren Struktur gearbeitet wird.

## Freigabepflichtig, bevor produktiv etwas passiert

- Endgültige Sitemap/URL-Struktur (Entwurf liegt vor)
- Strapi-Content-Modell und MCP-Rechte-Tabelle (Entwurf liegt vor)
- Jeglicher veröffentlichter Inhalt auf der neuen Website
- Datenschutztext: Freigabe durch Morgan erforderlich, bevor er final übernommen wird

## Nächste Schritte (sobald offene Punkte geklärt sind)

1. Antworten von Jan einarbeiten, Sitemap und Redirect-Tabelle final abstimmen.
2. Astro-Grundgerüst im GitHub-Repository "Homepage" aufsetzen (Ordnerstruktur, Basis-Layout, Navigation nach neuer Sitemap).
3. Cloudflare Pages Preview-Deployment einrichten, damit Jan Zwischenstände live ansehen kann, ohne dass etwas öffentlich sichtbar wird.
4. Strapi-Instanz in der Cloud aufsetzen und Content-Types gemäß Entwurf anlegen.
5. Erstbefüllung mit vorhandenen Texten aus der Bestandsaufnahme (bereinigt um Platzhalter).
6. MCP-Anbindung mit eingeschränktem Admin-Token einrichten und testen.
7. Vor jedem produktiven Schritt: kurze Freigaberunde mit Jan.

## Risiken, die im Blick bleiben müssen

- SEO-Sichtbarkeitsverlust bei Livegang, falls Redirect-Tabelle nicht vollständig umgesetzt wird.
- Rechtliches Risiko, falls Datenschutztext ohne Morgans Prüfung finalisiert würde – wird bewusst vermieden.
- Datenqualität: Solange Telefonnummer/E-Mail nicht eindeutig bestätigt sind, wird nichts final in die globalen Kontaktdaten übernommen.
