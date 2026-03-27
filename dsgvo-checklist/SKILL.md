---
name: dsgvo-checklist
description: Prueft deutsche Websites auf DSGVO, Impressum, Cookies, E-Commerce-Recht. Aktiviert bei Website-Builds, Audits oder wenn Datenschutz/Impressum/Cookie/DSGVO erwaehnt wird.
---

# DSGVO & Rechts-Checkliste fuer deutsche Websites

## Wann aktivieren
- Website mit deutschem Inhalt wird gebaut oder auditiert
- User erwaehnt "DSGVO", "Datenschutz", "Impressum", "Cookie", "Rechtliches"
- Bei jedem Website-Deploy oder Go-Live Check
- Bei E-Commerce/Shop-Projekten automatisch

## Pflicht-Checks (jede deutsche Website)

### 1. Impressum (TMG §5)
Pruefe ob vorhanden und vollstaendig:
- Impressum-Seite von jeder Seite erreichbar (max. 2 Klicks)
- Vollstaendiger Name oder Firma + Rechtsform
- Postanschrift (kein Postfach)
- Kontaktweg (Telefon oder Kontaktformular mit schneller Antwort)
- E-Mail-Adresse
- Vertretungsberechtigte Person(en)
- Handelsregisternummer + Gericht (falls eingetragen)
- USt-IdNr. (falls vorhanden)

### 2. Datenschutzerklaerung (DSGVO Art. 13/14)
Pruefe ob vorhanden und alle Pflichtangaben enthalten:
- Verantwortlicher mit vollstaendigen Kontaktdaten
- Zweck + Rechtsgrundlage JEDER Datenverarbeitung
- Speicherdauer oder Loeschkriterien
- Betroffenenrechte vollstaendig aufgezaehlt
- Beschwerderecht bei Aufsichtsbehoerde
- Drittlandtransfers mit Rechtsgrundlage (besonders USA)

### 3. Cookie-Consent (TTDSG + ePrivacy)
Pruefe das Cookie-Banner:
- Opt-In VOR Setzen nicht-essentieller Cookies
- "Ablehnen" gleichwertig zu "Akzeptieren" (gleiche Groesse, Farbe, Position)
- Keine vorausgewaehlten Checkboxen
- Granulare Auswahl moeglich
- Widerruf jederzeit moeglich (Link im Footer)
- Google Analytics / FB Pixel NUR nach explizitem Consent

### 4. Externe Ressourcen
- Google Fonts MUSS lokal eingebunden sein (nicht von googleapis.com laden)
- Google Maps: 2-Klick-Loesung oder Consent-Pflicht
- YouTube: Erweiterter Datenschutz-Modus (`youtube-nocookie.com`)
- Keine externen CDNs ohne Datenschutz-Hinweis

### 5. Formulare
- HTTPS Pflicht (gesamte Website)
- Datenschutz-Hinweis bei jedem Formular
- Einwilligungs-Checkbox (nicht vorausgewaehlt)
- Newsletter: Double-Opt-In Pflicht

## E-Commerce Zusatz-Checks
Nur wenn Online-Shop vorhanden:
- AGB vorhanden und vor Kauf einsehbar
- Widerrufsbelehrung + Muster-Widerrufsformular
- Preise inkl. MwSt. + Versandkosten sichtbar
- Button: "Zahlungspflichtig bestellen"
- OS-Plattform-Link (EU-Streitbeilegung)
- Bestelluebersicht vor Kaufabschluss

## Output
Erstelle eine Checkliste mit:
- Status pro Punkt (OK / FEHLT / WARNUNG)
- Konkrete Fix-Anweisung fuer jeden fehlenden Punkt
- Prioritaet (Kritisch = Abmahngefahr / Wichtig / Empfohlen)
