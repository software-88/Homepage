# Arbeitsbericht – Website-Relaunch schmidt-solutions.de
Stand: 30.09.2026 · erstellt von Freddy

## Erledigt (23.–30.09.2026)

1. Öffentliche Prüfung der bestehenden Live-Website (alle Hauptseiten, robots.txt) durchgeführt.
2. Bestandsaufnahme erstellt und abgelegt (GitHub `docs/bestandsaufnahme.md`, Google Drive-Ordner "Homepage").
3. Zielarchitektur mit Jan abgestimmt und festgelegt: Astro (Frontend) + Strapi Cloud (CMS) + Cloudflare Pages (Hosting) + GitHub (Code/Versionierung) + eingeschränktes Strapi-MCP-Token für Freddys Agentenzugriff.
4. GitHub-Repository "Homepage" und Google-Drive-Ordner "Homepage" als feste Ablageorte bestätigt und mit Grundgerüst befüllt (README, Bestandsaufnahme, Sitemap-Entwurf, Content-Modell-Entwurf).
5. Sitemap- und URL-Konzept mit vollständiger Redirect-Tabelle (alt → neu) entworfen, inklusive Behebung des Tippfehlers `/schulung-und-vertireb`, der kryptischen Impressum-URL und der defekten Lenksysteme-Seite.
6. Strapi-Content-Modell entworfen: 10 Content-Types (u. a. Leistung, Produkt, Schulung, Team, Referenz, Fachbeitrag, FAQ, Kontaktanfrage) mit Pflichtfeldern, die sichtbare Baukasten-Platzhalter wie auf der aktuellen Seite technisch ausschließen.
7. Rollen-/Rechte-Tabelle für das MCP-Admin-Token entworfen: Freddy kann künftig Inhalte lesen und als Entwurf anlegen/bearbeiten, aber nicht löschen oder eigenständig veröffentlichen.
8. Notiz ergänzt: Morgan prüft die Datenschutz-/DSGVO-Seite inhaltlich, sobald sie fertig vorliegt – bis dahin bleibt der bestehende Rechtstext unverändert.
9. **Entscheidung (24.09.2026):** Lenksysteme entfallen komplett als Angebot. `/lenksysteme` wird per 301 auf `/produkte` weitergeleitet; die Produktkategorie „Lenksystem" wurde aus dem Content-Modell entfernt.
10. **Zweite Domain geprüft (30.09.2026):** agridrones-europe.com wurde als weitere, von Schmidt Solutions betriebene Website identifiziert und öffentlich geprüft (WordPress, vollständig zweisprachig DE/EN, eigene Produkt-, Zubehör-, Software- und Team-Seiten). Ergebnis in `docs/bestandsaufnahme.md`, Abschnitt 9, dokumentiert.
11. **Entscheidung (30.09.2026):** schmidt-solutions.de und agridrones-europe.com bleiben getrennte Marken. schmidt-solutions.de fokussiert auf Dienstleistung/Beratung/Training, agridrones-europe.com bleibt der eigenständige Drohnen-Shop. Beide Seiten sollen künftig klar gegenseitig verlinkt werden.
12. **PIX4Dfields ins Homepagekonzept aufgenommen (30.09.2026, auf Hinweis von Ethan):** neue Produktkategorie „Software" mit eigener Seite `/produkte/software` im Sitemap-Entwurf; im Strapi-Content-Modell um das Feld „Externe Produktseite" sowie verpflichtende Felder „Quellen" und „Prüfstatus" ergänzt, damit Hersteller- und Leistungsangaben nachvollziehbar bleiben. Ausführliche Produktinformationen und Kaufberatung verbleiben bei agridrones-europe.com/pix4dfields/, um Doppelpflege zu vermeiden.

## Offen / wartet auf Jan

