---
name: dsgvo-checklist
description: Prueft deutsche Websites auf DSGVO, Impressum, Cookies, Fonts, Formulare, E-Commerce-Recht. Aktiviert bei Website-Builds, Audits, Deploy-Checks oder wenn Datenschutz/Impressum/Cookie/DSGVO/Rechtliches erwaehnt wird.
---

# DSGVO & Rechts-Checkliste fuer deutsche Websites

## Wann aktivieren
- Website mit deutschem Inhalt wird gebaut oder auditiert
- User erwaehnt "DSGVO", "Datenschutz", "Impressum", "Cookie", "Rechtliches", "Abmahnung"
- Bei jedem Website-Deploy oder Go-Live Check
- Bei E-Commerce/Shop-Projekten automatisch
- Wenn Formulare, Newsletter oder Tracking eingebaut werden
- NICHT bei rein englischsprachigen Projekten ohne DE-Bezug

## Prioritaeten-System
- **KRITISCH** = Abmahngefahr, sofort fixen
- **HOCH** = Rechtlich erforderlich, zeitnah fixen
- **MITTEL** = Best Practice, sollte gefixt werden
- **NIEDRIG** = Empfehlung

---

## 1. Impressum (TMG §5) — KRITISCH

Pruefe ob vorhanden und vollstaendig:
- [ ] Impressum-Seite existiert unter `/impressum` oder `/impressum.html`
- [ ] Von jeder Seite in max. 2 Klicks erreichbar (Footer-Link)
- [ ] Link-Text ist "Impressum" (nicht "Legal" oder "About")
- [ ] Vollstaendiger Name oder Firma + Rechtsform
- [ ] Postanschrift (KEIN Postfach!)
- [ ] Telefonnummer (in Deutschland Pflicht)
- [ ] E-Mail-Adresse
- [ ] Vertretungsberechtigte Person(en) bei jur. Personen
- [ ] Handelsregisternummer + Registergericht (falls eingetragen)
- [ ] USt-IdNr. (falls vorhanden)
- [ ] Verantwortlich i.S.d. §18 Abs. 2 MStV (bei redaktionellen Inhalten)
- [ ] EU-Streitschlichtungsplattform: Link auf https://ec.europa.eu/consumers/odr
- [ ] Verbraucherstreitbeilegung: Erklaerung ob Teilnahme ja/nein

**Berufsspezifisch (Aerzte, Anwaelte, Steuerberater, Architekten):**
- [ ] Berufsbezeichnung und Staat der Verleihung
- [ ] Zustaendige Kammer
- [ ] Berufsrechtliche Regelungen mit Fundstelle

## 2. Datenschutzerklaerung (DSGVO Art. 13/14) — KRITISCH

- [ ] Datenschutz-Seite existiert unter `/datenschutz`
- [ ] Im Footer von jeder Seite verlinkt
- [ ] Verantwortlicher mit vollstaendigen Kontaktdaten
- [ ] Datenschutzbeauftragter (Pflicht bei >20 Personen mit regelmaessiger Datenverarbeitung)

Fuer JEDEN eingesetzten Dienst einzeln pruefen:
- [ ] Hosting-Anbieter deklariert (Cloudflare, Vercel, Netlify, etc.)
- [ ] Kontaktformular: Zweck, Rechtsgrundlage (Art. 6 Abs. 1 lit. b), Speicherdauer
- [ ] E-Mail-Anbieter deklariert (Google Workspace, Proton, etc.)
- [ ] Analytics-Tool benannt + Rechtsgrundlage (oder "kein Tracking" explizit geschrieben)
- [ ] Cookie-Kategorien mit Zweck und Speicherdauer
- [ ] Externe Fonts: Anbieter + uebermittelte Daten (IP) + Rechtsgrundlage
- [ ] CDN/Externe Ressourcen: Anbieter + IP-Uebermittlung
- [ ] Social Media Plugins/Embeds mit Datenfluss
- [ ] Newsletter: Anbieter, Double-Opt-In, Abmeldung
- [ ] Betroffenenrechte vollstaendig: Auskunft (Art. 15), Berichtigung (Art. 16), Loeschung (Art. 17), Einschraenkung (Art. 18), Portabilitaet (Art. 20), Widerspruch (Art. 21)
- [ ] Beschwerderecht bei Aufsichtsbehoerde (Landesbeauftragter benennen)
- [ ] Drittlandtransfers: Rechtsgrundlage fuer USA etc. (Angemessenheitsbeschluss / SCCs)

## 3. Cookie-Consent (TTDSG + ePrivacy) — KRITISCH

- [ ] Kein Tracking-Code VOR Consent im HTML (auch kein Google Tag Manager)
- [ ] Cookie-Banner vorhanden wenn Tracking/Marketing eingesetzt wird
- [ ] Opt-In VOR Setzen nicht-essentieller Cookies
- [ ] "Ablehnen" gleichwertig zu "Akzeptieren" (gleiche Groesse, Farbe, Position!)
- [ ] Keine vorausgewaehlten Checkboxen
- [ ] Granulare Auswahl: Notwendig (immer aktiv), Statistik, Marketing
- [ ] Widerruf jederzeit moeglich (Link im Footer: "Cookie-Einstellungen")
- [ ] KEIN Cookie-Wall (Zugang nicht an Consent koppeln)
- [ ] Google Analytics NUR nach explizitem Consent laden
- [ ] Facebook Pixel NUR nach explizitem Consent laden
- [ ] Consent wird dokumentiert (Zeitpunkt, Umfang, Version)

