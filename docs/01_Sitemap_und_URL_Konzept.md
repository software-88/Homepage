# Sitemap & URL-Konzept – schmidt-solutions.de (Entwurf)
Stand: 23.09.2026 · erstellt von Freddy · Status: ENTWURF, freigabepflichtig vor Umsetzung

Dieses Dokument ist ein Vorschlag. Es ersetzt nicht die Antworten auf die offenen Fragen aus der Bestandsaufnahme (Telefonnummern, `/lenksysteme`, Bildmaterial, Maps/YouTube/WhatsApp, DSGVO-Prüfung durch Morgan). Vor Umsetzung: Freigabe durch Jan.

## 1. Leitprinzipien für die neue URL-Struktur

- Sprechende, fehlerfreie deutsche URLs ohne Umlaute (bessere Kompatibilität, keine Wiederholung des `/über-uns`-Problems)
- Keine zufälligen/kryptischen Suffixe wie bei `/impressum7fff571f`
- Flache Struktur wo möglich, maximal zwei Ebenen tief
- Leistungsseiten unter einem gemeinsamen `/leistungen/...`-Pfad statt verstreuter Einzelseiten
- Vorbereitung auf Mehrsprachigkeit: URLs so gewählt, dass später `/en/...` als Sprachpräfix ergänzt werden kann, ohne die deutschen URLs zu ändern
- Jede alte URL bekommt eine 301-Weiterleitung auf die neue Ziel-URL (siehe Abschnitt 3)

## 2. Neue Seitenstruktur (Vorschlag)

```
/                                   Startseite
/leistungen                         Leistungsübersicht
/leistungen/landwirtschaft          Landwirtschaftliche Dienstleistungen
/leistungen/weinbau                 Weinbau (Steillagen) – NEU als eigene Seite vorgeschlagen
/leistungen/forst                   Forstwirtschaft – NEU als eigene Seite vorgeschlagen
/leistungen/inspektionen            Gebäude-/PV-Anlagen-Inspektion, Thermografie
/schulungen                         Schulung & Vertrieb (bereinigter Slug, ersetzt /schulung-und-vertireb)
/produkte                           Drohnen & Zubehör (Übersicht)
/produkte/agrardrohnen              Sprüh-/Streudrohnen (z. B. EAVISION J100)
/produkte/kameradrohnen             Kamera-/Multispektraldrohnen (z. B. DJI Mavic 3M)
/produkte/lenksysteme               Lenksysteme (ersetzt defekte Seite /lenksysteme)
/ueber-uns                          Team & Unternehmen (ohne Umlaut in der URL)
/referenzen                         Projekte/Referenzen – NEU, aktuell nicht vorhanden
/ratgeber                           Fachbeiträge/Blog – NEU, für SEO-Content
/kontakt                            Nur Kontakt (Formular, Telefon, E-Mail, Anfahrt)
/datenschutz                        Eigenständige Datenschutzseite (aus /kontakt herausgelöst)
/impressum                          Bereinigter Slug (ersetzt /impressum7fff571f)
```

### Warum aus `/kontakt` zwei Seiten werden
Aktuell sind Kontakt und die vollständige Datenschutzerklärung auf einer URL zusammengefasst. Das ist weder für Nutzer noch für Suchmaschinen ideal: Der Kontaktbereich soll kurz und handlungsorientiert sein (Formular, Telefon, Karte), während die Datenschutzerklärung ein eigenständiges, rechtlich klar auffindbares Dokument braucht. Diese Trennung steht unter Vorbehalt der Prüfung durch Morgan.

### Neu vorgeschlagene Seiten (nicht in der bisherigen Website vorhanden)
- `/leistungen/weinbau` und `/leistungen/forst`: Die Startseite nennt "Landwirtschaft, Weinbau und Forst" prominent, aber es gibt aktuell keine eigenen Landingpages dafür. Das ist SEO-Potenzial, das ungenutzt bleibt.
- `/referenzen`: Aktuell keine Referenzen/Case Studies auf der Website sichtbar. Für Vertrauen und lokale Auffindbarkeit ("Agrardrohnen Baden-Württemberg") sehr wirksam.
- `/ratgeber`: Raum für Fachbeiträge (z. B. "Wann lohnt sich Drohnensaat?", "Eichenprozessionsspinner erkennen"). Wichtig für organisches Wachstum jenseits der Leistungsseiten selbst.

Diese drei sind **Vorschläge**, keine Entscheidung – bitte im Team (ggf. mit Ethan) einmal grundsätzlich abstimmen, ob und wann Referenzen/Ratgeber-Inhalte realistisch gepflegt werden können.

## 3. Redirect-Tabelle (alt → neu)

| Alte URL | Neue URL | Redirect-Typ |
|---|---|---|
| `/` | `/` | unverändert |
| `/leistungen` | `/leistungen` | unverändert |
| `/leistungen/landwirtschaft` | `/leistungen/landwirtschaft` | unverändert |
| `/leistungen#Inspektionen` | `/leistungen/inspektionen` | 301, aus Anker wird eigene Seite |
| `/schulung-und-vertireb` | `/schulungen` | 301 (behebt Tippfehler) |
| `/produkte` | `/produkte` | unverändert (wird Übersichtsseite) |
| `/lenksysteme` | `/produkte/lenksysteme` | 301 (ersetzt defekte Seite) |
| `/über-uns` | `/ueber-uns` | 301 (Umlaut-URL bereinigt) |
| `/kontakt` | `/kontakt` | unverändert (wird schlanker) |
| `/kontakt#datenschutz` | `/datenschutz` | 301, eigenständige Seite |
| `/impressum7fff571f` | `/impressum` | 301 (technische URL bereinigt) |

**Wichtig:** Diese Tabelle ist die Blaupause für die spätere technische Umsetzung der 301-Weiterleitungen. Ohne sie verliert die Website bei jedem indexierten Suchergebnis Sichtbarkeit. Sie darf beim Livegang nicht vergessen werden.

## 4. Noch offen / abhängig von Jans Antworten

- Ob `/produkte/lenksysteme` inhaltlich befüllt werden kann, hängt davon ab, ob die Lenksysteme weiterhin Teil des Angebots sind (siehe offene Frage zu `/lenksysteme`-Fehler).
- Die genaue Positionierung von Weinbau/Forst als eigene Seiten oder als Abschnitte innerhalb von `/leistungen/landwirtschaft` sollte final mit Jan abgestimmt werden.
- `/referenzen` und `/ratgeber` sind bewusst als Vorschlag markiert und noch nicht verbindlich eingeplant.
