# Schmidt Solutions – Website Relaunch

Neue Website für https://schmidt-solutions.de
Betreut von Freddy (Website/SEO) in Abstimmung mit Jan Schmidt.

## Zielarchitektur

- **Frontend:** Astro, gehostet auf Cloudflare Pages
- **CMS:** Strapi Cloud (managed)
- **Code/Versionierung:** dieses GitHub-Repository
- **Agentenzugriff:** Strapi MCP-Server mit eingeschränktem Admin-Token
  (nur Lesen/Entwurf/Bearbeiten, kein Löschen, keine eigenständige Veröffentlichung)
- **Domain/E-Mail:** vorerst weiter bei IONOS
- **Material/Dokumente:** Google Drive-Ordner "Homepage" (parallel zu diesem Repo)

## Status

Aktuell in Bestandsaufnahme-Phase. Die bestehende Live-Website läuft noch auf dem
IONOS-Baukasten und wird schrittweise abgelöst, ohne dass die aktuelle Website
vorzeitig abgeschaltet wird.

Offene Punkte vor dem eigentlichen Aufbau sind im Dokument
`Bestandsaufnahme_schmidt-solutions.md` (im Drive-Ordner "Homepage" und im Chat)
festgehalten, u. a.:

- gültige Telefonnummer(n) und E-Mail-Adresse(n)
- Status der defekten Unterseite `/lenksysteme`
- vorhandenes Bildmaterial
- Umgang mit Google Maps / YouTube / WhatsApp Business Einbindungen
- spätere DSGVO-Prüfung der Datenschutzseite durch Morgan

## Geplante Repo-Struktur (wird schrittweise angelegt)

```
/
├── src/
│   ├── pages/         Astro-Seiten (Routing)
│   ├── layouts/        gemeinsame Seitenlayouts
│   ├── components/     wiederverwendbare UI-Bausteine
│   └── content/        lokale Inhalte, sofern nicht aus Strapi geladen
├── public/              statische Dateien (Favicon, robots.txt, etc.)
├── docs/                Planungsdokumente (Sitemap, Redirect-Tabelle, Content-Modell)
└── README.md
```

## Nächste Schritte

1. Offene Fragen aus der Bestandsaufnahme klären (Jan)
2. Neue Informationsarchitektur (Sitemap + Redirect-Tabelle alt → neu) entwerfen
3. Strapi-Content-Types modellieren
4. Astro-Grundgerüst aufsetzen
5. Cloudflare Pages Preview-Deployment einrichten
6. Freigaberunde vor jeder inhaltlichen Veröffentlichung

Wesentliche inhaltliche, strukturelle oder veröffentlichungsrelevante Änderungen
werden vor Umsetzung mit Jan (und bei strategischen Fragen mit Ethan) abgestimmt.