Kein Banner noetig wenn:
- Nur technisch notwendige Cookies (Session, CSRF)
- Kein Analytics, kein Marketing, kein Tracking
- YouTube nur ueber youtube-nocookie.com eingebunden
→ Trotzdem in Datenschutzerklaerung erwaehnen!

## 4. Google Fonts & Externe Ressourcen — KRITISCH

- [ ] KEINE Requests an `fonts.googleapis.com` (Browser DevTools → Network pruefen!)
- [ ] Fonts als .woff2 lokal in `/public/fonts/` oder `/assets/fonts/`
- [ ] `@font-face` mit `font-display: swap` im CSS
- [ ] Keine externen CDNs fuer jQuery, Bootstrap etc. ohne Datenschutz-Hinweis
- [ ] Font Awesome: Icons als SVG inline statt CDN
- [ ] Google Maps: 2-Klick-Loesung oder Consent-Pflicht
- [ ] YouTube: `youtube-nocookie.com` statt `youtube.com`
- [ ] reCAPTCHA: Alternative (hCaptcha, Honeypot) bevorzugen

## 5. Formulare & Kontakt — HOCH

- [ ] HTTPS auf der gesamten Website (nicht nur Formular-Seiten)
- [ ] Datenschutz-Hinweis bei/neben jedem Formular
- [ ] Einwilligungs-Checkbox (NICHT vorausgewaehlt)
- [ ] Link zur Datenschutzerklaerung im Checkbox-Text
- [ ] Nur notwendige Felder (Datenminimierung)
- [ ] Newsletter: Double-Opt-In implementiert
- [ ] Newsletter: 1-Klick Abmeldung in jeder Mail
- [ ] Kein Koppelungsverbot (Newsletter nicht an Download/Dienst koppeln)
- [ ] Speicherdauer der Formulardaten in Datenschutzerklaerung angegeben

## 6. E-Commerce Zusatz-Checks — KRITISCH (wenn Shop)

Nur wenn Online-Shop / Checkout vorhanden:
- [ ] AGB vorhanden und vor Kauf einsehbar
- [ ] Widerrufsbelehrung vorhanden
- [ ] Muster-Widerrufsformular bereitgestellt
- [ ] Widerrufsfrist: 14 Tage korrekt angegeben
- [ ] Preise: Brutto inkl. MwSt. angezeigt
- [ ] "zzgl. Versandkosten" mit Link zur Versandkosten-Seite
- [ ] Grundpreisangabe bei Gewicht/Volumen-Waren (PAngV)
- [ ] Streichpreise: Niedrigster Preis der letzten 30 Tage angezeigt (Omnibus)
- [ ] Lieferzeiten angegeben
- [ ] Zahlungsarten aufgelistet
- [ ] Button-Text: "Zahlungspflichtig bestellen" (§312j BGB)
- [ ] Bestelluebersichts-Seite VOR dem letzten Klick
- [ ] Checkout-Checkbox: AGB + Widerrufsbelehrung (nicht vorausgewaehlt)
- [ ] OS-Plattform-Link: https://ec.europa.eu/consumers/odr
- [ ] Bestellbestaetigungs-Email mit Widerrufsbelehrung

## 7. Technische Sicherheit — HOCH

- [ ] HTTPS/SSL aktiv (gesamte Website)
- [ ] HTTP → HTTPS Redirect konfiguriert
- [ ] HSTS-Header gesetzt (`Strict-Transport-Security: max-age=31536000`)
- [ ] Content-Security-Policy Header
- [ ] X-Content-Type-Options: nosniff
- [ ] X-Frame-Options: DENY (oder SAMEORIGIN)
- [ ] Referrer-Policy: strict-origin-when-cross-origin

## 8. Cold-Outreach Compliance (UWG §7) — HOCH

Nur relevant wenn Kalt-Akquise per Email:
- [ ] Nur B2B (B2C Cold-Email ist verboten!)
- [ ] Sachlicher Bezug zum Geschaeft des Empfaengers
- [ ] Vollstaendiges Impressum in jeder Mail
- [ ] Opt-Out-Moeglichkeit in jeder Mail
- [ ] Herkunft der Kontaktdaten in erster Mail erwaehnen (DSGVO Art. 14)
- [ ] Opt-Out-Liste fuehren (Widerspruch = NIE MEHR kontaktieren)

---

## Output-Format

Erstelle eine Checkliste mit:

| Prioritaet | Bereich | Check | Status | Fix |
|------------|---------|-------|--------|-----|
| KRITISCH | Impressum | Telefonnummer vorhanden | OK / FEHLT | "Telefonnummer im Impressum ergaenzen" |

Sortierung: KRITISCH → HOCH → MITTEL → NIEDRIG
Bei KRITISCH-Fehlern: **Sofort fixen vor Go-Live!**
