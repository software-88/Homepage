# Strapi Content-Modell (Entwurf) – schmidt-solutions.de
Stand: 23.09.2026 · erstellt von Freddy · Status: ENTWURF, freigabepflichtig vor technischer Umsetzung

Ziel: jedes Inhaltselement hat klar benannte Pflichtfelder. Damit sind die auf der aktuellen
Website sichtbaren Platzhalter ("Slide title", "Bildtitel", "Button" ohne Ziel) im neuen
System technisch nicht mehr möglich – ein Feld ohne Inhalt bleibt leer sichtbar oder blockiert
die Veröffentlichung, es wird nie ein Platzhaltertext live angezeigt.

## 1. Globale Einstellungen (Single Type: `global-settings`)
- Firmenname
- Telefonnummer(n) (wiederholbare Komponente: Label + Nummer, z. B. "Zentrale", "Mobil")
- E-Mail-Adresse(n) (wiederholbare Komponente: Label + Adresse)
- Adresse (Straße, PLZ, Ort, Bundesland)
- Öffnungszeiten (optional)
- Social-/Messenger-Links (z. B. WhatsApp Business Nummer)
- Standard-SEO-Bild (Fallback für Open-Graph)
- Footer-Text
- Rechtlicher Verantwortlicher (Name, Anschrift) – Pflichtfeld, wird für Impressum/Datenschutz referenziert

→ Löst das aktuelle Problem widersprüchlicher Kontaktdaten auf mehreren Seiten: Es gibt nur
noch eine Quelle der Wahrheit, aus der alle Seiten die Kontaktdaten automatisch beziehen.

## 2. Leistungsseite (Collection Type: `leistung`)
| Feld | Typ | Pflicht | Hinweis |
|---|---|---|---|
| Titel | Text | ja | |
| Slug | UID | ja | aus Titel generiert, manuell überschreibbar |
| Kurzbeschreibung | Text (kurz) | ja | für Übersichtskarten |
| Zielgruppe | Text | nein | z. B. "Landwirte", "Weinbaubetriebe" |
| Einsatzbereich/Problem | Rich Text | ja | |
| Leistungsumfang | wiederholbare Komponente (Titel + Beschreibung + Icon) | ja, min. 1 Eintrag | ersetzt die alten leeren "Button"-Listen |
| Ablauf/Vorgehen | wiederholbare Komponente (Schritt-Nr. + Text) | nein | |
| Vorteile | wiederholbare Komponente (Text) | nein | |
| Region/Einsatzgebiet | Text | nein | für lokale SEO |
| Bildergalerie | Medienfeld (mehrere Bilder, je mit Pflichtfeld Alt-Text) | ja, min. 1 Bild | kein Bild ohne Alt-Text speicherbar |
| FAQ | Relation zu `faq` | nein | |
| SEO-Titel | Text | ja | |
| Meta-Beschreibung | Text (max. 160 Zeichen) | ja | |
| Call-to-Action Text | Text | ja | Standardwert: "Jetzt anfragen" |
| Übergeordnete Kategorie | Enumeration (Landwirtschaft/Weinbau/Forst/Inspektion) | ja | steuert Navigation |

## 3. Produkt (Collection Type: `produkt`)
| Feld | Typ | Pflicht |
|---|---|---|
| Produktname | Text | ja |
| Slug | UID | ja |
| Kategorie | Enumeration (Agrardrohne/Kameradrohne/Lenksystem/Zubehör) | ja |
| Kurzbeschreibung | Text | ja |
| Beschreibung | Rich Text | ja |
| Technische Daten | wiederholbare Komponente (Label + Wert) | nein |
| Bildergalerie | Medienfeld mit Alt-Text-Pflicht | ja |
| Hersteller | Text | nein |
| Verfügbarkeit | Enumeration (Verfügbar/Auf Anfrage/Nicht mehr verfügbar) | ja |
| Verknüpfte Schulung | Relation zu `schulung` | nein |
| SEO-Titel/Meta-Beschreibung | Text | ja |

## 4. Schulung (Collection Type: `schulung`)
| Feld | Typ | Pflicht |
|---|---|---|
| Titel | Text | ja |
| Slug | UID | ja |
| Zielgruppe | Text | nein |
| Inhalte | wiederholbare Komponente (Titel + Beschreibung) | ja |
| Dauer/Format | Text | nein |
| Voraussetzungen | Rich Text | nein |
| Verknüpfte Produkte | Relation zu `produkt` | nein |
| SEO-Titel/Meta-Beschreibung | Text | ja |