1. Welche Telefonnummer(n) und E-Mail-Adresse(n) sind aktuell tatsächlich gültig? (Aktuell widersprüchliche Angaben zwischen sichtbarem Text, `tel:`/`mailto:`-Linkzielen und Impressum/Datenschutztext.)
2. Gibt es weitere, aktuell nicht verlinkte Unterseiten oder Landingpages?
3. Ist vorhandenes Bildmaterial (Drohnen, Team, Einsätze) in guter Qualität vorhanden, oder muss neues Material beschafft werden?
4. Sollen bestehende Google Maps-/YouTube-/WhatsApp-Business-Einbindungen 1:1 übernommen oder datenschutzfreundlicher ersetzt werden?
5. Grundsätzliche Freigabe/Rückmeldung zu den vier neu vorgeschlagenen Seiten `/leistungen/weinbau`, `/leistungen/forst`, `/referenzen`, `/ratgeber` – sind das sinnvolle Ergänzungen oder eher nicht leistbar?
6. Konkrete Umsetzung der gegenseitigen Verlinkung zwischen schmidt-solutions.de und agridrones-europe.com (z. B. Footer-Hinweis oder Box auf der Produktübersicht) – Freddy kann einen Formulierungsvorschlag machen, sobald gewünscht.

## Blockiert

- Keine technische Blockade aktuell. Der Fortschritt bei Punkt "Astro-Grundgerüst aufsetzen" wartet bewusst auf die Antworten oben, damit nicht mit falschen Kontaktdaten oder einer unklaren Struktur gearbeitet wird.
- Google-Drive-Altversionen der Konzeptdokumente (Sitemap, Content-Modell, Bestandsaufnahme) können mit den aktuell verfügbaren Werkzeugen nicht gelöscht werden – nur neue Versionen können hochgeladen werden. Bereinigung müsste händisch durch Jan erfolgen oder wartet auf ein Werkzeug mit Löschfunktion.

## Freigabepflichtig, bevor produktiv etwas passiert

- Endgültige Sitemap/URL-Struktur (Entwurf liegt vor, inkl. PIX4Dfields-Ergänzung)
- Strapi-Content-Modell und MCP-Rechte-Tabelle (Entwurf liegt vor, inkl. PIX4Dfields-Ergänzung)
- Jeglicher veröffentlichter Inhalt auf der neuen Website
- Datenschutztext: Freigabe durch Morgan erforderlich, bevor er final übernommen wird
- Formulierung der gegenseitigen Verlinkung zwischen schmidt-solutions.de und agridrones-europe.com

## Nächste Schritte (sobald offene Punkte geklärt sind)

1. Antworten von Jan zu den verbleibenden offenen Punkten einarbeiten, Sitemap und Redirect-Tabelle final abstimmen.
2. Astro-Grundgerüst im GitHub-Repository "Homepage" aufsetzen (Ordnerstruktur, Basis-Layout, Navigation nach neuer Sitemap).
3. Cloudflare Pages Preview-Deployment einrichten, damit Jan Zwischenstände live ansehen kann, ohne dass etwas öffentlich sichtbar wird.
4. Strapi-Instanz in der Cloud aufsetzen und Content-Types gemäß Entwurf anlegen (inkl. Kategorie „Software" für PIX4Dfields).
5. Erstbefüllung mit vorhandenen Texten aus der Bestandsaufnahme (bereinigt um Platzhalter).
6. MCP-Anbindung mit eingeschränktem Admin-Token einrichten und testen.
7. Vor jedem produktiven Schritt: kurze Freigaberunde mit Jan.

## Risiken, die im Blick bleiben müssen

- SEO-Sichtbarkeitsverlust bei Livegang, falls Redirect-Tabelle nicht vollständig umgesetzt wird.
- Rechtliches Risiko, falls Datenschutztext ohne Morgans Prüfung finalisiert würde – wird bewusst vermieden.
- Datenqualität: Solange Telefonnummer/E-Mail nicht eindeutig bestätigt sind, wird nichts final in die globalen Kontaktdaten übernommen.
- Verwechslungsgefahr zwischen schmidt-solutions.de und agridrones-europe.com bei Nutzern und in Suchmaschinen, falls die gegenseitige Verlinkung/Abgrenzung nicht zeitnah sauber umgesetzt wird.
