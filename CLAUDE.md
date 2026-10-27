# Silvio Schäfer · Prime Code™ Website
## Entwickler- & KI-Handbuch für Claude

Dieses Repository enthält den vollständigen, produktionsbereiten Webauftritt von **Silvio Schäfer Training & Coaching** (Hormon- und Leistungsoptimierung für Unternehmer ab 40).

---

### 1. Architektur & Philosophie
* **100% Vanilla Web:** Reines HTML5, modernes CSS3 und Vanilla JavaScript.
* **Keine Build-Tools:** Kein npm, kein Webpack, kein Vite nötig. Alle Dateien sind direkt im Browser lauffähig und können ohne Kompilierung auf jeden beliebigen Webspace / Host hochgeladen werden.
* **Responsive Design-System:**
  * Desktop (> 900px): Pinned Cinematic Storytelling mit Proximity-Ausleuchtung, 3D-Power-Hub und animierten Stage-Elementen.
  * Mobile (≤ 900px): Clean Editorial Flow, linksbündige Schweizer Typografie, Wandering-Line-Führung, 2-Spalten-Bento-Grid und touch-optimierte 44px-Pillen.

---

### 2. Projekt- und Ordnerstruktur
```
silvio-schaefer/
├── index.html                  # Hauptseite (Landingpage & Verkaufstrichter)
├── impressum.html              # Rechtliches Impressum (GmbH-konform)
├── datenschutz.html            # Datenschutzerklärung (DSGVO-konform)
├── assets/                     # Medien und Markenzeichen
│   ├── media/                  # Video, Transformationen, Porträts, Testimonials
│   │   ├── headervideo.mp4     # 3D-Hintergrundvideo mit rotierendem Powerbutton
│   │   ├── silvio2.png         # Silvios Porträtfoto (Über Silvio)
│   │   ├── transformations/    # 10 Vorher/Nachher-Vergleichsbilder (01 bis 10)
│   │   └── testimonials/       # 16:9 Thumbnails für Video-Interviews
│   └── Signet/                 # Offizielle Marken-Logos (SVG, 2x, 4x, EPS)
├── CLAUDE.md                   # Dieses Handbuch für KI-Assistenten (Claude)
├── DESIGN.md                   # Designtokens, Typografie & Farbpalette
├── README.md                   # Schnellanleitung für Silvio (Hosting & Upload)
├── .nojekyll                   # GitHub Pages Kompatibilität
└── .gitignore                  # Git-Ausschlussregeln
```

---

### 3. Corporate Identity & Design-Tokens

* **Primärer Hintergrund (Tiefschwarz):** `#171217`
* **Karten- & Panel-Hintergrund:** `#1B1619` / `#191419`
* **Performance-Akzent (Argon Orange):** `#FF6D29`
* **Sekundärtext (Muted Silver):** `rgba(255, 255, 255, 0.72)` / `#C9C6C4`
* **Feine Trennlinien (Border Subtle):** `rgba(255, 255, 255, 0.08)`
* **Typografie:**
  * Headings: `'Space Grotesk'`, sans-serif (800 / 700)
  * Body: `'Plus Jakarta Sans'`, sans-serif (400 / 500)
* **Wichtig:** Keine Gedankenstriche (`–` oder `—`) in Texten oder Code-Kommentaren verwenden.

---

### 4. Leitfaden für Änderungen (How-To)

#### A. Texte & Headlines ändern
Alle Abschnitte sind in `index.html` mit semantischen IDs versehen:
* `#top` → Hero-Stage (Headline, Subline, Haupt-Button)
* `#system` → Status Quo (Die 5 Kernsymptome mit Wandering Line)
* `#ansatz` → Der Ansatz (Die 5 Stellschrauben im Bento-Grid)
* `#programm` → Das Programm (10-Wochen-Roadmap Timeline)
* `#ergebnisse` → Dual-Proof Center (Vorher/Nachher-Slider & Video-Interviews)
* `#ueber-silvio` → Über Silvio (Story & Philosophie)
* `#kontakt` → Erstgespräch / Bewerbungsformular

#### B. Vorher/Nachher-Bilder austauschen oder hinzufügen
Die Vorher/Nachher-Transformationen liegen in `assets/media/transformations/` (`transformation-01.jpg` bis `transformation-10.jpg`).
In `index.html` steuert das Array `TRANSFORMATION_PAIRS` (Zeile ~6450) die Bilder:
```javascript
const TRANSFORMATION_PAIRS = [
  { id: 1, title: "Transformation 01", type: "composite", src: "assets/media/transformations/transformation-01.jpg" },
  // ... weitere Bilder
];
```
Die Bilder sind als Composit-Dateien formatiert (links Vorher, rechts Nachher, 16:9 oder 4:3).

#### C. Video-Interviews anpassen
Die Video-Testimonials in `#ergebnisse` nutzen YouTube-Einbettungen.
Um Videos auszutauschen, einfach die YouTube-Video-IDs in `index.html` anpassen:
* `data-video-id="GjwhQVk29pI"` (Helge Sidow)
* `data-video-id="y3U0BGE6pAE"` (Marco)

#### D. Formular-Versand einbinden (Backend / Webhook)
Das Formular `<form class="contact-form" id="applicationForm">` in `#kontakt` sammelt:
* `firstName`, `lastName`, `email`
* `selectedGoals` (Kommaseparierte Liste der angetippten Ziel-Pillen)
* `tried` (Optionales Freitextfeld für bisherige Versuche)

Um Anfragen per E-Mail oder CRM zu erhalten:
* **Option 1 (Make / Zapier / n8n Webhook):** Im JS-Event-Listener `applicationForm.addEventListener('submit', ...)` eine `fetch('DEINE_WEBHOOK_URL', { method: 'POST', body: ... })` eintragen.
* **Option 2 (Formspree / Formbold):** Dem `<form>` das Attribut `action="https://formspree.io/f/DEINE_ID" method="POST"` geben.

---

### 5. Lokales Testen & Live-Vorschau
Da keine Node-Pakete erforderlich sind:
* Im Editor (z. B. VS Code) mit der Erweiterung **Live Server** öffnen.
* Oder im Terminal mit Python: `python -m http.server 8000`
* Oder mit Node: `npx serve .`

---

### 6. Upload auf den Webserver / Hosting-Provider
Zum Veröffentlichen einfach den gesamten Inhalt des Ordners (inklusive `index.html`, `impressum.html`, `datenschutz.html` und des Ordners `assets/`) in das Hauptverzeichnis (`public_html`, `htdocs` oder `www`) des Webhosters hochladen (per FTP / FileZilla oder Web-Dateimanager).
