# Sitemap & URL-Konzept – schmidt-solutions.de (Entwurf)
Stand: 30.09.2026 · erstellt von Freddy · Status: ENTWURF, freigabepflichtig vor Umsetzung

Die vier ergänzten Seiten und die genannten Kontaktdaten/Integrationen sind von Jan am 30.09.2026 bestätigt. Die technische Umsetzung und Veröffentlichung bleiben freigabepflichtig. Die Datenschutzerklärung wird vor finaler Übernahme durch Morgan geprüft.

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
/leistungen/weinbau                 Weinbau (Steillagen) – von Jan am 30.09.2026 freigegeben
/leistungen/forst                   Forstwirtschaft – von Jan am 30.09.2026 freigegeben
/leistungen/inspektionen            Gebäude-/PV-Anlagen-Inspektion, Thermografie
/schulungen                         Schulung & Vertrieb (bereinigter Slug, ersetzt /schulung-und-vertireb)
/produkte                           Drohnen, Software & Zubehör (Übersicht)
/produkte/agrardrohnen              Sprüh-/Streudrohnen (z. B. EAVISION J100)
/produkte/kameradrohnen             Kamera-/Multispektraldrohnen (z. B. DJI Mavic 3M)
/produkte/software                  Software für Drohnenauswertung (PIX4Dfields), schlanker Überblick mit Link zu Agridrones Europe
/ueber-uns                          Team & Unternehmen (ohne Umlaut in der URL)
/referenzen                         Projekte/Referenzen – von Jan am 30.09.2026 freigegeben
/ratgeber                           Fachbeiträge/Blog – von Jan am 30.09.2026 freigegeben
/kontakt                            Nur Kontakt (Formular, Telefon, E-Mail, Anfahrt)
/datenschutz                        Eigenständige Datenschutzseite (aus /kontakt herausgelöst)
/impressum                          Bereinigter Slug (ersetzt /impressum7fff571f)
```

**Hinweis:** Lenksysteme wurden als eigenständiger Bereich vollständig gestrichen (Entscheidung vom 24.09.2026) – siehe Abschnitt 3 und 4.

### PIX4Dfields im Produktkonzept
PIX4Dfields wird auf schmidt-solutions.de als Softwarelösung für die Auswertung von Drohnen- und Felddaten aufgenommen. Die Seite `/produkte/software` bleibt bewusst kompakt: Sie erklärt den Anwendungsbezug und führt für ausführliche Produktinformationen, Verfügbarkeit und Kaufberatung zu **agridrones-europe.com/pix4dfields/**. Dadurch bleibt die Trennung beider Websites erhalten und Produktinhalte werden nicht doppelt gepflegt. Hersteller- und Leistungsangaben müssen vor Veröffentlichung quellenbezogen geprüft werden.

### Warum aus `/kontakt` zwei Seiten werden
Aktuell sind Kontakt und die vollständige Datenschutzerklärung auf einer URL zusammengefasst. Das ist weder für Nutzer noch für Suchmaschinen ideal: Der Kontaktbereich soll kurz und handlungsorientiert sein (Formular, Telefon, Karte), während die Datenschutzerklärung ein eigenständiges, rechtlich klar auffindbares Dokument braucht. Diese Trennung steht unter Vorbehalt der Prüfung durch Morgan.

### Von Jan freigegebene Ergänzungen
- `/leistungen/weinbau` und `/leistungen/forst`: eigenständige Leistungsseiten zu den bereits genannten Einsatzfeldern Weinbau und Forst.
- `/referenzen`: Referenzprojekte als Vertrauens- und Nachweisbereich; konkrete Inhalte sind vor Veröffentlichung zu belegen und freizugeben.
- `/ratgeber`: Fachbeiträge zu passenden Beratungs- und Trainingsthemen; Inhalte werden vor Veröffentlichung geprüft und freigegeben.

Die Seiten sind als Konzeptumfang freigegeben; konkrete Texte, Referenzen und deren Veröffentlichung benötigen weiterhin die übliche Inhaltsfreigabe.

## 3. Redirect-Tabelle (alt → neu)

| Alte URL | Neue URL | Redirect-Typ |
|---|---|---|
| `/` | `/` | unverändert |
| `/leistungen` | `/leistungen` | unverändert |
| `/leistungen/landwirtschaft` | `/leistungen/landwirtschaft` | unverändert |
| `/leistungen#Inspektionen` | `/leistungen/inspektionen` | 301, aus Anker wird eigene Seite |
| `/schulung-und-vertireb` | `/schulungen` | 301 (behebt Tippfehler) |
| `/produkte` | `/produkte` | unverändert (wird Übersichtsseite) |
| `/lenksysteme` | `/produkte` | 301 (Lenksysteme entfallen komplett als Angebot, Weiterleitung auf Produktübersicht) |
| `/über-uns` | `/ueber-uns` | 301 (Umlaut-URL bereinigt) |
| `/kontakt` | `/kontakt` | unverändert (wird schlanker) |
| `/kontakt#datenschutz` | `/datenschutz` | 301, eigenständige Seite |
| `/impressum7fff571f` | `/impressum` | 301 (technische URL bereinigt) |

**Wichtig:** Diese Tabelle ist die Blaupause für die spätere technische Umsetzung der 301-Weiterleitungen. Ohne sie verliert die Website bei jedem indexierten Suchergebnis Sichtbarkeit. Sie darf beim Livegang nicht vergessen werden.

## 4. Status der offenen Punkte (30.09.2026)

- **Geklärt (24.09.2026):** Lenksysteme fallen komplett aus dem Angebot weg. `/lenksysteme` wird per 301 auf `/produkte` weitergeleitet, keine eigene Nachfolgeseite. Die Kategorie „Lenksystem" entfällt entsprechend auch aus dem Produkt-Content-Modell (siehe `02_Strapi_Content_Modell.md`).
- **Geklärt (30.09.2026):** Weinbau, Forst, Referenzen und Ratgeber sind freigegeben und werden alle vier umgesetzt (siehe oben).
- **Geklärt (30.09.2026):** Telefonnummer(n) (`0172/1644944` und `0162/2391173`) und E-Mail (`drohne@schmidt-solutions.de`) sind bestätigt und fließen unverändert in die globalen Kontaktdaten ein.
- **Geklärt (30.09.2026):** Keine weiteren, unverlinkten Unterseiten vorhanden.
- **Geklärt (30.09.2026):** Bildmaterial ist vorhanden, kein Neubeschaffungsbedarf für den Start.
- **Geklärt (30.09.2026):** Google Maps/YouTube/WhatsApp Business werden 1:1 übernommen wie bisher.

Damit sind alle in diesem Dokument offenen Punkte geklärt. Verbleibend: die konkrete Formulierung/Platzierung der gegenseitigen Verlinkung zwischen schmidt-solutions.de und agridrones-europe.com (siehe Bestandsaufnahme, Abschnitt 9) – Freddy erstellt hierzu einen separaten Vorschlag.