## 5. Team (Collection Type: `team-mitglied`)
| Feld | Typ | Pflicht |
|---|---|---|
| Name | Text | ja |
| Rolle/Funktion | Text | ja |
| Kurzprofil | Rich Text | ja |
| Foto | Medienfeld mit Alt-Text-Pflicht | ja |
| Reihenfolge | Zahl | nein |

## 6. Referenz (Collection Type: `referenz`) – NEU, siehe Sitemap-Vorschlag
| Feld | Typ | Pflicht |
|---|---|---|
| Titel/Projektname | Text | ja |
| Kunde/Region | Text | nein (Anonymisierung möglich) |
| Leistungsart | Relation zu `leistung` | ja |
| Beschreibung | Rich Text | ja |
| Ergebnis/Nutzen | Text | nein |
| Bildergalerie | Medienfeld mit Alt-Text-Pflicht | nein |
| Datum | Datum | nein |

## 7. Fachbeitrag (Collection Type: `fachbeitrag`) – NEU, siehe Sitemap-Vorschlag
| Feld | Typ | Pflicht |
|---|---|---|
| Titel | Text | ja |
| Slug | UID | ja |
| Teaser | Text | ja |
| Inhalt | Rich Text | ja |
| Titelbild | Medienfeld mit Alt-Text-Pflicht | ja |
| Autor | Relation zu `team-mitglied` | nein |
| Veröffentlichungsdatum | Datum | ja |
| Verknüpfte Leistung | Relation zu `leistung` | nein |
| SEO-Titel/Meta-Beschreibung | Text | ja |

## 8. FAQ (Collection Type: `faq`)
| Feld | Typ | Pflicht |
|---|---|---|
| Frage | Text | ja |
| Antwort | Rich Text | ja |
| Kategorie | Relation zu `leistung` | nein |

## 9. Rechtliche Seiten (Single Types: `impressum`, `datenschutz`)
- Freitext-Rich-Text-Feld für den jeweiligen rechtlichen Inhalt
- Letzte-Änderung-Datum (automatisch)
- **Wichtig:** Der Datenschutz-Inhalt wird inhaltlich erst nach Prüfung durch Morgan final freigegeben.
  Bis dahin wird der bestehende Text unverändert als Ausgangsbasis eingepflegt.

## 10. Kontaktanfrage (Collection Type: `kontaktanfrage`, nur intern, nicht öffentlich abrufbar)
| Feld | Typ | Pflicht |
|---|---|---|
| Name | Text | ja |
| E-Mail | Text | ja |
| Telefon | Text | nein |
| Anliegen/Nachricht | Rich Text | ja |
| Bezug (Leistung/Produkt) | Relation | nein |
| Status | Enumeration (Neu/In Bearbeitung/Erledigt) | ja, Standard "Neu" |
| Eingegangen am | Datum/Zeit (automatisch) | ja |

→ Erfasst Website-Anfragen strukturiert, wie in der Rollenbeschreibung gefordert. Freddy erfasst
und dokumentiert diese Einträge, beantwortet sie aber nicht eigenständig und qualifiziert nicht.
Die spätere Übergabe an den Microsoft-Planner-Workflow wird erst mit Ethan final definiert;
dieses Feld-Set ist bewusst schlank gehalten, um später ohne Bruch erweiterbar zu sein.

## 11. Rollen/Berechtigungen für den Agentenzugriff (MCP-Token für Freddy)

Empfohlene Rechte für das Admin-Token, das Freddy nutzt:

| Content-Type | Lesen | Erstellen | Bearbeiten | Löschen | Veröffentlichen |
|---|---|---|---|---|---|
| leistung | ja | ja (als Entwurf) | ja | nein | nein |
| produkt | ja | ja (als Entwurf) | ja | nein | nein |
| schulung | ja | ja (als Entwurf) | ja | nein | nein |
| team-mitglied | ja | nein | nein | nein | nein |
| referenz | ja | ja (als Entwurf) | ja | nein | nein |
| fachbeitrag | ja | ja (als Entwurf) | ja | nein | nein |
| faq | ja | ja (als Entwurf) | ja | nein | nein |
| impressum/datenschutz | ja | nein | nein | nein | nein |
| kontaktanfrage | ja | nein | ja (nur Status) | nein | nein |
| global-settings | ja | nein | nein | nein | nein |

Diese Tabelle ist die Blaupause für die spätere Admin-Token-Konfiguration in Strapi und muss
vor Inbetriebnahme der MCP-Anbindung so oder in angepasster Form von Jan bestätigt werden.
