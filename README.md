# Claude Code DSGVO & Rechts-Checkliste

Umfassender Skill fuer [Claude Code](https://docs.anthropic.com/en/docs/claude-code) — prueft deutsche Websites automatisch auf DSGVO, Impressum, Cookies, Schriftarten, Formulare und E-Commerce-Recht.

Aktiviert sich automatisch wenn du eine Website baust, auditierst oder deployest.

---

## Inhaltsverzeichnis

- [Installation](#installation)
- [Impressum (TMG §5)](#1-impressum-tmg-5)
- [Datenschutzerklaerung (DSGVO)](#2-datenschutzerklaerung-dsgvo-art-1314)
- [Cookie-Consent (TTDSG)](#3-cookie-consent-ttdsg--eprivacy)
- [Google Fonts & Externe Ressourcen](#4-google-fonts--externe-ressourcen)
- [Formulare & Kontakt](#5-formulare--kontakt)
- [E-Commerce / Online-Shop](#6-e-commerce--online-shop)
- [Cold-Outreach & Email-Marketing](#7-cold-outreach--email-marketing-uwg-7)
- [Technische Sicherheit](#8-technische-sicherheit)
- [Haeufige Abmahngefahr](#9-haeufige-abmahngruende-priorisiert)

---

## Installation

```bash
cp -r dsgvo-checklist ~/.claude/skills/
```

Der Skill aktiviert sich automatisch bei:
- Website-Builds mit deutschem Inhalt
- Audits und Reviews
- Keywords: "DSGVO", "Datenschutz", "Impressum", "Cookie", "Rechtliches"
- E-Commerce/Shop-Projekten

---

## 1. Impressum (TMG §5)

Jede geschaeftliche Website in Deutschland braucht ein Impressum. Verstoss = Abmahnung.

### Pflichtangaben

| Angabe | Pflicht | Beispiel |
|--------|---------|---------|
| Vollstaendiger Name | Immer | Max Mustermann |
| Rechtsform | Bei Gesellschaften | GmbH, UG, GbR, e.K. |
| Postanschrift | Immer (kein Postfach!) | Musterstr. 1, 80331 Muenchen |
| Telefonnummer | Immer (DE) | +49 89 1234567 |
| E-Mail-Adresse | Immer | info@example.de |
| USt-IdNr. | Wenn vorhanden | DE123456789 |
| Handelsregister | Wenn eingetragen | HRB 12345, AG Muenchen |
| Vertretungsberechtigte | Bei jur. Personen | Geschaeftsfuehrer: Max Mustermann |
| Verantwortlich (MStV §18) | Bei redakt. Inhalten | V.i.S.d.P.: Max Mustermann |
| EU-Streitschlichtung | Immer | Link auf ec.europa.eu/consumers/odr |
| Verbraucherstreitbeilegung | Immer | Teilnahme-Erklaerung (ja/nein) |

### Technische Anforderungen
- Von **jeder Seite** in max. 2 Klicks erreichbar (Footer-Link)
- Bezeichnung: "Impressum" (nicht "Legal", "About", "Kontakt")
- Maschinenlesbar (kein Bild, kein PDF)

### HTML-Beispiel

```html
<footer>
  <a href="/impressum">Impressum</a>
  <a href="/datenschutz">Datenschutz</a>
</footer>
```

---

## 2. Datenschutzerklaerung (DSGVO Art. 13/14)

### Pflichtangaben

Fuer **jeden Dienst** der Daten verarbeitet muss einzeln aufgefuehrt werden:

| Abschnitt | Inhalt |
|-----------|--------|
| Verantwortlicher | Name, Adresse, E-Mail, Telefon |
| Datenschutzbeauftragter | Nur Pflicht bei >20 Personen die regelmaessig Daten verarbeiten |
| Hosting | Anbieter, Standort, Rechtsgrundlage (Art. 6 Abs. 1 lit. f) |
| Kontaktformular | Zweck, Rechtsgrundlage (Art. 6 Abs. 1 lit. b), Speicherdauer |
| E-Mail-Kontakt | Anbieter (Google Workspace, Proton, etc.), Zweck |
| Analytics | Tool benennen, Rechtsgrundlage (Einwilligung Art. 6 Abs. 1 lit. a) |
| Cookies | Kategorien, Zweck, Speicherdauer, Opt-Out |
| Externe Fonts | Anbieter, uebermittelte Daten (IP), Rechtsgrundlage |
| Social Media | Plugins, Embeds, Share-Buttons mit Datenfluss |
| CDN/Externe Ressourcen | Anbieter, IP-Uebermittlung |
| Newsletter | Double-Opt-In, Anbieter, Abmeldemoeglichkeit |
| Betroffenenrechte | Art. 15-21 DSGVO (Auskunft, Loeschung, Widerspruch, Portabilitaet) |
| Aufsichtsbehoerde | Zustaendiger Landesbeauftragter |
| Drittlandtransfer | Rechtsgrundlage fuer USA etc. (Angemessenheitsbeschluss/SCCs) |

### Rechtsgrundlagen-Referenz

| Rechtsgrundlage | Wann |
|----------------|------|
| Art. 6 Abs. 1 lit. a | Einwilligung (Cookies, Newsletter, Marketing) |
| Art. 6 Abs. 1 lit. b | Vertragserfuellung (Bestellprozess, Kontaktanfrage) |
| Art. 6 Abs. 1 lit. c | Rechtliche Verpflichtung (Rechnungsaufbewahrung) |
| Art. 6 Abs. 1 lit. f | Berechtigtes Interesse (Hosting, Sicherheit, Statistik) |

---

## 3. Cookie-Consent (TTDSG + ePrivacy)

### Wann ist ein Banner Pflicht?

| Situation | Banner noetig? |
|-----------|---------------|
| Reine Info-Website ohne Tracking | Nein (nur Datenschutz-Hinweis) |
| Google Analytics / Plausible | Ja (Opt-In vor dem Laden!) |
| Facebook Pixel / Marketing | Ja |
| YouTube-Embeds (normal) | Ja (IP-Uebermittlung) |
| YouTube-nocookie Embeds | Nein (aber Datenschutz-Hinweis) |
| Google Maps Embed | Ja (2-Klick oder Consent) |
| Nur technisch notwendige Cookies | Nein |

### Banner-Anforderungen

- **Opt-In VOR Setzen** nicht-essentieller Cookies
- **"Ablehnen" gleichwertig** zu "Akzeptieren" (gleiche Groesse, Farbe, Position)
- **Keine vorausgewaehlten** Checkboxen
- **Granulare Auswahl** moeglich (Notwendig / Statistik / Marketing)
- **Widerruf jederzeit** moeglich (Link im Footer: "Cookie-Einstellungen")
- **Kein Cookie-Wall** (Zugang nicht an Consent koppeln)
- **Consent dokumentieren** (Zeitpunkt, Umfang, Version)

### Code-Beispiel: Minimaler Consent-Check

```javascript
// Cookies NUR setzen wenn Consent vorliegt
function loadAnalytics() {
    if (localStorage.getItem('cookie-consent-analytics') === 'true') {
        // Google Analytics laden
        const script = document.createElement('script');
        script.src = 'https://www.googletagmanager.com/gtag/js?id=G-XXXXXXX';
        document.head.appendChild(script);
    }
}

// NICHT so (Verstoss!):
// <script src="https://www.googletagmanager.com/gtag/js"> direkt im HTML
```

---

## 4. Google Fonts & Externe Ressourcen

### Google Fonts: IMMER LOKAL

Seit dem LG-Muenchen-Urteil (Jan 2022) ist das Laden von Google Fonts ueber `fonts.googleapis.com` ein DSGVO-Verstoss (IP-Uebermittlung an Google ohne Einwilligung). Schadenersatz: 100 EUR pro Besucher.

**FALSCH (Abmahngefahr!):**
```html
<link href="https://fonts.googleapis.com/css2?family=Inter" rel="stylesheet">
```

**RICHTIG (lokal eingebunden):**
```css
@font-face {
    font-family: 'Inter';
    src: url('/fonts/inter-variable.woff2') format('woff2');
    font-display: swap;
    font-weight: 100 900;
}
```

### Setup-Anleitung: Fonts lokal einbinden

```bash
# 1. Font herunterladen (google-webfonts-helper oder direkt)
mkdir -p public/fonts

# 2. .woff2 Dateien in /public/fonts/ ablegen

# 3. @font-face in CSS definieren (siehe oben)

# 4. Pruefen: Keine Requests an googleapis.com
#    Browser DevTools → Network → Filter "googleapis"
#    Muss leer sein!
```

### Weitere externe Ressourcen

| Ressource | Problem | Loesung |
|-----------|---------|---------|
| Google Fonts CDN | IP an Google | Lokal hosten |
| Font Awesome CDN | IP an Cloudflare | Icons als SVG inline |
| jQuery CDN | IP an jQuery Foundation | Lokal hosten oder entfernen |
| Bootstrap CDN | IP an StackPath | Lokal hosten |
| Google Maps | IP + Standort an Google | 2-Klick oder Consent-Pflicht |
| YouTube | IP + Cookies an Google | `youtube-nocookie.com` nutzen |
| Vimeo | IP an Vimeo | Consent oder 2-Klick |
| Google reCAPTCHA | IP + Verhalten an Google | Alternative: hCaptcha oder Honeypot |

### YouTube Datenschutz-Modus

```html
<!-- FALSCH -->
<iframe src="https://www.youtube.com/embed/VIDEO_ID"></iframe>

<!-- RICHTIG (erweiterter Datenschutz-Modus) -->
<iframe src="https://www.youtube-nocookie.com/embed/VIDEO_ID"></iframe>
```

### Google Maps 2-Klick-Loesung

```html
<div id="map-placeholder">
    <p>Klicken Sie hier um die Google Maps Karte zu laden.</p>
    <p><small>Dabei werden Daten an Google uebermittelt.
    <a href="/datenschutz">Datenschutzerklaerung</a></small></p>
    <button onclick="loadMap()">Karte laden</button>
</div>

<script>
function loadMap() {
    document.getElementById('map-placeholder').innerHTML =
        '<iframe src="https://www.google.com/maps/embed?pb=..." ' +
        'width="100%" height="400" style="border:0" loading="lazy"></iframe>';
}
</script>
```

---

## 5. Formulare & Kontakt

### Pflicht-Anforderungen

- **HTTPS** auf der gesamten Website (nicht nur Formular-Seiten)
- **Datenschutz-Hinweis** bei/neben jedem Formular
- **Einwilligungs-Checkbox** (nicht vorausgewaehlt):

```html
<label>
    <input type="checkbox" name="privacy" required>
    Ich habe die <a href="/datenschutz" target="_blank">Datenschutzerklaerung</a>
    gelesen und stimme der Verarbeitung meiner Daten zu.
</label>
```

- **Datenminimierung**: Nur Felder die wirklich noetig sind
- **Speicherdauer** in der Datenschutzerklaerung angeben

### Newsletter

- **Double-Opt-In Pflicht**: Bestaetigung per E-Mail erforderlich
- **Abmeldung** in jeder E-Mail moeglich (1-Klick Unsubscribe)
- **Kein Koppelungsverbot**: Newsletter nicht an Dienst/Download koppeln

---

## 6. E-Commerce / Online-Shop

### Pflicht-Seiten

| Seite | Pflicht | Gesetz |
|-------|---------|--------|
| Impressum | Ja | TMG §5 |
| Datenschutz | Ja | DSGVO |
| AGB | Ja (bei Vertraegen) | BGB |
| Widerrufsbelehrung | Ja | §355 BGB |
| Muster-Widerrufsformular | Ja | EGBGB Art. 246a |

### Preis-Darstellung

```html
<!-- RICHTIG -->
<span class="price">49,99 EUR</span>
<small>inkl. MwSt., <a href="/versand">zzgl. Versandkosten</a></small>

<!-- Bei Waren nach Gewicht/Volumen: Grundpreis Pflicht (PAngV) -->
<span class="price">4,99 EUR / 250g</span>
<small>(Grundpreis: 19,96 EUR / kg)</small>
```

### Streichpreise (Omnibus-Richtlinie seit 2023)

Bei durchgestrichenen Preisen muss der **niedrigste Preis der letzten 30 Tage** angezeigt werden:

```html
<span class="old-price">59,99 EUR</span>
<span class="new-price">39,99 EUR</span>
<small>Niedrigster Preis der letzten 30 Tage: 49,99 EUR</small>
```

### Checkout-Pflichten

- **Bestelluebersicht** vor dem letzten Klick (Artikel, Preis, Versand, Gesamt)
- **Button-Text**: Muss "zahlungspflichtig bestellen" enthalten (§312j BGB)
- **Checkout-Checkbox**: AGB + Widerrufsbelehrung gelesen (nicht vorausgewaehlt)

```html
<button type="submit">Zahlungspflichtig bestellen</button>
<!-- NICHT: "Kaufen", "Bestellen", "Abschicken" -->
```

### OS-Plattform (EU Online-Streitbeilegung)

Pflicht-Link auf jeder Shop-Seite (meist im Footer + Impressum):

```html
<p>
    Die Europaeische Kommission stellt eine Plattform zur
    Online-Streitbeilegung (OS) bereit:
    <a href="https://ec.europa.eu/consumers/odr" target="_blank" rel="noopener">
        https://ec.europa.eu/consumers/odr
    </a>
</p>
```

### Bestellbestaetigungs-Email

Pflicht-Inhalt:
- Zusammenfassung der Bestellung
- Widerrufsbelehrung (nochmal!)
- Kontaktdaten
- Geschaetzte Lieferzeit

---

## 7. Cold-Outreach & Email-Marketing (UWG §7)

### B2B Cold-Email (erlaubt unter Bedingungen)

| Bedingung | Pflicht? |
|-----------|---------|
| Sachlicher Bezug zum Geschaeft des Empfaengers | Ja |
| Vollstaendiges Impressum in der Mail | Ja |
| Opt-Out-Moeglichkeit | Ja |
| Herkunft der Adresse erwaehnen (DSGVO Art. 14) | Ja, in erster Mail |
| Opt-Out-Liste fuehren | Ja (Widerspruch = nie mehr kontaktieren) |

### B2C Cold-Email

**Verboten** ohne vorherige ausdrueckliche Einwilligung. Keine Ausnahmen.

### Bestandskunden-Ausnahme (§7 Abs. 3 UWG)

Werbung an bestehende Kunden ist erlaubt wenn:
- Adresse im Zusammenhang mit einem Kauf erhalten
- Werbung fuer aehnliche Produkte
- Bei Erhebung UND in jeder Mail auf Widerspruch hingewiesen
- Kein Widerspruch eingelegt

---

## 8. Technische Sicherheit

### HTTPS

- **Pflicht** fuer jede Website mit Formularen oder Nutzerdaten
- Gesamte Website ueber HTTPS, nicht nur einzelne Seiten
- HTTP → HTTPS Redirect einrichten
- HSTS-Header setzen:

```
Strict-Transport-Security: max-age=31536000; includeSubDomains
```

### Security Headers

```
Content-Security-Policy: default-src 'self'; script-src 'self'
X-Content-Type-Options: nosniff
X-Frame-Options: DENY
Referrer-Policy: strict-origin-when-cross-origin
Permissions-Policy: camera=(), microphone=(), geolocation=()
```

---

## 9. Haeufige Abmahngruende (priorisiert)

| Prioritaet | Verstoss | Risiko |
|------------|---------|--------|
| KRITISCH | Google Fonts extern geladen | 100 EUR+ pro Besucher |
| KRITISCH | Kein/unvollstaendiges Impressum | 5.000-10.000 EUR |
| KRITISCH | Cookie-Banner fehlt bei Tracking | 1.000-5.000 EUR |
| KRITISCH | "Ablehnen" versteckt/kleiner als "Akzeptieren" | 1.000-5.000 EUR |
| HOCH | Datenschutzerklaerung fehlt/unvollstaendig | 2.000-5.000 EUR |
| HOCH | Newsletter ohne Double-Opt-In | 1.000-3.000 EUR |
| HOCH | Shop: Falscher Button-Text | 1.000-3.000 EUR |
| HOCH | Shop: Keine Widerrufsbelehrung | 5.000-10.000 EUR |
| MITTEL | Fehlende Grundpreisangabe | 500-2.000 EUR |
| MITTEL | Streichpreise ohne 30-Tage-Referenz | 500-2.000 EUR |
| MITTEL | Kein OS-Plattform-Link | 500-1.000 EUR |

---

## Rechtshinweis

Diese Checkliste ersetzt keine Rechtsberatung. Sie basiert auf dem Stand Maerz 2026 und deckt die gaengigsten Anforderungen fuer deutsche Websites und Online-Shops ab. Bei Unsicherheiten einen Fachanwalt fuer IT-Recht konsultieren.

Relevante Gesetze und Verordnungen:
- DSGVO (EU 2016/679)
- TTDSG (Telekommunikation-Telemedien-Datenschutz-Gesetz)
- TMG §5 (Telemediengesetz)
- UWG §7 (Gesetz gegen den unlauteren Wettbewerb)
- BGB §§312, 355 (Buergerliches Gesetzbuch)
- PAngV (Preisangabenverordnung)
- MStV §18 (Medienstaatsvertrag)
- Omnibus-Richtlinie (EU 2019/2161)

---

## Lizenz

MIT
