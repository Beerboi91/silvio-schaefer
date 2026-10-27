# Silvio Schäfer · Prime Code™ Website

Vollständiger, produktionsbereiter Webauftritt von **Silvio Schäfer Training & Coaching** (Hormon- und Leistungsoptimierung für Unternehmer ab 40).

---

## Schnellanleitung für den Upload (Hosting / Provider)

Diese Website ist als **reines statisches Web-Projekt** (HTML5, CSS3, JavaScript) gebaut. Es gibt **keine Build-Schritte**, keine Datenbank und keine Server-Abhängigkeiten. Die Seite läuft sofort auf jedem Webspace oder Hosting-Provider.

### Option A: Upload per FTP (All-Inkl, Strato, IONOS, Hetzner, Hostinger)
1. Verbinde dich mit deinem FTP-Programm (z. B. **FileZilla** oder **Cyberduck**) mit deinem Webspace.
2. Navigiere in das Zielverzeichnis deiner Domain (heißt meist `public_html`, `htdocs` oder `www`).
3. Lade alle Dateien und Ordner aus diesem Projektverzeichnis hoch:
   - `index.html` (muss direkt im Hauptverzeichnis liegen)
   - `impressum.html`
   - `datenschutz.html`
   - Ordner `assets/` (mit allen Unterordnern `media/` und `Signet/`)
4. Fertig. Deine Website ist unter deiner Domain erreichbar.

### Option B: Upload per Web-Dateimanager im Provider-Kundenbereich
1. Logge dich im Kundenbereich deines Providers ein (z. B. cPanel, Plesk, KAS bei All-Inkl).
2. Öffne den **Dateimanager** (File Manager).
3. Packe diesen Projektordner als `.zip`-Datei, lade die ZIP in das Hauptverzeichnis (`public_html` bzw. `htdocs`) hoch und entpacke sie dort.

### Option C: Modernes Cloud-Hosting (Vercel, Netlify, Cloudflare Pages)
- Einfach das Repository verknüpfen. Das Root-Directory ist direkt die Build-Ausgabe (kein Build-Command erforderlich).

---

## Ordnerstruktur im Überblick

```
silvio-schaefer/
├── index.html                  # Hauptseite (Landingpage & Verkaufstrichter)
├── impressum.html              # Rechtliches Impressum (GmbH-konform)
├── datenschutz.html            # Datenschutzerklärung (DSGVO-konform)
├── assets/                     # Alle verwendeten Medien & Marken-Assets
│   ├── media/                  # Video, Transformationen, Porträts, Testimonials
│   │   ├── headervideo.mp4     # 3D-Powerbutton Hintergrundvideo
│   │   ├── silvio2.png         # Porträtfoto von Silvio
│   │   ├── transformations/    # Vorher/Nachher-Vergleichsbilder (01–10)
│   │   └── testimonials/       # 16:9 Video-Thumbnails
│   └── Signet/                 # Offizielle Marken-Logos & Icons (SVG, PNG, EPS)
├── CLAUDE.md                   # Spezielles Handbuch für Änderungen mit KI (Claude)
├── DESIGN.md                   # Design-System, Farben & Typografie
└── README.md                   # Dieses Dokument
```

---

## Änderungen mit Claude vornehmen

Wenn du Anpassungen (Texte, Farben, Bilder oder Formularanbindung) mit **Claude** (Claude Code, Claude Projects oder Claude Desktop) vornehmen möchtest:
- Claude liest automatisch die beiliegende Datei **`CLAUDE.md`**.
- Darin sind alle Sektionen, Variablen und Anleitungen exakt beschrieben, sodass Claude präzise und fehlerfrei arbeiten kann.

---

## Kontakt & Impressum

**Silvio Schäfer Training & Coaching GmbH**  
Dürrlewangstraße 23, 70565 Stuttgart  
E-Mail: info@silvioschaefer.de  
Website: [www.silvioschaefer.de](https://www.silvioschaefer.de)
