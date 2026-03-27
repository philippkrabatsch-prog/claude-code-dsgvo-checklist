# Claude Code DSGVO & Rechts-Checkliste

Skill fuer [Claude Code](https://docs.anthropic.com/en/docs/claude-code) — prueft deutsche Websites auf DSGVO, Impressum, Cookies und rechtliche Pflichten.

Aktiviert sich automatisch wenn du eine Website baust oder auditierst.

---

## Was wird geprueft

### Impressum (TMG §5)
- [ ] Impressum-Seite vorhanden und von jeder Seite erreichbar
- [ ] Vollstaendiger Name / Firma
- [ ] Postanschrift (kein Postfach)
- [ ] Telefon oder schneller Kontaktweg
- [ ] E-Mail-Adresse
- [ ] Rechtsform und Vertretungsberechtigte
- [ ] Handelsregisternummer + Registergericht (falls vorhanden)
- [ ] USt-IdNr. (falls vorhanden)
- [ ] Berufsrechtliche Angaben (bei reglementierten Berufen)

### Datenschutzerklaerung (DSGVO Art. 13/14)
- [ ] Datenschutz-Seite vorhanden und verlinkt
- [ ] Verantwortlicher mit Kontaktdaten
- [ ] Datenschutzbeauftragter (falls noetig: >20 Personen mit Datenverarbeitung)
- [ ] Zweck und Rechtsgrundlage jeder Datenverarbeitung
- [ ] Empfaenger / Kategorien von Empfaengern
- [ ] Speicherdauer oder Kriterien fuer Loeschung
- [ ] Betroffenenrechte (Auskunft, Loeschung, Widerspruch, Portabilitaet)
- [ ] Beschwerderecht bei Aufsichtsbehoerde
- [ ] Drittlandtransfers (USA, etc.) mit Rechtsgrundlage

### Cookie-Consent (ePrivacy + TTDSG)
- [ ] Cookie-Banner vorhanden
- [ ] Opt-In VOR Setzen nicht-essentieller Cookies
- [ ] Keine vorausgewaehlten Checkboxen
- [ ] "Ablehnen" genauso prominent wie "Akzeptieren"
- [ ] Granulare Auswahl moeglich (Kategorien)
- [ ] Consent-Widerruf jederzeit moeglich
- [ ] Kein Cookie-Wall (Zugang nicht an Consent geknuepft)
- [ ] Google Analytics / Facebook Pixel nur nach Consent
- [ ] Consent-Dokumentation (wann, was, wie)

### Schriftarten & Externe Ressourcen
- [ ] Google Fonts LOKAL eingebunden (nicht von googleapis.com)
- [ ] Keine externen CDNs ohne Consent (jQuery, Bootstrap von CDN)
- [ ] Google Maps nur nach Consent oder mit 2-Klick-Loesung
- [ ] YouTube-Videos im erweiterten Datenschutz-Modus
- [ ] Externe Schriften: Datenschutzerklaerung erweitert

### Formulare & Kontakt
- [ ] SSL/TLS-Verschluesselung (HTTPS)
- [ ] Hinweis auf Datenverarbeitung bei Kontaktformularen
- [ ] Checkbox fuer Datenschutz-Einwilligung (nicht vorausgewaehlt)
- [ ] Link zur Datenschutzerklaerung im/am Formular
- [ ] Newsletter: Double-Opt-In Verfahren
- [ ] Kein Koppelungsverbot-Verstoss (Dienst nicht an Newsletter geknuepft)

### E-Commerce Zusaetzlich (falls Online-Shop)
- [ ] AGB vorhanden und vor Kauf einsehbar
- [ ] Widerrufsbelehrung mit Muster-Widerrufsformular
- [ ] Widerrufsfrist korrekt (14 Tage)
- [ ] Preise mit MwSt. und Versandkosten-Hinweis
- [ ] Grundpreisangabe (bei Waren nach Gewicht/Volumen)
- [ ] Lieferzeiten angegeben
- [ ] Zahlungsarten aufgelistet
- [ ] Button-Beschriftung: "Zahlungspflichtig bestellen" (nicht "Kaufen")
- [ ] OS-Plattform-Link (EU Online-Streitbeilegung)
- [ ] Bestelluebersichts-Seite vor Kaufabschluss
- [ ] Bestellbestaetigungs-Email

---

## Installation

```bash
cp -r dsgvo-checklist ~/.claude/skills/
```

## Wann aktiviert sich der Skill

- Beim Bauen einer Website mit deutschem Inhalt
- Bei Website-Audits und Reviews
- Wenn du "DSGVO", "Datenschutz", "Impressum" oder "Cookie" erwaehnt
- Bei E-Commerce/Shop-Projekten automatisch die Shop-Checks

## Rechtshinweis

Diese Checkliste ersetzt keine Rechtsberatung. Sie basiert auf dem Stand Maerz 2026 und deckt die gaengigsten Anforderungen ab. Bei Unsicherheiten einen Fachanwalt fuer IT-Recht konsultieren.

---

## Lizenz

MIT
